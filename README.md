# VGX Skills

> © 2026 VGX Global Consulting (OPC) Pvt Ltd. All rights reserved.

Claude Code skills by VGX Global Consulting. Install once, use across every project.

---

## Install

### Mac / Linux

```bash
curl -fsSL https://raw.githubusercontent.com/VGXDigital/vgx-skills/main/install.sh | bash
```

### Windows

Open PowerShell and paste:

```powershell
irm https://raw.githubusercontent.com/VGXDigital/vgx-skills/main/install.ps1 | iex
```

No git required — the script downloads the current skills straight from GitHub and installs them.

Restart Claude Code after install (or reload the VS Code window).

### Claude Desktop app (claude.ai app)

The desktop app uses a different Skills mechanism than Claude Code — no `~/.claude/skills/` folder, no auto-pickup from disk. Skills are uploaded as a `.zip` through the UI.

1. Download the skill zip: [`dist/vgx-pfix.zip`](https://github.com/VGXDigital/vgx-skills/raw/main/dist/vgx-pfix.zip)
2. In the desktop app: **Settings → Capabilities → Skills → Upload skill** → select the zip
3. No restart needed — the skill is available in your next chat/Project

Zips are rebuilt automatically whenever a skill changes (see `.github/workflows/build-zips.yml`). Re-download and re-upload to update.

---

## Updating

The installer overwrites existing skills — just re-run the same one-liner from above.

---

## Skills

| Skill | Invoke | What it does |
|---|---|---|
| `vgx-pfix` | `/vgx-pfix` or *"fix my prompt"* | Diagnoses a developer prompt against the 5-Part Formula. Scores each part (Context, Existing Code, Request, Constraints, Output Format), flags the 10 prompting traps, gives a verdict, and rewrites the prompt to fix every issue. |

---

## How it works

Skills install to `~/.claude/skills/` on Mac/Linux and `%USERPROFILE%\.claude\skills\` on Windows. Claude Code picks them up automatically — no config needed.

Each skill is a single `SKILL.md` file. To inspect what a skill does before running it:

```
~/.claude/skills/vgx-pfix/SKILL.md
```

---

## For course instructors

This repo is the distribution point for VGX masterclass skills. To add a new skill:

1. Create `skills/<skill-name>/SKILL.md` (and any reference files it needs)
2. Add a `mkdir`/`curl` (or `New-Item`/`Invoke-WebRequest`) line per file to install.sh and install.ps1
3. Add a row to the Skills table above
4. Commit and push — participants re-run the installer to get it

Skills are scoped to the user's machine (global install), so they work in any project the participant opens in Claude Code.
