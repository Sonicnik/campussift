# EventSourcer browser connection

## Verified local setup — October 23, 2026

Playwright MCP `@playwright/mcp@0.0.83` is installed in `.eventsourcer/browser-runtime/`. The lockfile pins the dependency tree. Codex has an enabled STDIO server named `eventsourcer_browser`, registered in the user's configuration. It launches the installed package through the local Node executable, with Chrome and a separate persistent profile at `.eventsourcer/browser-profile/`. Browser output goes to `.eventsourcer/browser-output/`. Page-provided WebMCP tools are disabled.

The existing browser profile used by other tools was not attached or copied. The new profile is not signed into any source. Browser profile data and output are excluded from Git. Treat profile data as private; never include it in a release archive, even if an archive command ignores `.gitignore`.

## Verification evidence

An MCP client initialized the server and discovered 25 tools. Through MCP, it navigated to `https://calendar.duke.edu/`, extracted three live event links, and captured a screenshot. A non-secret local-storage marker persisted after closing and reopening the browser; the marker was removed afterward. This verifies profile persistence, not successful authenticated access.

- Machine-readable results: `../.eventsourcer/playwright-smoke.json`
- Screenshot: `../.eventsourcer/browser-output/public-calendar.png`
- Codex registration was read back with `codex mcp get eventsourcer_browser`.

The tools were not added to the already-running chat's tool catalog. Start a new chat in this project (reload the app if needed), then confirm that `eventsourcer_browser` tools are available before discovery. Configuration alone is not proof that a new chat successfully connected.

## Using the connection

Use the `eventsourcer_browser` tools for EventSourcer browsing when available. Open the chosen source in this dedicated profile, let the user complete sign-in and multifactor authentication directly in Chrome, then verify that an event listing is readable. Record source access and its check date in the report. Existing Chrome logins do not transfer automatically. If tools or a source are unavailable, report the gap; use another authorized browser only with its actual access state clearly identified.

Run only one browser instance against this profile at a time. Discovery reads event information; registration, group joining, messaging, and calendar writes remain separate user-authorized actions. No university mailbox access is part of this setup.

## Packaging for other users

A bare `SKILL.md` installation does not register an MCP server. For a supported agent with plugin packaging, bundle the skills with MCP configuration in a plugin. For other clients, supply their supported configuration or an explicit setup command. Users still need Node, a supported browser, and manual login for private sources. Publish compatibility only after testing it.

The portable launch command can use `npx -y @playwright/mcp@0.0.83 --browser chrome --user-data-dir <private-absolute-profile-path> --output-dir <private-absolute-output-path> --no-webmcp`. The installer must resolve paths for that user instead of shipping this Mac's paths. The tested local registration uses the already-installed package so launching it requires no fresh package download.

References: [Playwright MCP](https://github.com/microsoft/playwright-mcp), [Codex MCP configuration](https://developers.openai.com/codex/mcp).
