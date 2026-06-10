---
id: pillar-personal-foundation
title: Decisions Should Be Deliberate and Recorded
type: pillar
namespace: personal
visibility: public
summary: The founding principle that deliberate, recorded decisions outperform ad-hoc reactions over time, especially as context fragments across projects and seasons of life.
auto_inject: false
applicable_when: "Empty"
confidence: 1.0
verified_at: 06/11/2026
verified_by: System Bootstrap
staleness_signal: If this vault is archived or its purpose changes fundamentally, mark as historical
tags: ["core-philosophy", "decision-making", "institutional-memory", "knowledge-management"]
edges: [
  {"target": "decision-personal-first", "type": "supports", "weight": 0.9, "note": "The decision exemplifies the principle of deliberate action recorded in writing"}
]
related: ["[[decision-personal-first]]"]
source_url: "Empty"
---

# Decisions Should Be Deliberate and Recorded

## Why This Pillar Exists

The default mode under pressure is reaction. A question gets answered, a choice gets made, and within a week nobody remembers why. Context decays, and the same debates repeat themselves endlessly.

This pillar asserts that **time spent recording the reasoning behind a decision is not overhead — it is leverage**. The marginal cost of writing a decision record is small; the cost of not having it when context is needed is large.

## What "Deliberate" and "Recorded" Mean

A deliberate decision makes explicit: the problem being solved, the alternatives considered, the criteria for choice, the expected outcome, and the conditions for reversal. Deliberate does not mean slow — a five-minute writeup is enough for most operational choices. The point is traceability, not formality.

Recording means placing the decision in this vault with structured frontmatter and a body that explains the reasoning, retrievable via namespace, tags, and edges to related nodes.

## Implications for Vault Behavior

Every agent and human operating within this vault should:

1. Default to creating a decision node before taking significant action.
2. Fill in all required frontmatter fields — especially `staleness_signal`.
3. Wire decisions to pillars that justify them, using the `supports` edge type.
4. Revisit decision nodes when their staleness signal is triggered.

---

*This pillar was bootstrapped as part of the initial vault scaffolding on 06/11/2026.*
