# EventSourcer weekly plan — Fall 2026

## Current discovery workflow — October 23, 2026

This section defines the discovery workflow for this workspace and supersedes older discovery defaults, including the two-week default in any installed copy of the skill. Use the workspace skill at `skills/duke-campus-events/SKILL.md` together with this plan.

**Browser connection:** use the configured `eventsourcer_browser` Playwright MCP tools when available. See `docs/Playwright_MCP_Setup.md` for the tested setup, private profile and login procedure. An already-running chat may need a new chat/reload to load the connection. Check tool availability and source access before claiming coverage; use other authorized browser tools only with their access state identified. The Playwright profile starts without the existing Chrome session's logins.

### Window and source pass

1. Resolve **next week** as the next Monday through Sunday in `America/New_York`: start at Monday 00:00 and stop at the following Monday 00:00, exclusive. State the actual dates in the report. On a Monday, next week begins seven days later. Use another window when the user explicitly requests it. For example, an October 23, 2026 run covers October 26–November 1.
2. Read `Duke_Event_Discovery_Master_List.md`, its access audit, `Upcoming_Signups.md`, and prior reports before browsing. Work through every relevant active source in the master directory, searching by organizer as well as topic. Refresh startup/software/AI/product/builder sources first, then cover the other eligible academic, career, research and social sources. A top-five list is a presentation aid, not a stopping condition.
3. Maintain a source coverage table in the report: source code/name, URL, date checked, dates covered, result and access limitation. Account for relevant active sources as checked with qualifying events, checked with none found, partially checked, inaccessible, or not checked. Identify paused and out-of-scope directory sources separately; do not activate them. Historical access is not current verification. If the pass is incomplete, save the partial report and identify the remaining sources.
4. Use organizer Instagram first for student announcements, then official event/registration pages where available. Read flyer images and daily agendas when necessary. Use available authorized browser tools and check signed-in access afresh. Duke Groups event/member feeds, Duke email, newsletters and listservs remain paused.
5. Document **every qualifying event found in the window**, with no cap. New discovery remains in-person and on Duke campus; preserve earlier off-campus selections only as existing commitments. Separate unverified venue/time leads from confirmed campus listings. Exclude canceled events and label sold-out or closed-registration events with their participation barrier rather than presenting them as open signups. Keep recurrence-derived dates distinct from dated announcements.
6. Verify event dates, Eastern times, venue, host, recurrence, eligibility, cost, registration/deadline and realistic opportunities to meet people. Record unknown details explicitly. Deduplicate cross-posts, preserve stable event codes, and distinguish newly found from previously reported events. Include a later campus event only in a separate deadline section if an actionable application/registration deadline falls in the requested week; it is not an event occurring next week.
7. Check classes, local selections and the primary calendar when available. Report named overlaps and tight transfers. If calendar access fails, state that calendar checking is incomplete rather than claiming no conflicts.

### Saved report and completion

Save `reports/YYYY-MM-DD.md` using the actual run date, preserving earlier reports and same-day work (append a clearly dated update if that file already exists). Include, in order:

1. Selected events occurring next week, with registration and calendar status distinguished.
2. All newly found unsigned qualifying events.
3. All previously reported unsigned qualifying events still occurring in the window.
4. Any unverified leads and later-event deadlines, clearly separated from the week's confirmed inventory.
5. Source coverage table, gaps and incomplete conflict checks.
6. A final paragraph ranking up to five newly found events and explaining their fit; state when none are new.

Lead unsigned sections with startup/software/AI/product/builder events, followed by other academic/professional and social options. Each discovered event has a stable code, linked name, two-sentence description, host, date/time, venue, conflict flag, quality score and rarity score; include material eligibility, registration and cost barriers in its description. Compress recurring series into one entry with the week's occurrence dates.

Before reporting completion, verify the dated report exists, all relevant active directory sources have a recorded coverage status, every qualifying finding is represented once, codes are stable, expired entries have left the upcoming tracker without implying attendance, history is preserved, and the final paragraph contains the top picks. Discovery alone creates no calendar events, organizer registrations, account connections or scheduled tasks. Calendar additions follow only the user's selections; keep selected overlaps under the standing preference.

## Priority correction — October 19, 2026

The user reaffirmed that **startups, software engineering, AI, product and technical builder communities are the top discovery and presentation priority**. Lead the unsigned-event briefing with hands-on software/AI workshops, build sessions, hackathons, founder conversations, demos, developer employer visits and product communities. Complete the live Pathways/Co-Lab and organizer-specific startup/software pass before expanding general academic or social inventory; an old carried listing is not a substitute for refreshing these sources. Broad physics, quant/finance, academic and social events remain eligible and uncapped, but appear after the priority tech section. Do not let a general campus calendar dominate the top five or treat any AI-keyword talk as equivalent to building software or meeting founders.

