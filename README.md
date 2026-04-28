# Claude Skills

Personal Claude Code skills.

## Skills

### deslop
Removes AI writing patterns from prose. Invoke with `/deslop` or paste the condensed prompt into any AI chat. Covers AI vocabulary, copula avoidance, formulaic structures, formatting tells, filler, and more. Includes a full pattern catalog in `references/patterns.md`.

### caveman
Ultra-compressed communication mode. Cuts all filler and responds in minimal, direct language.

### council
Multi-perspective deliberation using parallel subagents. Each councilor (Skeptic, Advocate, Pragmatist, First-Principles, Minimalist) responds independently, a neutral panel evaluates, and a Chairman synthesizes. Good for decisions where you want genuine push-back before committing.

## Installation

Each skill follows the standard Claude plugin structure. To install locally:

1. Copy the skill folder to `~/.claude/plugins/cache/local/<skill-name>/`
2. Add an entry to `~/.claude/plugins/installed_plugins.json`
3. Add `"<skill-name>@local": true` to `enabledPlugins` in `~/.claude/settings.json`

Both registration files are required or the skill won't appear.
