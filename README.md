# BrowserAct Codex plugin

Codex Skills for browser automation and reusable website-skill generation with the [Browser Act CLI](https://pypi.org/project/browser-act-cli/).

The repository root is the plugin root. Its `skills/` directory contains exactly the two Skills below.

## Skills

| Skill | Purpose |
|---|---|
| `browser-act` | Entry point for BrowserAct browser automation: rendered content, interaction, screenshots, network capture, and browser/session workflows. |
| `browser-act-skill-forge` | Explores a website's implementation path, then generates and verifies reusable, site-specific Skill packages. |

`browser-act` is a discovery stub. After it loads, retrieve the matching workflow instructions from the installed CLI:

```bash
browser-act get-skills core --skill-version 2.0.2
```

`browser-act-skill-forge` is for reusable work rather than one-off extraction. Its `references/` directory is part of the Skill and defines the exploration and output format used when generating site-specific packages.

## Requirements

- Python 3.12+
- [`uv`](https://docs.astral.sh/uv/)
- `browser-act-cli`

Install the CLI when it is not already available:

```powershell
uv tool install browser-act-cli --python 3.12
```

The skill-forge workflow also checks that its API Key is configured before exploring a site. Follow the workflow guidance if configuration is required.

## Repository contents

The plugin's runtime content is `.codex-plugin/`, `assets/`, `skills/`, `README.md`, and `LICENSE`. This repository does not include a local Marketplace configuration, packaging script, or validation script.

## License

MIT — see [LICENSE](LICENSE).
