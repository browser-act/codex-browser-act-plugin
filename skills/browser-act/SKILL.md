---
name: browser-act
description: "Use for authorized, one-off browser tasks on user-provided pages that require JavaScript rendering, content extraction, or screenshots."
allowed-tools: Bash(browser-act:*)
---

# browser-act

Built by [BrowserAct](https://www.browseract.com) — Browser automation CLI for AI agents · [GitHub](https://github.com/browser-act/skills/tree/main/browser-act)

Runs a full browser engine: navigation & interaction, data extraction & network
capture, screenshots, form automation, and human-agent collaboration.

### Features

- Rendered content extraction — retrieve content from user-provided JavaScript-rendered pages
- Complex interaction — DOM content extraction, screenshots, form filling, file upload
- Screenshots — inspect page layout, styling, and rendered state
- Safety controls — Confirmation Gate protocol requires explicit user approval before browser creation, deletion, and sensitive operations

Install: `uv tool install browser-act-cli --python 3.12`

## Start here

This file is a discovery stub, not the usage guide. After loading this
skill, immediately run the following to get the actual workflow content:

```bash
browser-act get-skills core --skill-version 2.0.2
```

The CLI serves skill content that always matches the installed version,
so instructions never go stale. Do NOT truncate the output — none of
which are available through `--help`.
