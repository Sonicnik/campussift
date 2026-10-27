---
name: duke-campus-events
description: Run EventSourcer to discover Duke on-campus events across the user's academic, career, builder, and social interests, report schedule conflicts, and add selected events to Google Calendar.
---

# Duke campus events

Use this workflow for campus event discovery and follow-up selections. The working directory is `/Users/soni8nik/Documents/Codex/EventSourcer`. Read its `AGENTS.md`, `Duke_Event_Discovery_Master_List.md`, current plan, `Upcoming_Signups.md`, and relevant recent reports. The directory is a source map, not proof of live access. These campus-only instructions and the user's latest preferences supersede older off-campus/report/conflict rules in that workspace.

## Discovery

- Default to the next Monday–Sunday in America/New_York, following the date boundaries, source coverage table and completion checks in the current discovery workflow in `EventSourcer_Plan.md`. Use another window when requested. Do not inherit an expired semester schedule or create monitoring/automations merely by invoking this skill.
- Include in-person events at Duke's main, East, and connected campus venues, such as the Rubenstein Arts Center and Freeman Center. Exclude virtual-only sessions, campus farm/forest/observatory destinations, and Durham/Triangle venues outside campus, even when Duke hosts them. Put roomless campus leads in an explicitly unverified section until a venue is confirmed.
- Find all qualifying events in the requested window, without a shortlist-size cap. Cover the relevant sources across physics and astronomy; quantum computing and materials; math, probability, statistics and quant trading; finance, economics and investing; CS, AI, engineering and robotics; startups, product and entrepreneurship; interdisciplinary research, climate and energy; and campus social, cultural, arts, music, games, food, quad and student-group activities. Include interactive workshops, small discussions, employer visits, competitions and social gatherings, not just prominent talks. Leave BME out of the personalized tech priority as currently requested.
- Search by both topic and organizer using every relevant active source in the master directory. Include organizer/club Instagram first for student announcements, then current official event or registration pages to verify. Use the connected Chrome session when browsing logged-in sources; recheck access rather than assuming a prior login still works. Duke Groups event/member discovery, Duke email, newsletters and listservs remain paused. Do not connect accounts or a Duke mailbox. If Handshake is blocked, report the gap and use public Career Hub details without claiming to have checked restricted RSVP/cohort information.
- Verify dates, Eastern times, campus venue, host, recurrence, eligibility, costs, registration/deadline, cancellation status and actual opportunity to meet people. Read flyer images when captions omit details; expand multi-day agendas because daily hours can differ. Distinguish current dated announcements from inferred recurrence. Record each checked source, covered dates and inaccessible/incomplete sources; never claim exhaustive campus coverage while gaps remain.
- Deduplicate cross-posts. Reuse stable report codes; one code per one-off event or recurring series. Keep codes for selection and tracking, including leading zeroes. Do not reuse a code for an unrelated event or automatically select every occurrence of a series.

## Reports and conflicts

Save dated Markdown reports under `reports/` and preserve history. Put upcoming selected events first, then all newly found unsigned events, then earlier unsigned events still upcoming, with source gaps before a final top-five paragraph. Group campus entries by field so physics, quant/finance, builders/research, and social options are easy to find. Each entry includes a selectable code, linked name, two-sentence description, host, date/time, venue, conflict flag, separate quality and rarity scores, and material participation barriers. Rank for fit, host/access, and realistic interaction; do not hide qualifying low-scoring events.

Check the primary Google Calendar in a bounded window, paginate fully, and check conflicts among selections plus the current class timetable in the workspace plan. Ignore US holiday events. Apply the academic calendar's breaks and term dates; verify a new term's timetable instead of assuming Fall 2026 repeats.

**Conflict prose uses event names, never selection codes.** Name each event and give one short sentence explaining what it is about, then the overlapping hours or walking-time problem. For example: “Market Making in Prediction Markets is a practitioner talk about prediction-market trading. Presenting Research at Conferences is a workshop on writing abstracts; it ends in Bostock at 6 p.m., when the talk begins in Gross, leaving no transfer time.” Use the same convention inside calendar descriptions.

The user has explicitly chosen to keep overlapping selected events and decide on the spot. Report overlaps and tight transitions, then add requested selections without asking the same keep-both question again. Classes are warnings, not blockers. Keep existing commitments unless the user explicitly asks to replace/remove one. If the user changes this preference, follow their current decision. Ask only for genuinely missing details needed to schedule, such as an unknown end time or an ambiguous occurrence date.

## Selection and calendar writes

Resolve selections against saved reports and recheck organizer details and calendar duplicates before writing. A series selection defaults to its next concrete dated occurrence in the current report when unambiguous; explain that date. Distinguish an expressed attendance selection, a user-reported completed RSVP, and an organizer-confirmed registration. A calendar hold is not registration. Complete organizer registration only when the user asks for it and required information/permissions are available; otherwise provide the registration link and accurate pending status.

Use the connected Google Calendar tools with `calendar_id: primary`, Eastern start/end times, `attendees: []`, and `add_google_meet: false`. Split a multi-day daytime workshop into one timed entry per day so evenings and overnight hours are not falsely blocked. Search by date, title and source link as well as tracker ID, since calendar titles contain no codes.

**Calendar title:** the human event name only. Do not prefix/suffix a selection code.

**Calendar description:** plain prose before and after the source URL. Put the URL on a line in the middle of the description, preceded by an event-details label and immediately followed by useful prose on the next line. Use single newlines throughout this paragraph; do not put a blank line directly after the URL, because the connector converts that into a closing paragraph tag touching the URL. Do not manually add HTML tags or use a URL as the opening/final text. This prevents connector-added paragraph tags from touching the URL when Google Calendar syncs to Apple Calendar. Keep codes in the local tracker, not the event title or conflict prose.

Example description:

```text
A discussion of quantum research with students and postdocs. Hosted by Duke Quantum Center.
Event details: https://calendar.duke.edu/verified-event-link
Arrival: tea and cookies from 1:45 p.m.; seminar starts at 2 p.m.
Registration: no attendee RSVP requirement stated in the listing.
Schedule note: finishes 30 minutes before your physics section.
```

Read back each created/updated event and verify its title, times, venue, intact source URL with following prose, no attendees and no conferencing. If the connector adds the calendar owner as an attendee, remove that attendee and recheck while retaining the organizer. If a write fails, preserve confirmed IDs, report partial completion, and inspect for an existing write before retrying; never create duplicates.

Update `Upcoming_Signups.md` with future selections, organizer links, registration status and verified calendar IDs; a multi-day selection may have multiple IDs. Expired signups leave the tracker but remain in report/calendar history. Save a concise selection/conflict receipt using names and one-sentence descriptions. Confirm only verified calendar writes and registration submissions; do not claim Apple Calendar sync itself was verified without checking it.
