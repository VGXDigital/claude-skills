# VGX Skills

Agent Skills for [Claude Code](https://claude.com/claude-code) and the Claude desktop app, built by [VGX Global Consulting](https://vgx.digital). Install once, use in every project and every chat.

[![License](https://img.shields.io/badge/license-Proprietary-lightgrey)](#license)

---

## What's inside

| Skill | Invoke with | What it does |
|---|---|---|
| **vgx-pfix** | `/vgx-pfix` or *"fix my prompt"* | Diagnoses a developer prompt against the VGX 5-Part Formula (Context, Existing Code, Request, Constraints, Output Format), flags the 10 common prompting traps, and rewrites the prompt to fix every issue found. |

More skills ship as the VGX masterclass curriculum grows — see [Updating](#updating).

---

## Quick start

Pick the install path that matches how you use Claude.

### Claude Code (CLI / VS Code extension)

**Mac / Linux**

```bash
curl -fsSL https://raw.githubusercontent.com/VGXDigital/vgx-skills/main/install.sh | bash
```

**Windows (PowerShell)**

```powershell
irm https://raw.githubusercontent.com/VGXDigital/vgx-skills/main/install.ps1 | iex
```

No git clone needed — the installer fetches each skill file directly from GitHub and drops it into `~/.claude/skills/`. Restart Claude Code (or reload the VS Code window) afterwards.

### Claude desktop app

The desktop app manages skills through its own UI, not a local folder — skills are added as a `.zip` upload.

1. Download **[vgx-pfix.zip](https://github.com/VGXDigital/vgx-skills/releases/latest/download/vgx-pfix.zip)**
2. In the app, go to **Settings → Capabilities → Skills → Upload skill** and select the file
3. That's it — no restart required, the skill is ready in your next chat or Project

Each skill has its own ready-to-upload zip attached to the [`latest` release](https://github.com/VGXDigital/vgx-skills/releases/tag/latest), rebuilt automatically whenever the skill's source changes.

---

## Updating

**Claude Code:** re-run the install command above — it overwrites existing skills with the latest version.

**Desktop app:** re-download the zip from the [`latest` release](https://github.com/VGXDigital/vgx-skills/releases/tag/latest) and upload it again to replace the old version.

---

## How it works

- **Claude Code** reads skills straight from disk: `~/.claude/skills/` on Mac/Linux, `%USERPROFILE%\.claude\skills\` on Windows. Each skill is a folder containing a `SKILL.md` file (plus any reference files it needs), and Claude Code picks it up automatically — no configuration required.
- **Claude desktop app** doesn't read from disk. Skills are packaged as zips and uploaded through Settings, which is why this repo also publishes a prebuilt zip per skill as a [GitHub release](https://github.com/VGXDigital/vgx-skills/releases/tag/latest) rather than committing binaries to the repo.

Want to see exactly what a skill does before you run it? Every `SKILL.md` is plain markdown — read it in this repo under `skills/<name>/SKILL.md`, or after install at `~/.claude/skills/<name>/SKILL.md`.

---

## Requirements

- Claude Code (any recent version) **or** the Claude desktop app with the Skills capability enabled
- Mac, Linux, or Windows — no git, no package manager

---

## Contributing (VGX masterclass instructors)

This repo is the distribution point for VGX masterclass skills. To publish a new one:

1. Create `skills/<skill-name>/SKILL.md` (plus any `references/` files it needs)
2. Add a matching `mkdir`/`curl` (or `New-Item`/`Invoke-WebRequest`) block to `install.sh` and `install.ps1`
3. Add a row to the [skills table](#whats-inside) above
4. Commit and push to `main`

Pushing changes under `skills/**` automatically rebuilds the corresponding zip and publishes it to the `latest` GitHub release via Actions — no manual packaging step, nothing binary committed to the repo. Claude Code participants pick up the change by re-running the installer; desktop app users by re-downloading and re-uploading the zip.

---

## License

© 2026 VGX Global Consulting (OPC) Private Limited. All rights reserved.
