---
name: session
description: Use when managing authorized ordinary BrowserAct browsers, sessions, or tabs, including existing signed-in state and visible remote assistance. Excludes private or stealth modes, profile or cookie transfer, proxy settings, and service authentication.
---

# BrowserAct session management

## Shared preconditions

This skill assumes `browser-act:router` has, in the current turn, read [commands](../router/rules/commands.md), [confirmation](../router/rules/confirmation.md), and [security](../router/rules/security.md), and verified `browser-act --version` reports exactly `1.2.0.1`.

If those checks are not established in the current conversation context, read those rules and run `browser-act --version` before any other BrowserAct CLI command. If the CLI is absent or the version differs, also read [installation](../router/rules/install.md) and do not install, replace, or upgrade it without user confirmation.

## Workflow

1. Prefer an existing authorized ordinary browser and list state before creating anything.
2. Create only `chrome` or `chrome-direct` resources. Show type, name, description, purpose, and any restart impact, then confirm creation.
3. Browser updates are limited to name or description and require separate confirmation. Deletion requires confirmation with the exact browser identifier.
4. Tabs and sessions may be listed and switched read-only. Confirm close when unsaved state may be lost.
5. Use existing signed-in state without exporting it. If authentication is required, offer visible remote assistance after confirmation; the user enters credentials directly in the browser.

Never request credentials in chat or transfer cookies, profiles, tokens, or authentication headers. Stop if the requested session depends on an excluded browser mode, network routing feature, access-control bypass, or security-challenge handling.
