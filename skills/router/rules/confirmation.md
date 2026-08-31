# Action-time confirmation

Confirmation is required immediately before an action when the exact target and effect are known. Explain what will happen, where, and what data is involved.

Require confirmation for:

- installing, replacing, or changing the CLI version;
- creating, renaming, or deleting a browser resource;
- restarting an ordinary local browser;
- uploading a file, submitting a form, publishing, sending, purchasing, saving, or any click/key/dialog action that can change external state;
- starting HAR capture, including its target scope and output path;
- starting visible remote assistance;
- closing a tab or session when unsaved state may be lost.

No extra confirmation is required for authorized read-only navigation, extraction, screenshots, or request-list inspection unless the user requested a narrower gate.

Before request-detail or HAR capture, disclose that raw network data can enter the Agent context before redaction. Redact authorization headers, cookies, tokens, personal fields, and secrets from summaries and saved artifacts.

Do not ask for confirmation for excluded behavior. Refuse or stop instead.
