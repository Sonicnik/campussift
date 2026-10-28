# CampusSift

**Discover campus events worth showing up for.**

An AI-powered campus event scout that finds opportunities across scattered sources, verifies the details, ranks them by your interests, and flags schedule conflicts.

Workshops. Founder meetups. Research talks. Club gatherings. Something fun on a Thursday.

CampusSift helps you find them—and understand whether you can actually attend.

## Why CampusSift?

Campus events are scattered across university calendars, department websites, club Instagram accounts, career platforms and registration pages.

Finding an announcement is only the beginning. Is it current? Open to undergraduates? On campus? Already full? Does it overlap with class?

CampusSift gives your AI agent a repeatable workflow for answering those questions and producing a useful event briefing.

## What it does

- **Searches across sources.** Checks university calendars, departments, student organizations and organizer pages.
- **Verifies practical details.** Looks for dates, times, venues, eligibility, costs and registration requirements.
- **Ranks for your interests.** Helps you assess opportunities for learning, building, meeting people and enjoying campus life.
- **Tracks events consistently.** Deduplicates announcements and preserves event codes across reports.
- **Checks conflicts.** Compares events with your supplied timetable, recorded selections and an authorized calendar.
- **Shows its limits.** Records which sources were checked and where access or information was incomplete.
- **Supports your selections.** Can create calendar holds through a connected calendar tool when you request them.

A calendar hold, an attendance selection and an organizer registration are tracked separately.

## Try it

Ask your agent:

> Find campus events for next week across my interests in AI, startups, physics and social activities. Check the active source directory and flag conflicts with my schedule.

You can also narrow the request:

> Find beginner-friendly robotics workshops and builder meetups over the next two weeks.

After reviewing a report:

> Add the Raspberry Pi workshop to my calendar.

Calendar actions require a connected tool and verified scheduling details. Creating a calendar entry does not register you with the organizer.

## How it works

1. **Set the scope.** Specify your campus, interests and date window.
2. **Check the sources.** Work through the active source directory and verify live access.
3. **Verify each event.** Read organizer listings, registration pages and flyer images where needed.
4. **Assess the options.** Remove duplicates, identify participation barriers and check schedule conflicts.
5. **Save the briefing.** Produce a report with stable codes, source links, recommendations and explicit gaps.

Comprehensive discovery documents every qualifying event found. The final top-five recommendation is a starting point for browsing the report.

## What you get

Each report includes:

- Your selected events in the requested window.
- Newly discovered opportunities, grouped by interest.
- Previously reported events that are still upcoming.
- Dates, venues, organizer links and participation requirements.
- Named conflicts and tight travel transitions.
- Separate quality and rarity scores.
- Unverified leads, actionable deadlines and source coverage notes.

Reports are saved as Markdown so you can read, edit and keep them locally.

## Use as a skill

The discovery instructions are in [`skills/duke-campus-events/SKILL.md`](skills/duke-campus-events/SKILL.md). The current skill identifier is `duke-campus-events`.

Use an agent that supports skills and browser tools. Keep the supporting source directory and workflow files available to the agent, and configure workspace paths for your installation. The current skill contains a local workspace path that must be adjusted before using it elsewhere.

The included [source directory](Duke_Event_Discovery_Master_List.md) covers **Duke University**. Using CampusSift at another university requires a campus-specific source directory, scope and timetable. Review the [workflow plan](EventSourcer_Plan.md) for the included defaults and replace personal schedule settings with your own.

Browser access is configured separately. See [browser setup](docs/Playwright_MCP_Setup.md) for the tested Playwright MCP approach.

## Browser integration and plugin packaging

CampusSift's discovery skill supplies the workflow; [Microsoft Playwright MCP](https://github.com/microsoft/playwright-mcp) supplies browser tools.

The intended plugin will bundle the skill with configuration that launches Playwright MCP as an external dependency. Browser profiles and login sessions stay on each user's machine.

**Plugin packaging is planned.** The current repository provides the skill, workflow documentation and Duke source directory; it does not yet provide a one-step plugin installer or automatically register a browser server. No cross-agent installation compatibility is claimed.

## Access and privacy

Public sources can be checked without signing into university accounts. Restricted sources require your own authorized session; complete sign-in and multifactor authentication directly in the browser.

Calendar access is optional. Discovery can run without it, with calendar conflict checking marked incomplete.

Keep browser profiles, credentials, calendar exports and personal reports out of version control. Account connections, registrations, messages, calendar changes and scheduled monitoring require your instruction.

## Limitations

- Listings can change after verification.
- Some announcements are private, temporary or unavailable to the browsing tool.
- Recurring meetings may have cancellations that are not publicly posted.
- Missing hours, venues or eligibility rules remain explicitly unverified.
- Comprehensive source passes can take substantial time and tokens.
- Compatibility depends on the agent and tools configured for your installation.

CampusSift reports what it could verify and where you still need to check with the organizer.
