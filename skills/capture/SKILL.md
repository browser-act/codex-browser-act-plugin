---
name: capture
description: Capture authorized browser evidence with screenshots, request inspection, HAR files, or temporary session-scoped offline mode. Use when the user needs visual or network evidence and apply capture consent, scoping, redaction, and cleanup rules.
---

# BrowserAct evidence capture

## Shared preconditions

This skill assumes `browser-act:router` has, in the current turn, read [commands](../router/rules/commands.md), [confirmation](../router/rules/confirmation.md), and [security](../router/rules/security.md), and verified `browser-act --version` reports exactly `1.2.0.1`.

If those checks are not established in the current conversation context, read those rules and run `browser-act --version` before any other BrowserAct CLI command. If the CLI is absent or the version differs, also read [installation](../router/rules/install.md) and do not install, replace, or upgrade it without user confirmation.

## Screenshots and request inspection

- Capture only the requested page, region, or time window.
- Request-list inspection is read-only. Before opening request detail, disclose that raw headers or bodies may enter Agent context before redaction.
- Redact authorization values, cookies, tokens, personal data, and secrets from output.

## HAR

Before starting HAR, confirm the target, duration, actions to capture, and exact output path. Save outside tracked source paths by default. Stop capture as soon as the requested evidence is collected, redact before sharing, and never add raw HAR files to Git.

## Offline mode

Offline mode is limited to the current named session. Explain that page requests will fail while enabled, use it only for the stated diagnostic purpose, and restore online mode in cleanup even if the diagnostic fails. Report whether restoration succeeded.