## Current workflow preferences — October 4, 2026

Use the workspace `duke-campus-events` skill at `skills/duke-campus-events/SKILL.md`. Current scope is Duke on-campus events only, across all related academic, career, builder and social fields, with no cap on qualifying listings. Default manual discovery covers next Monday–Sunday unless the user specifies another window; the dated semester schedule below does not create a new automation.

The user explicitly prefers adding all selected events despite conflicts and deciding on the spot. Report each conflict with the event names and one short sentence about each, without selection codes; do not hold the batch for a repeated keep-both question. Retain existing events unless replacement is explicitly requested. Classes remain warnings. Use codes only for reports/selections and local tracking, never calendar titles or conflict prose.

Calendar descriptions must have prose before and after the source URL within the same paragraph, using single newlines. A blank line immediately after the URL makes the connector add `</p>` directly to it; do not use that layout. Verify the written description and title. Record selection, calendar creation and organizer RSVP as distinct statuses. Split multi-day daytime events into their actual daily hours. These preferences supersede contrary off-campus, ranking-layout and conflict-choice requirements in the historical plan below.

## Historical semester schedule

Find Duke and nearby opportunities to meet builders, founders, students, researchers, and professionals, while also showing enjoyable social events. Tech and startups have the highest priority. Use [the master directory](Duke_Event_Discovery_Master_List.md) for sources and its dated access audit for what may be reachable.

The historical schedule called for **12:00 a.m. Saturday, America/New_York** reports, starting after this plan is set up. The signup briefing covers the following Monday through Sunday. The original semester-wide discovery horizon is replaced by the requested week above. Stop the weekly run after **December 16, 2026** (last Saturday run: December 12). This is a semester-specific plan.

## Files

- Save each report as `reports/YYYY-MM-DD.md`, using the actual run date. Preserve earlier reports.
- Keep only future confirmed signups in [Upcoming_Signups.md](Upcoming_Signups.md). Update it when the user replies with event codes. Remove an entry when the user says they attended or after its end time has passed; leave past Google Calendar entries intact.
- Reuse stable event codes from earlier reports. Give each one-off event its own code. Give a recurring series one code; the user names a date along with the code when signing up for an occurrence. Read prior reports to determine whether an event or series is new.

## Weekly source pass

1. Read the master directory, its latest access audit, prior reports, and the upcoming-signups file. Check every active, accessible source in the directory. For student groups, look at the organizer's Instagram account first. Use the organizer's current public event or registration page to verify details where possible. Do not use the paused Duke Groups event/member feeds, Duke email, newsletters, or listservs. Do not connect a Duke mailbox. Leave BME in the directory but out of the personalized tech priority unless the user changes that preference.
2. Search by organizer as well as topic. Include on-campus social gatherings, competitions, conferences, workshops and application opportunities in the requested window. Check an outside organizer and its Duke host when both may list the same visit. Deduplicate copies of the same event.
3. Verify the date and time in Eastern Time, host, venue or virtual format, recurrence, eligibility, registration or application deadline, and whether there is a meaningful way to meet people. Check fees and off-campus travel time/cost for assessment; mention material barriers within the two-sentence description. If a fact cannot be verified, state the uncertainty rather than inventing it. Record sources that were inaccessible or had incomplete feeds, and never claim complete coverage from an old access test.
4. Remove events that have passed, are canceled, or no longer have an actionable deadline. Keep all found qualifying opportunities without a list-size cap. New recommendations must meet the campus-only scope.

## Ranking and scores

Place newly reported events before previously reported ones. Within each group, include campus events only and use these tiers: **tech/startup**, **other professional/research**, then **social**. Within each tier, order by quality score, using rarity to break close ties. Treat downtown Durham, Research Triangle Park, Chapel Hill, Cary, Raleigh, Duke Forest, and venues outside Duke's main and East Campus as off campus, even when Duke hosts the event. A recurring series becomes previously reported after its first weekly report; show one entry with its schedule, such as “every Saturday at 7 p.m.”, rather than repeating each occurrence.

- **Quality, 1–10:** Score host strength and evidence of popularity first, then fit with the user's goals and realistic opportunities to meet people. Do not treat a prominent logo or an estimated crowd as verified attendance. A good small meetup can still score well when it offers unusually strong access to the right people.
- **Rarity, 1–10:** Score how infrequently the opportunity occurs and whether this specific access is unusual. Weekly series score low; annual or one-time opportunities score high. When recurrence is uncertain, give a clearly marked provisional estimate.
- Keep the two scores separate. Neither is a claim that the user should register.

