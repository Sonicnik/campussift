---
name: campus-events
description: Find in-person campus events for a student at any university (workshops, talks, career events, club meetups, socials), verify the details, rank them by the student's interests, flag schedule conflicts, and add the events they pick to their calendar. Use when the user asks what's on at their campus, wants events for next week, names an interest to find events for, or replies with event codes from a CampusSift report.
---

# Campus events

## Files

All state lives in a `campussift/` folder in the user's current working directory. Never write state into this skill's own folder.

| File | Holds |
|---|---|
| `campussift/profile.md` | Campus, timezone, term dates, interests, things to skip, class timetable, preferences |
| `campussift/sources.md` | Where this campus posts events, with access status |
| `campussift/signups.md` | Upcoming selected events, with registration and calendar status |
| `campussift/reports/YYYY-MM-DD.md` | One report per run, history kept |

Templates for the first two are at the end of this file. Reread `profile.md` and `sources.md` every run: the user may have edited them. A preference the user states in chat overrides the profile for that run; when they say it should last, update `profile.md`.

## First run: set up

**If `campussift/profile.md` is missing:**

1. Ask in one message, skipping anything the user already said: their university and campus; their interests in priority order; anything to leave out; their class timetable (optional, they can paste it); whether to check their calendar for conflicts; and, when two selected events overlap, whether to keep both and warn (default) or ask first.
2. Look up the university's official academic calendar for the timezone, term dates and breaks. Work out what counts as on campus: the main campus areas plus venues physically connected to them. Venues elsewhere in town are off campus even when the university hosts the event.
3. Write `profile.md` from the profile template below, citing the academic calendar link. Show the user a three-line summary.

**If `campussift/sources.md` is missing:**

1. Build it from the live web. Search for, and open, at least: the university's central events calendar; the student activities office and its club directory or events feed; the career center and the career platform it uses; the entrepreneurship or innovation center; the events or seminar page of each department matching the user's interests; the arts center, student union, recreation center and residential life; and the student newspaper's event listings. For clubs in the user's interests, find where they announce events (often Instagram).
2. Record each one in the sources template format below, with a code (G general, C career, E entrepreneurship and tech, A academic and research, S social and arts, K clubs), URL, what it covers, access (public, sign-in, members-only or unknown) and the date checked. A source you didn't open is marked unverified. Only record URLs you actually found; never guess one.
3. Favor breadth: 20 to 60 sources is typical. Tell the user how many you found in each group and which ones need them to sign in.

If the user only asked to set up, stop here. Otherwise continue to discovery.

## Discovery

- **Window:** default is next Monday 00:00 to the following Monday 00:00 (exclusive) in the profile's timezone. On a Monday, next week starts seven days later. Use any window the user asks for, and state the actual dates in the report.
- **Before browsing,** read the profile, sources, `signups.md` and recent reports.
- **Cover every relevant active source,** by topic and by organizer, starting with the user's top interests. For student clubs, check where the club posts first, then verify on the official event or registration page. Use the browser tools for pages that need JavaScript or a sign-in. The user completes any sign-in themselves. Recheck access each run: earlier access is not current access. Skip sources the profile lists as paused.
- **Scope:** in-person and on campus per the profile. Leave out virtual-only and cancelled events. Keep sold-out or closed-registration events, labelled with that barrier. A lead with no confirmed room goes in an unverified section.
- **Verify** the date, local time, venue, host, recurrence, eligibility, cost, registration or deadline, cancellation status, and whether there is a real chance to meet people. Read flyer images when the caption leaves details out. Expand multi-day agendas, since daily hours can differ. Unknown details stay marked unknown. Keep dated announcements apart from recurrence you inferred.
- **No cap:** document every qualifying event. Deduplicate cross-posts.
- **Codes:** a stable three-digit code per one-off event or recurring series, reused in later reports and never reused for a different event. Keep leading zeroes.
- **Coverage:** for each source, record checked with events, checked with none, partial, inaccessible or not checked, with the dates covered. Never claim complete coverage while gaps remain.
- **New sources** found along the way go into `sources.md`.

## Ranking

