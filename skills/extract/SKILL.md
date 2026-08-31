---
name: extract
description: Use when extracting authorized content from known JavaScript-rendered pages, including text, links, attributes, bounded pagination, or public commercial monitoring. Do not use for general web search, access-restricted content, or external writes.
---

# BrowserAct extraction

## Shared preconditions

This skill assumes `browser-act:router` has, in the current turn, read [commands](../router/rules/commands.md), [confirmation](../router/rules/confirmation.md), and [security](../router/rules/security.md), and verified `browser-act --version` reports exactly `1.2.0.1`.

If those checks are not established in the current conversation context, read those rules and run `browser-act --version` before any other BrowserAct CLI command. If the CLI is absent or the version differs, also read [installation](../router/rules/install.md) and do not install, replace, or upgrade it without user confirmation.

## Workflow

1. Confirm the target URL, requested fields, authorization basis, and a finite page/item limit. Default to the smallest useful scope.
2. Use an existing independent ordinary session or obtain one through the session Skill.
3. Navigate, inspect `state`, and prefer `get markdown`, `get text`, or selected HTML over full-page output.
4. For pagination or scrolling, stop at the requested bound, repeated content, access restriction, or rate-limit signal.
5. Return structured results with source URLs and distinguish missing values from inferred values.

For competitor monitoring, collect only public commercial facts such as product, price, inventory, rating, promotion, and page changes. Do not infer or enrich personal identity, behavior, or sensitive characteristics.

## Read-only JavaScript

Use `eval` only when allowed extraction commands cannot obtain the requested value. Before execution, show the exact script and explain why it is read-only.

Allowed JavaScript may read DOM text, attributes, computed styles, element geometry, or perform pure in-memory calculation. It must not read cookies, web storage, secrets, clipboard, or authentication state; initiate network calls; construct dynamic code; dispatch events; submit forms; navigate; or persistently mutate page or browser state. If the effect is ambiguous, stop.
