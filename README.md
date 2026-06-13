# dotfiles

Managed by [chezmoi](https://chezmoi.io).

## Quick start

```bash
chezmoi init --apply <repo>
```

## Contents

- `dot_hermes/` -- Hermes Agent config
  - `config.yaml` -- full hermes config (no secrets)
  - `SOUL.md.tmpl` -- host-specific SOUL (template)
  - `env.tmpl` -- secrets template (chezmoi `{{ env }}`)
- `.chezmoitemplates/` -- shared template fragments
  - `soul-telsha.md` -- Operator 21O (Telsha)
  - `soul-ishtar.md` -- Operator 17O (Ishtar)
  - `soul-kaltashar.md` -- Operator 11O (Kaltashar)

## Host-specific SOUL

`SOUL.md.tmpl` selects the correct operator profile by hostname:

| Host      | Operator | Archetype                     |
| --------- | -------- | ----------------------------- |
| telsha    | 21O      | The Strict Guardian (ISTJ)    |
| ishtar    | 17O      | The Flight-Bay Analyst (ESFJ) |
| kaltashar | 11O      | The Logistics Anchor (ISTJ)   |

## Secrets

Secrets are stored as environment variables and injected via chezmoi templates.
Required env vars:

- `DISCORD_BOT_TOKEN`
- `DISCORD_ALLOWED_USERS`
- `MATRIX_HOMESERVER`
- `API_SERVER_KEY`
- `GOOGLE_API_KEY`
- `GITHUB_TOKEN`
- `DISCORD_HOME_CHANNEL`
- `OPENROUTER_API_KEY`
