---
name: obsidian-vault
description: Search, read, create, and manage notes in the Obsidian vault (Second Brain). Use when the user references notes, vault content, or needs to find/create/update anything in Obsidian.
---

# Obsidian Vault

The Second Brain vault is the canonical source of truth for who Adam is, agent instructions, project context, and durable memory.

## Access

Vault: `/Users/adamtracht/Documents/Second Brain`

### REST API (requires Local REST API plugin installed and Obsidian running)

> **Note:** The token and port below are device-specific. Each Obsidian installation generates its own token (find it in Settings > Local REST API). Port 27125 is set here because 27124 was occupied on this machine — check the plugin settings if the default differs on another device.

```bash
# List vault root
curl -sk https://localhost:27125/vault/ \
  -H "Authorization: Bearer YOUR_TOKEN_HERE"

# Read a note
curl -sk https://localhost:27125/vault/{path} \
  -H "Authorization: Bearer YOUR_TOKEN_HERE"

# Create/update a note
curl -sk -X PUT https://localhost:27125/vault/{path} \
  -H "Authorization: Bearer YOUR_TOKEN_HERE" \
  -H "Content-Type: text/markdown" \
  -d 'Note content here'

# Delete a note
curl -sk -X DELETE https://localhost:27125/vault/{path} \
  -H "Authorization: Bearer YOUR_TOKEN_HERE"
```

HTTPS only, self-signed cert (always use `-k`). Falls back to filesystem if API times out.

### Direct filesystem (fallback)

```bash
# Read
cat "/Users/adamtracht/Documents/Second Brain/{path}"

# Search by filename
find "/Users/adamtracht/Documents/Second Brain" -name "*.md" | grep -i "keyword"

# Search by content
grep -rl "keyword" "/Users/adamtracht/Documents/Second Brain/" --include="*.md"
```

## Vault structure

```
Second Brain/
├── Home.md                 — Dual index (Agent Context / Newsletter)
├── README.md
├── 00-system/              — Architecture, shared instructions
│   └── instructions/       — AGENTS.shared.md, MEMORY-RULES.md, WRITING-STYLE.md
├── 02-memory/              — Memory files
│   └── daily/              — Daily notes
├── 03-people/              — Adam.md + contacts
├── 04-projects/            — Project docs
├── 08-agents/              — Agent role definitions
├── 09-adapters/            — Tool-specific configs
├── Templates/              — Note templates
├── raw/                    — Source material
│   ├── articles/
│   ├── pdfs/
│   └── transcripts/
└── scripts/                — Vault utility scripts
```

## Key files

- `03-people/Adam.md` — who Adam is (canonical user profile)
- `00-system/instructions/AGENTS.shared.md` — shared agent rules
- `00-system/instructions/MEMORY-RULES.md` — memory conventions
- `00-system/instructions/WRITING-STYLE.md` — writing voice
- `08-agents/` — per-agent role definitions

## Creating notes

1. Pick the right folder based on content type (see structure above)
2. Prefer REST API (`PUT /vault/{path}`) so Obsidian indexes immediately
3. Fall back to direct filesystem write if REST API is unavailable
4. Add `[[wikilinks]]` to related notes where appropriate

## Vault metadata

- **Vault ID:** `a795d5abee695f22`
- **Plugins:** dataview v0.5.68, smart-connections v4.3.0, obsidian-local-rest-api v3.6.1
- **Embeddings:** all-MiniLM-L6-v2 (via Smart Connections)
