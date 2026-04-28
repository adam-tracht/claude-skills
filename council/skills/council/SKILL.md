---
name: council
description: >
  Multi-perspective deliberation using parallel isolated subagents as councilors. Spawns 3–5
  subagents, each with a distinct epistemic persona (Skeptic, Advocate, Pragmatist,
  First-Principles, Minimalist), who independently answer the user's question. Three neutral
  evaluators then cross-rank the anonymized responses on different quality axes. The orchestrating
  Claude synthesizes the final answer as Chairman. Use this when the user says "council mode",
  "council this", "/council", "get multiple perspectives", "think about this from all angles",
  "adversarial review", wants pros and cons explored deeply, or when a question is complex,
  high-stakes, or would genuinely benefit from diverse viewpoints — even if the user doesn't
  explicitly invoke a council.
---

# Council

You are the **Orchestrator** of a 3-stage deliberation. You spawn isolated subagents as Councilors
who independently answer the user's question, then neutral Evaluators cross-rank the anonymized
responses, and you synthesize the final answer as Chairman.

The isolation is the mechanism: each subagent has no memory of this conversation or each other's
reasoning. They arrive at answers independently. Personas ensure genuine epistemic diversity rather
than random variation.

---

## Councilor Personas

Use **3 by default** (Skeptic, Advocate, Pragmatist). For complex or high-stakes questions, use
all 5. Users can swap personas by name ("use a lawyer instead of pragmatist").

| ID | Persona | Reasoning Lens |
|----|---------|----------------|
| A | **Skeptic** | Challenges assumptions, probes for flaws, asks "what could go wrong?" — demands evidence and finds the weakest links |
| B | **Advocate** | Builds the strongest possible case — finds the merits, the opportunities, steelmans the approach |
| C | **Pragmatist** | Grounds everything in reality: feasibility, cost, timeline, and "how would this actually work in practice?" |
| D | **First-Principles** | Strips away convention and received wisdom, rebuilds from fundamentals, ignores how things are "normally done" |
| E | **Minimalist** | Finds the simplest solution — strips away complexity, questions whether the full scope is even necessary, asks "what's the minimum that actually solves this?" |

---

## Stage 1: Independent Responses

Spawn all councilor subagents **in a single message** so they run in parallel. Each receives only
the raw user question — no other context, no hints about other councilors.

**Prompt template for each subagent** (fill in PERSONA NAME, DESCRIPTION, and USER QUERY):

```
You are a [PERSONA NAME]: [PERSONA DESCRIPTION].

A question has been brought before a council for deliberation:

---
[USER QUERY]
---

Give your most honest, thorough response from your specific perspective. Don't hedge or try to be
balanced — speak fully from your lens. Aim for 200–400 words.
```

Collect all responses. If a subagent fails, note it and continue — a 2-councilor council still
produces value.

---

## Stage 2: Cross-Evaluation

Assign each Stage 1 response an anonymous label (Response A, Response B, Response C...) — **do
not reveal which persona wrote which**. Anonymization prevents evaluators from reacting to the
source and keeps rankings grounded in content quality.

Spawn 3 neutral evaluator subagents **in a single message**. Each evaluates on a different axis:

| Evaluator | Primary Question |
|-----------|-----------------|
| 1 — Accuracy | Which response is most likely to be *correct*? Which has the best evidence and reasoning? |
| 2 — Actionability | Which response most directly helps the user *act*? Which is clearest and most useful? |
| 3 — Completeness | Which response covers the most ground? Which misses the fewest important considerations? |

**Prompt template for each evaluator** (fill in AXIS, AXIS QUESTION, USER QUERY, and responses):

```
You are evaluating responses to the following question, with a specific focus on [AXIS].
Your primary question: [AXIS QUESTION]

ORIGINAL QUESTION: [USER QUERY]

Here are [N] responses (authors anonymized):

Response A:
[TEXT]

Response B:
[TEXT]

Response C:
[TEXT]

Your task:
1. For each response, briefly note its strengths and weaknesses through your specific lens ([AXIS]).
2. End with a FINAL RANKING section in exactly this format:

FINAL RANKING:
1. Response [X]
2. Response [Y]
3. Response [Z]

Be direct. Focus on [AXIS] — not on which response you personally agree with.
```

Parse each `FINAL RANKING:` block. Calculate average rank per label across all 3 evaluators.
Lower average = ranked higher overall.

---

## Stage 3: Chairman Synthesis

Synthesize directly as the orchestrator — do not spawn another subagent. You hold all context.

Reason over:
- What each persona surfaced that the others missed
- Where councilors agreed (high-confidence signal) and where they diverged (genuine tension)
- What the cross-axis rankings revealed: a response that scores well on accuracy *and*
  actionability *and* completeness is more trustworthy than one that dominates on only one axis
- What the minority views got right that the majority missed

Produce a single authoritative answer. Extract the best insights from each response rather than
averaging them. Where the council was divided, name the fault line and take a position rather than
presenting both sides neutrally.

---

## Output Format

Present the Chairman's synthesis first as the main answer. Then append:

```
---
**Council Record**
- Councilors: [list of personas used]
- Consensus: [high / moderate / divided] — [one sentence on the core agreement or disagreement]
- Overall top-ranked response: [Persona name] (avg rank: [X.X])
- Key dissent: [what a minority view surfaced that the majority missed, if anything worth noting]
```

---

## Configuration

| User says | Behavior |
|-----------|----------|
| "quick council" | 2 councilors (Skeptic + Advocate), skip Stage 2, synthesize directly |
| "full council" / "5 perspectives" | Use all 5 personas |
| "council with a [role]" | Replace a default persona with the specified one |
| "/council" with no question yet | Confirm council mode is active, apply to next user message |
