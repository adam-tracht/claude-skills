# Claude Skills

Personal Claude Code skills: be-a-human, caveman, council, obsidian-vault.

## Skills

### be-a-human
Removes AI writing patterns from prose. Invoke with `/be-a-human` or paste the text you want cleaned. Covers AI vocabulary, copula avoidance, formulaic structures, formatting tells, filler, and more. Includes a full pattern catalog in `references/patterns.md`.

### caveman
Ultra-compressed communication mode. Cuts all filler and responds in minimal, direct language.

### council
Multi-perspective deliberation using parallel subagents. Each councilor (Skeptic, Advocate, Pragmatist, First-Principles, Minimalist) responds independently, a neutral panel evaluates, and a Chairman synthesizes. Good for decisions where you want genuine push-back before committing.

### obsidian-vault
Search, read, create, and manage notes in an Obsidian vault. Supports the Local REST API plugin (preferred) with filesystem fallback. Requires device-specific configuration after install — see the note at the bottom.

---

## Installation

### Claude Code — manual (simplest)

Skills live at `~/.claude/skills/<skill-name>/SKILL.md`. To install a skill from this repo, create the directory and download the file:

```bash
mkdir -p ~/.claude/skills/be-a-human
curl -o ~/.claude/skills/be-a-human/SKILL.md \
  https://raw.githubusercontent.com/adam-tracht/claude-skills/main/be-a-human/skills/be-a-human/SKILL.md

# be-a-human also has a reference file:
mkdir -p ~/.claude/skills/be-a-human/references
curl -o ~/.claude/skills/be-a-human/references/patterns.md \
  https://raw.githubusercontent.com/adam-tracht/claude-skills/main/be-a-human/skills/be-a-human/references/patterns.md
```

No JSON files to edit, no CLI needed. Claude Code watches `~/.claude/skills/` automatically — the skill is available immediately in new sessions.

Invoke with `/skill-name` or describe your task and Claude picks it up automatically based on the skill description.

### Claude Code — marketplace (faster for installing multiple skills)

This repo is registered as a plugin marketplace, which handles fetching and placement automatically:

```bash
# Register the marketplace (one-time)
claude plugins marketplace add adam-tracht/claude-skills

# Install whichever skills you want
claude plugins install be-a-human@adam-tracht-skills
claude plugins install caveman@adam-tracht-skills
claude plugins install council@adam-tracht-skills
claude plugins install obsidian-vault@adam-tracht-skills
```

### Claude Code — project-level skills

To make a skill available only within a specific project, put it in `.claude/skills/` inside that project and commit it:

```
your-project/
└── .claude/
    └── skills/
        └── my-skill/
            └── SKILL.md
```

### Claude.ai (web)

1. Download the `SKILL.md` file for the skill you want
2. Create a folder with the skill name (e.g. `be-a-human`)
3. Put `SKILL.md` inside it and zip the folder
4. In Claude.ai: **Customize > Skills > + Create skill > Upload a skill**
5. Toggle the skill on after upload

The folder name inside the zip must match the `name` field in the SKILL.md frontmatter. A flat zip with SKILL.md at the root won't work.

```
be-a-human.zip
└── be-a-human/
    └── SKILL.md
```

**Prerequisite:** Settings > Capabilities > **Code execution and file creation** must be enabled.

---

## SKILL.md frontmatter

`description` is recommended so Claude knows when to invoke the skill automatically. `name` defaults to the directory name if omitted.

```yaml
---
name: skill-name        # optional — defaults to directory name
description: "..."      # recommended — tells Claude when to use this skill
---
```

---

## Note on obsidian-vault

The `obsidian-vault` skill connects to Obsidian's Local REST API plugin. The auth token and port are generated per device, so the version in this repo ships with a placeholder token. After installing, open the SKILL.md and replace `YOUR_TOKEN_HERE` with your actual token.

For the manual install, that file is at `~/.claude/skills/obsidian-vault/SKILL.md`.
For the marketplace install, it's at `~/.claude/plugins/cache/adam-tracht-skills/obsidian-vault/<version>/skills/obsidian-vault/SKILL.md`.

Find your token in Obsidian: **Settings > Local REST API**.
