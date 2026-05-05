# Claude Skills

Personal Claude Code skills.

## Skills

### deslop
Removes AI writing patterns from prose. Invoke with `/deslop` or paste the text you want cleaned. Covers AI vocabulary, copula avoidance, formulaic structures, formatting tells, filler, and more. Includes a full pattern catalog in `references/patterns.md`.

### caveman
Ultra-compressed communication mode. Cuts all filler and responds in minimal, direct language.

### council
Multi-perspective deliberation using parallel subagents. Each councilor (Skeptic, Advocate, Pragmatist, First-Principles, Minimalist) responds independently, a neutral panel evaluates, and a Chairman synthesizes. Good for decisions where you want genuine push-back before committing.

### obsidian-vault
Search, read, create, and manage notes in an Obsidian vault. Supports the Local REST API plugin (preferred) with filesystem fallback. Requires device-specific configuration after install — see the note below.

---

## Using a skill from any repo

If you find a `SKILL.md` file anywhere (this repo or someone else's), here's how to use it.

### Claude.ai (web)

1. Create a folder named after the skill (lowercase, hyphens only — e.g. `deslop`)
2. Put `SKILL.md` inside it
3. Zip the folder
4. In Claude.ai: **Customize > Skills > + Create skill > Upload a skill**
5. Toggle the skill on after it appears in your list

The folder name inside the zip must match the `name` field in the SKILL.md frontmatter. A flat zip with SKILL.md at the root won't work.

```
deslop.zip
└── deslop/
    └── SKILL.md
```

**Prerequisite:** Settings > Capabilities > **Code execution and file creation** must be enabled.

### Claude Code — quick test (session only)

```bash
claude --plugin-dir ./deslop
```

Loads the skill for that session without installing anything permanently.

### Claude Code — permanent install from this repo

This repo is registered as a marketplace:

```bash
# Register the marketplace (one-time)
claude plugins marketplace add adam-tracht/claude-skills

# Install individual skills
claude plugins install deslop@adam-tracht-skills
claude plugins install caveman@adam-tracht-skills
claude plugins install council@adam-tracht-skills
claude plugins install obsidian-vault@adam-tracht-skills
```

### Claude Code — permanent install from any other repo

If the repo contains a single plugin with a `.claude-plugin/plugin.json` at its root:

```bash
claude plugins install https://github.com/owner/repo
```

If it's just a folder of SKILL.md files with no plugin structure, you'll need to add the folder as a local marketplace first:

```bash
claude plugins marketplace add ./path/to/local/folder
claude plugins install skill-name@folder-name
```

---

## Slash commands

After installing a skill in Claude Code, you can optionally add a slash command so you can invoke it with `/skill-name`. Create a file at `~/.claude/commands/<skill-name>.md`:

```
Invoke the `<skill-name>:<skill-name>` skill now. $ARGUMENTS
```

---

## SKILL.md frontmatter

Every `SKILL.md` needs a frontmatter block or it won't be recognized:

```yaml
---
name: skill-name       # required — kebab-case, max 64 chars
description: "..."     # required — max 200 chars
---
```

---

## Note on obsidian-vault

The `obsidian-vault` skill connects to Obsidian's Local REST API plugin. The auth token and port are generated per device, so the version in this repo ships with a placeholder token. After installing, patch your token and port into the installed SKILL.md:

```
~/.claude/plugins/cache/adam-tracht-skills/obsidian-vault/<version>/skills/obsidian-vault/SKILL.md
```

Find your token in Obsidian: **Settings > Local REST API**.
