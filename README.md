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
Search, read, create, and manage notes in an Obsidian vault. Supports the Local REST API plugin (preferred) with filesystem fallback. Requires device-specific configuration after install (see SKILL.md for details).

---

## Installation

### Claude Code (CLI)

This repo is a registered marketplace. Install via the CLI:

```bash
# Register the marketplace (one-time)
claude plugins marketplace add adam-tracht/claude-skills

# Install individual skills
claude plugins install deslop@adam-tracht-skills
claude plugins install caveman@adam-tracht-skills
claude plugins install council@adam-tracht-skills
claude plugins install obsidian-vault@adam-tracht-skills
```

Restart Claude Code after installing. Skills are available in new sessions immediately.

**Slash commands** (optional): add a file at `~/.claude/commands/<skill-name>.md` to invoke a skill with `/skill-name`:

```
Invoke the `<skill-name>:<skill-name>` skill now. $ARGUMENTS
```

**Note on obsidian-vault:** after installing, patch your device-specific auth token and port into the installed SKILL.md at `~/.claude/plugins/cache/adam-tracht-skills/obsidian-vault/<version>/skills/obsidian-vault/SKILL.md`. The repo ships with a placeholder token.

### Claude chat (claude.ai)

Chat uses zip upload rather than the filesystem. The zip must have the skill folder at the root:

```bash
cd <skill-name>/skills && zip -r ~/Desktop/<skill-name>.zip <skill-name>/
```

The archive should look like:
```
<skill-name>/
├── SKILL.md
└── references/   # if present
```

Then in claude.ai: **Settings > Customize > Skills > Upload**.
