# VGX Open-Source Skills Collection

Open-source [Agent Skills](https://claude.com/claude-code) by [VGX Global Consulting](https://vgx.digital), for Claude Code and the Claude desktop app. Install once, use in every project and every chat.



## Skills

### Prompt Fixer (`vgx-pfix`)

Fixes vague prompts before you send them. Invoke with `/vgx-pfix` or say *"fix my prompt"* — paste a prompt you were about to send Claude, and it tells you what's missing and hands back a better version.

**Before:**
> fix the bug in my login

**After:**
> ## Prompt Diagnosis
> - Context: MISSING — no mention of which app, stack, or where auth lives
> - Existing Code: MISSING — no file path or snippet to work from
> - Request: WEAK — "the bug" is undefined, no repro steps
> - Constraints: MISSING
> - Output Format: MISSING
>
> **Verdict: WEAK**
>
> ## Suggested Prompt
> In `src/auth/login.ts`, users with valid credentials get a 401 on the second login attempt within the same session. Reproduce by logging in, logging out, then logging in again immediately. Find the root cause and fix it — don't just add a retry. Keep the existing session-token format.

Every skill is plain markdown — read what it does before you run it, under [`skills/<name>/SKILL.md`](skills/).

---

## Install

### Claude Code (CLI / VS Code extension)

**Mac / Linux**

```bash
curl -fsSL https://raw.githubusercontent.com/VGXDigital/claude-skills/main/install.sh | bash
```

**Windows (PowerShell)**

```powershell
irm https://raw.githubusercontent.com/VGXDigital/claude-skills/main/install.ps1 | iex
```

Restart Claude Code (or reload the VS Code window) afterwards.

### Claude desktop app

1. Download the skill's zip from the [`latest` release](https://github.com/VGXDigital/claude-skills/releases/tag/latest) — e.g. [vgx-pfix.zip](https://github.com/VGXDigital/claude-skills/releases/latest/download/vgx-pfix.zip)
2. In the app, go to **Settings → Capabilities → Skills → Upload skill** and select the file

The skill is ready in your next chat or Project — no restart needed.



## Updating

**Claude Code:** re-run the install command — it overwrites installed skills with the latest version.

**Desktop app:** re-download the zip from the [`latest` release](https://github.com/VGXDigital/claude-skills/releases/tag/latest) and upload it again.



