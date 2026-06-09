---
name: plan
description: "Scope a feature/bug-sweep/project, discuss the approach, and write a phased plan doc that lives in the repo and is resumed across sessions. Use when the user wants to plan or scope work, write a PRD/spec, break work into phases or sprints, decide between approaches before building, or asks 'what's left' from / wants to update an existing plan doc."
trigger: /plan
---

# /plan

A planning loop: a short conceptual discussion, one recommendation, the user's terse go, then a phased markdown plan that lives in `plans/` at the repo root and gets resumed and updated across sessions. NOT a brainstorm-heavy, PR-bound, ceremony-first process. Scope, recommend, wait, persist, execute, keep current.

## The one hard rule: discuss before you build, persist only on his go

When invoked to create a plan, do NOT write any file yet. First, in chat:

1. **Scope it.** Restate the actual thing being solved (diagnose what he flagged, not an adjacent problem). Ask only the questions you genuinely can't resolve from the codebase or context.
2. **Surface the real tradeoffs.** Honest about cost/benefit, not a feature list. If a capability touches a third party (payment API, model provider, tool), dispatch a subagent to read the current official docs this session before claiming what's possible.
3. **Give ONE recommendation.** Lead with the structurally correct, root-cause approach. If genuinely torn between approaches, invoke `/council`.
4. **Name what gets built on approval, then stop and wait.** He approves in two or three words ("let's do it", "proceed"). Nothing gets written to disk until that comes.

Keep the whole discussion at high altitude: what each thing is, why it matters, confidence it's worth doing, and effort. No file/function/variable/table names unless he asks to go deeper. Be ruthlessly concise.

## On his go: write the plan doc

Location: a `plans/` directory at the repo root, one doc per feature/effort, kebab-case filename (e.g. `plans/video-attachments.md`). Create `plans/` if it doesn't exist.

```markdown
# <Feature / effort name>

**Goal:** <one or two sentences, conceptual: what we're solving and why it matters>
**Source:** <where this came from + date>
**Status:** In progress | Shipped | Deferred

## Status key
- ✅ Done   - 🔲 Partial   - ⬜ Not started

## Phase 1: <theme>  (priority/impact/effort: <high/med/low>)
- ⬜ **<Item title>**: <what it is and why it matters, conceptual>. Confidence: <how sure>. Effort: <S/M/L>. Lands in: <pointer to where the detail will live>.

## Phase 2: <theme>  (...)
- ⬜ ...

## Deferred / future
- ⬜ **DEFERRED: <item>**: <reason / what it's waiting on>.

## Go-live / cutover (sequence last)
- ⬜ <Any irreversible or production-cutover step, ordered explicitly last>
```

Doc rules: phased and grouped by priority/impact/effort, not a flat list. Conceptual + pointers, not detail (implementation facts belong in the subsystem doc). Irreversible/go-live steps sequenced explicitly last. No YAML frontmatter. No status-log prose.

## Resume across sessions

When he says "what's left from @plans/<x>.md": read it, report remaining ⬜/🔲 work grouped by phase, high altitude, concise. The plan doc plus its pointers is the source of truth. Continue from there.

## Update as work ships

After an item ships: flip its icon to ✅ and append a one-line evidence note (test name, live-verified behavior, command output). Never delete completed items; git history is the archive. Keep filing discipline: implementation facts in the subsystem doc, pending/future work in the plan's "Deferred / future" section, CLAUDE.md/README only point. Commit the doc update alongside the code (no PR; push to main on his approval).

## Execution stays orchestrated

When he green-lights building, delegate to subagents (reads and implementation), with two-stage review per task: spec compliance first, then code quality. When done, run the documentation-subagent pass and update the plan doc's status without being asked.

## What this skill deliberately does not do

No PR/CI loop, no STRATEGY.md/CONCEPTS.md artifacts, no brainstorm ceremony. Deep research is `/deep-research`; torn between approaches is `/council`.