## Report layout

1. **Signed up next week:** From `Upcoming_Signups.md`, show each event's name, date, time, and location only. If there are none recorded, say so.
2. **Newly found:** All qualifying events and series not in earlier reports **that the user has not signed up for**, grouped by field with the tech/builder priority first.
3. **Previously reported and still upcoming:** All earlier unsigned-up events or series still within the search window, likewise grouped by field and ranked. Note material schedule changes or cancellations. Keep signed-up events in the briefing and `Upcoming_Signups.md`, not in the discovery lists.
4. **Source gaps:** Briefly list active sources that could not be checked or whose current listings were incomplete. Put this before the final paragraph.
5. **Top five to check:** The **last paragraph of the report** ranks up to five events from the newly found section and briefly says why each is worth checking. If fewer than five are new, rank those available; if none are new, say that there are no new picks.

Each discovered event entry has a stable **code**, linked **name**, **two-sentence description**, **host**, **date and time**, **location**, **conflict flag**, **quality score**, and **rarity score**. The linked name points to the current organizer listing when available. Do not add separate fields for price, eligibility, or registration; mention a material constraint in the description. For a later event included because of an earlier deadline, show both the deadline and event date in the date/time field.

## Conflicts and classes

Check reported opportunities and selected signups against busy events on the user's **primary Google Calendar**; ignore the US holidays calendar. Also check conflicts among multiple selected codes. Flag direct overlaps and unrealistic travel transitions. A matching calendar entry alone does not prove the user registered; the user's code reply is the signup source of truth. Avoid creating a duplicate calendar event.

Use this class timetable in Eastern Time for class-overlap warnings:

| Day | Time | Class |
| --- | --- | --- |
| Monday | 8:30–9:45 a.m. | MATH 221D |
| Monday | 10:05–11:20 a.m. | ECON 101CCD |
| Tuesday | 10:05–11:20 a.m. | PHYS 161D |
| Tuesday | 12:00–2:00 p.m. | PHYS 164L lab |
| Wednesday | 8:30–9:45 a.m. | MATH 221D |
| Wednesday | 10:05–11:20 a.m. | ECON 101CCD |
| Wednesday | 3:30–5:30 p.m. | PHYS 161D section |
| Thursday | 8:45–9:35 a.m. | ECON 101CCD discussion |
| Thursday | 10:05–11:20 a.m. | PHYS 161D |
| Friday | 8:30–9:45 a.m. | MATH 221D discussion |
| Friday | 10:05–11:20 a.m. | ECON 101CCD |

The [Duke Registrar's Fall 2026 calendar](https://registrar.duke.edu/2026-2027-academic-calendar/) says fall break starts October 9 at 7 p.m. and classes resume October 14; Thanksgiving recess starts November 24 at 10:30 p.m. and undergraduate classes resume November 30; undergraduate classes end December 4. Do not issue routine class warnings during those breaks or after December 4. Do not assume this timetable covers exams or one-off class changes.

Mention a class overlap when an event is first reported. If the user later signs up for it, identify the affected class again, then add the event without a class-versus-event comparison. A class overlap does not enter the calendar-conflict choice flow, even if the class also appears on Google Calendar.

## When the user replies with signup codes

1. Resolve each code to its event; for a recurring series, resolve the specific occurrence date. Recheck current organizer details and Google Calendar before writing. If the start or end time needed for a calendar entry is unknown, ask for the missing detail.
2. If there are **no non-class conflicts**, add all selected events to the user's primary Google Calendar and update `Upcoming_Signups.md`. Create personal events without guests or video links. Confirm each calendar write and avoid duplicates.
3. If non-class conflicts exist, report the event names, purpose, overlapping hours and transfer issues, then retain all requested selections under the standing keep-overlaps preference. Keep existing commitments unless the user explicitly requests replacement. Missing scheduling details still require clarification.
4. If a selected event overlaps a class, simply name the class and time; it does not block the calendar additions once other conflicts are resolved.

## First-run and quality checks

The first scheduled report is a live source pass, not a claim that the September 25 access audit still holds. Check the calendar connection and current organizer pages afresh. If a source or calendar is unavailable, save the report with a clear gap note and avoid asserting that a signup or conflict check succeeded. Before finishing each run, verify that the report file exists, older reports remain intact, signup entries are future-only, event codes are stable, and the final paragraph contains the top-five ranking.