- **Quality, 1–10:** host strength and evidence of interest, fit with the profile's interests, and a realistic chance to meet people. A prominent logo is not evidence of attendance.
- **Rarity, 1–10:** how seldom this happens. Weekly series score low; annual or one-time events score high. Mark estimates as provisional when recurrence is unclear.
- Keep the two scores separate. Group events by the profile's interests in priority order; within a group, sort by quality and break close ties by rarity.

## Report

Save `campussift/reports/YYYY-MM-DD.md` using the run date. If the file exists, append a dated update instead of overwriting. Sections, in order:

1. **Your selections** in the window, from `signups.md`: name, date, time, venue and registration status.
2. **Newly found,** grouped by interest.
3. **Still upcoming** from earlier reports and not yet selected.
4. **Unverified leads,** and deadlines falling in the window for later events.
5. **Source coverage and gaps,** including whether the conflict check was complete.
6. **Top five:** the last paragraph ranks up to five newly found events and says why each is worth a look. If none are new, say so.

Each event entry has: code, linked name (the current organizer listing), a two-sentence description that mentions any real barrier (cost, eligibility, RSVP), host, date and time, venue, conflict flag, quality score and rarity score. Show a recurring series once, with its occurrences in the window.

## Conflicts

- Check against the profile's class timetable (not during breaks or after classes end), the user's selections, and their calendar when the profile allows it and a calendar tool is connected. Paginate calendar results fully and ignore holiday calendars.
- Flag direct overlaps and transfers too tight to walk between venues.
- **Name events, never codes,** in conflict prose. Give one short sentence on what each event is, then the overlap. For example: "Market Making in Prediction Markets is a practitioner talk on prediction-market trading. Presenting Research at Conferences is a workshop on writing abstracts; it ends at 6 p.m. across campus, when the talk begins, leaving no time to get there."
- Classes are warnings, not blockers. Follow the profile's overlap preference and don't ask the same question again.
- If the calendar can't be read, say the conflict check is incomplete. Never report "no conflicts" in that case.

## When the user picks codes

1. Resolve each code against saved reports. A series resolves to its next dated occurrence in the report; say which date. Recheck the organizer page, and the calendar for duplicates, before writing.
2. Ask only for details genuinely needed to schedule, such as an unknown end time or an ambiguous date.
3. If a calendar tool is connected, add one entry per selection: the title is the event name only, times are local, there are no guests and no video link. Split a multi-day daytime event into one entry per day. In the description, write prose, then `Event details: <url>` on its own line, then more prose on the very next line, using single newlines with no blank line right after the URL (some connectors wrap it in markup otherwise). Read each entry back and verify the title, times, venue and link. If a write fails, report what was done, and check for an existing entry before retrying. Never create duplicates.
4. With no calendar tool, give the user the details and say nothing was added.
5. Track three statuses separately: selected, RSVP'd (the user says so), and registered (the organizer confirmed). A calendar entry is not a registration. Register with an organizer only when the user asks.
6. Update `signups.md` with future selections, links, status and calendar IDs, and drop events that have passed.

## Never without being asked

Sign in for the user, connect accounts, read their email, register for events, message organizers, remove or replace existing calendar events, or set up scheduled runs.

## Templates

`campussift/profile.md`:

```markdown
# CampusSift profile

## Campus

- **University:**
- **On campus counts as:** <main campus areas, plus venues connected to them. Anything else is off campus, even if the university hosts it.>
- **Timezone:** <IANA name, e.g. America/New_York>
- **Academic calendar:** <link>
- **Term:** <classes start> to <classes end>. Breaks: <dates>

## Interests, in priority order

1.

## Leave out

-

## Class timetable

<Optional. Times are local. Classes are warnings, not blockers.>

| Day | Time | Class |
|---|---|---|

## Preferences

- **Calendar for conflicts and holds:** <Google Calendar, primary | none>
- **Overlapping selections:** <keep both and warn | ask first>
- **Paused sources:** <sources not to use, e.g. email newsletters>
- **Default window:** next Monday to Sunday
```

`campussift/sources.md`:

```markdown
# CampusSift sources: <University>

Built <date>. Access is public, sign-in, members-only or unknown. A source not opened yet is marked unverified.

Groups: G general, C career, E entrepreneurship and tech, A academic and research, S social and arts, K clubs.

| Code | Source | URL | Covers | Access | Last checked |
|---|---|---|---|---|---|
```
