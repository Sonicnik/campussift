<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img src="assets/logo.svg" width="180" alt="CampusSift logo: scattered dots pour into a funnel and one highlighted event comes out">
  </picture>
</p>

<h1 align="center">CampusSift</h1>

<p align="center">
  <em>Discover campus events worth showing up for.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude%20Code-plugin-111111?style=flat-square" alt="Claude Code plugin">
  <img src="https://img.shields.io/badge/browser-Playwright%20MCP-111111?style=flat-square" alt="Browser: Playwright MCP">
  <img src="https://img.shields.io/badge/campus-any%20university-111111?style=flat-square" alt="Campus: any university">
  <img src="https://img.shields.io/github/stars/Sonicnik/campussift?style=flat-square&color=111111&label=stars" alt="Stars">
</p>

<p align="center">
  <strong>Find</strong> &middot; <strong>Verify</strong> &middot; <strong>Rank</strong> &middot; <strong>Conflict-check</strong> &middot; <strong>Calendar</strong>
</p>

---

Workshops. Founder meetups. Research talks. Club nights. Something fun on a Thursday.

They are all on campus somewhere: a department calendar, a club's Instagram, a career portal, a registration form. CampusSift is an AI agent skill that finds where your university posts events, goes through those sources for you, checks whether each event is real, current and open to you, ranks it against your interests, and tells you what clashes with your week.

You get one report. You pick codes. It puts them on your calendar.

## Install

**Claude Code**, in your terminal:

```bash
claude plugin marketplace add Sonicnik/campussift
```
```bash
claude plugin install campussift@campussift
```

Or inside a Claude Code session, as two separate prompts:

```
/plugin marketplace add Sonicnik/campussift
```
```
/plugin install campussift@campussift
```

Start a new session afterward so the skill and browser tools load. You need [Node.js](https://nodejs.org) (for `npx`) and Google Chrome.

**Other agents:** copy [`skills/campus-events/`](skills/campus-events/) into your agent's skills folder and register Playwright MCP yourself ([setup notes](docs/Playwright_MCP_Setup.md)). Only Claude Code has been tested.

**Update** to the latest version:

```bash
claude plugin marketplace update campussift
```

## First run

Open Claude Code in a folder you'll keep, such as `~/campus`, and ask for events:

> Find campus events for next week.

The first time, CampusSift asks a few questions: your university, your interests in priority order, anything to skip, and optionally your class timetable. Then it builds a list of where your campus posts events: the central calendar, student activities, the career center, departments matching your interests, arts and rec, and club accounts. Both are saved as plain Markdown you can edit:

```
~/campus/campussift/
├── profile.md      your campus, interests, timetable, preferences
├── sources.md      where your campus posts events
├── signups.md      events you picked
└── reports/        one report per run
```

Every run after that goes straight to finding events.

## Try it

> Find campus events for next week across my interests in AI, startups, physics and social activities, and flag conflicts with my schedule.

> Find beginner-friendly robotics workshops and builder meetups over the next two weeks.

After reading the report:

> Add 014 and 027 to my calendar.

## How it works

<p align="center">
  <strong>Sources</strong> &rarr; <strong>Verify</strong> &rarr; <strong>Rank</strong> &rarr; <strong>Conflicts</strong> &rarr; <strong>Report</strong> &rarr; <em>you pick codes</em> &rarr; <strong>Calendar</strong>
</p>

1. **Set the window.** Defaults to next Monday through Sunday in your campus's timezone. Ask for any other range.
2. **Sweep the sources.** Works through every relevant source in your `sources.md`, by topic and by organizer. Club accounts first for student announcements, then the official page to verify.
3. **Verify each event.** Reads listings, registration pages and flyer images. Unknown details stay marked unknown.
4. **Dedupe and rank.** One stable code per event or recurring series, kept across weeks. Ranked for fit, access and a real chance to meet people.
5. **Check conflicts.** Against your class timetable, your other selections and your calendar, if you connected one.
6. **Save the report.** A dated Markdown file in `campussift/reports/`, earlier reports kept.

## What a report looks like

<sub>Illustrative entry. Names, times and venues are made up.</sub>

> ### Builders & research
>
> **`014` · Intro to Robot Arms Workshop**
>
> A hands-on session building and programming a small robot arm. Teams of three, beginners welcome.
>
> 🗓 Wed Dec 2, 6:00–8:00 p.m. ET &nbsp;·&nbsp; 📍 Makerspace, Room 101 &nbsp;·&nbsp; 👥 Engineering student makerspace<br>
> ⚠️ **Conflict:** overlaps your 5:15–6:30 p.m. lab section<br>
> ⭐ **Quality** 8/10 &nbsp;·&nbsp; 💎 **Rarity** 7/10 &nbsp;·&nbsp; 🎟 RSVP required, 20 seats

Every report has, in order:

| Section | What's in it |
|---|---|
| **Your selections** | Events you already picked, with registration status |
| **Newly found** | Every qualifying new event, grouped by field |
| **Still upcoming** | Earlier finds you haven't picked yet |
| **Source coverage** | Each source checked, dates covered, and any gaps |
| **Top five** | The final paragraph: five new events worth a look, and why |

## What it will and won't do

| ✅ Does | 🚫 Won't, unless you ask |
|---|---|
| Read public listings and pages | Register you with an organizer |
| Use a browser session you signed into yourself | Sign in, connect accounts or read your email |
| Check conflicts against your calendar | Remove or replace events already on your calendar |
| Add calendar holds for the codes you pick | Set up recurring or scheduled monitoring |
| Say which sources it couldn't reach | Claim it covered all of campus when it didn't |

A calendar hold is not a registration. CampusSift tracks your selection, your RSVP and the organizer's confirmation separately, and tells you which one you have.

## Make it yours

Everything personal lives in your `campussift/` folder, not in the plugin. Edit it directly or just tell your agent:

- **Interests and priorities:** "Put hackathons above career fairs" updates `profile.md`.
- **Timetable:** paste your schedule; it's used for warnings only.
- **Sources:** add a club's page or Instagram to `sources.md`, or mark a source paused.
- **Overlaps:** keep both and warn (default), or ask before adding.

**See a full setup:** [`examples/duke/`](examples/duke/) has a real profile and a 121-source directory for Duke University. Duke students can copy its `sources.md` into their own `campussift/` folder and skip building one.

## What's inside

```
campussift/
├── .claude-plugin/                 plugin + marketplace manifests
├── .mcp.json                       starts Playwright MCP (Chrome)
├── skills/campus-events/
│   ├── SKILL.md                    the workflow, with profile and sources templates
│   └── agents/openai.yaml          Codex metadata
├── examples/duke/                  a complete Duke setup
└── docs/Playwright_MCP_Setup.md    manual browser setup notes
```

## Privacy

- Your profile, sources, reports, browser profile and sign-ins stay on your machine.
- You complete any sign-in or multi-factor prompt yourself, in the browser window.
- Calendar access is optional. Without it, discovery still runs and the conflict check is marked incomplete.

## Limits

- Listings change after they're checked, and some announcements are private or hidden from the browser.
- Recurring meetings can be cancelled without notice online.
- A full sweep of every source takes a while and uses a lot of tokens.
- Calendar writes need a Google Calendar tool connected to your agent.

CampusSift tells you what it verified, and where you still need to ask the organizer.
