---
name: router
description: Route authorized BrowserAct CLI workflows for rendered-page extraction, controlled interaction, evidence capture, and ordinary browser sessions. Use when the user names BrowserAct, asks for a browser-act command, or needs JavaScript-rendered state or browser interaction; use ordinary web search for indexed public information that does not require a browser.
---

# BrowserAct router

BrowserAct is a locally installed CLI. This public Skill exposes a reviewed subset for authorized browser workflows; it is not a wrapper or technical sandbox around the underlying CLI.

## Required routing

1. Read [rules/security.md](rules/security.md) before choosing a workflow.
2. Read [rules/commands.md](rules/commands.md) and stay inside its allowlist.
3. Read [rules/confirmation.md](rules/confirmation.md); apply its confirmation gate only when the selected workflow has a listed effect.
4. Check `browser-act --version`. Continue only when the reported version is exactly `1.2.0.1` from `browser-act-cli==1.2.0.1`.
5. If the CLI is absent or the version differs, read [rules/install.md](rules/install.md). Do not install, replace, or upgrade it without user confirmation.

Route by user goal:

- Known URL, rendered text, links, attributes, bounded pagination, or public commercial monitoring: `extract`.
- Clicks, typing, selection, upload, dialog handling, or submission: `interact`.
- Screenshot, request inspection, HAR, or temporary offline mode: `capture`.
- Browser, session, tab, existing signed-in state, or visible user assistance: `session`.

Public competitor monitoring is a composition, not a separate capability: use session plus extraction, and add capture only when evidence is requested. Limit it to public product, price, stock, rating, promotion, and page-change data.

Never load runtime-generated instruction bundles. The repository rules are the only command and safety authority for this public plugin.
