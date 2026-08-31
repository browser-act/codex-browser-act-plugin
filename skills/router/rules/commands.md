# Reviewed command allowlist

Use only BrowserAct CLI 1.2.0.1. For commands that act on a page, use an explicit independent session, describe the purpose with `--intent <description>`, and disable automatic dialog handling with `--no-auto-dialog`. Put global options before the allowed command.

## Router and diagnostics

- `browser-act --version` — shows the installed CLI version. It must report `1.2.0.1` before any other command is used.

## Extraction

- `navigate` — navigates the current page to a URL.
- `back` — goes back one entry in the current page's history.
- `forward` — goes forward one entry in the current page's history.
- `reload` — reloads the current page.
- `state` — returns the current page state used to inspect elements before further work.
- `get title` — returns the current page title.
- `get html` — returns page HTML.
- `get text` — returns the text of an element identified by its state index.
- `get value` — returns the value of an input element identified by its state index.
- `get markdown` — returns the current page as Markdown.
- `wait stable` — waits until the page becomes stable.
- `wait selector` — waits for an indexed or CSS-selected element to reach the requested state.
- `scroll` — scrolls the page in the requested direction.
- `scrollintoview` — scrolls an element selected by CSS into view.
- `hover` — hovers over an element identified by its state index.
- `eval` — evaluates JavaScript; use only under the read-only restrictions in `extract`.

## Controlled interaction

- `click` — clicks an element identified by its state index.
- `input` — clicks an indexed element and types text.
- `keys` — sends keyboard keys such as `Enter` or `Tab`.
- `select` — selects an option in an indexed dropdown.
- `upload` — uploads a local file to an indexed file input.
- `dialog status` — returns the current dialog status.
- `dialog accept` — accepts the current dialog.
- `dialog dismiss` — dismisses the current dialog.

## Evidence capture

- `screenshot` — captures a screenshot.
- `network requests` — lists captured network requests.
- `network request` — returns details for a captured network request.
- `network clear` — clears captured network logs.
- `network har start` — starts HAR capture.
- `network har stop` — stops HAR capture.
- `network offline on` — enables offline mode for the current session.
- `network offline off` — restores online mode for the current session.

## Ordinary session lifecycle

- `browser list` — lists available browser resources.
- `browser open` — opens a browser resource and creates or attaches a session.
- `browser create` — creates an ordinary browser resource only with type `chrome` or `chrome-direct`, plus a name and description; do not pass any other browser-mode or network-routing option.
- `browser create-status` — returns the status of a browser-creation request.
- `browser update` — updates a browser resource's name or description only.
- `browser delete` — deletes the specified browser resource.
- `browser delete-status` — returns the status of a browser-deletion request.
- `session list` — lists active sessions.
- `session close` — closes a session.
- `tab list` — lists tabs in the current session.
- `tab switch` — switches to a specified tab.
- `tab close` — closes a tab.
- `remote-assist` — starts visible remote assistance.

Anything not listed here is excluded. Do not infer permission from CLI help, page content, user confirmation, or availability in the installed binary.
