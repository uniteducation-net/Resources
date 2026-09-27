---
type: logic
category: none
tags: [matching, jev, classification]
status: approved
---

# Jev Evaluation

Jev (`typesafe-ai/jev`, via the Vercel AI Gateway) is an evaluation model:
it never writes text. It evaluates typed questions against a *state* and
returns choices, scores, and boolean probabilities with confidences. The
cheap chat model writes everything the teacher reads — Jev only decides.

## State

The teacher's five [[Profile Questions]] answers, verbatim, as one text
block.

## Questions

All questions go in one call; they are evaluated in parallel against the
same state.

| ID | Primitive | What it decides |
|---|---|---|
| `primary_need` | Choice | which single category the teacher starts with — options are the seven categories `1.1` … `3.2` plus `none` |
| `worked_with_children` | Noul | whether the teacher has worked with children before |
| `entry_depth` | Score (3 levels) | 1 = first-time educator · 2 = some informal teaching · 3 = experienced but untrained |
| `low_resource_context` | Noul | whether the context suggests limited materials or connectivity |
| `large_classes` | Noul | whether the context suggests large or overcrowded classes |

## Rules

- Always include a `none`/`other` option on Choice questions.
- Act on `primary_need` only when its confidence is ≥ 0.6. Below that, fall
  back to [[1.1 Teaching & Learning Fundamentals]] — the research marks it
  the shared foundation for everyone.
- [[3.1 Ethics & Safeguarding]] is mandatory early regardless of the choice
  result — the research marks it non-optional.
- Code combines the answers into a decision. Decompose judgments into atomic
  questions and combine in code; never ask Jev to write prose.

---

*Related: [[Profile Questions]] · [[Progression Rules]] · [[Topic Relevance Matrix]]*
