---
name: product-strategy
description: "Run the socratic discovery interview that separates the symptom from the cause, grades the evidence, applies the metric gate and prioritizes up to three hypotheses, and write the Discovery Brief as dated research of the loaded product node. Manually triggered, first station of the discovery pipeline."
---

# product-strategy — the Discovery Brief

First link of the discovery pipeline. It interviews socratically —never agreeing too early— to
separate the symptom from the cause, and closes by writing the Discovery Brief: the problem, the
evidence behind it, and up to three prioritized hypotheses.

## When it is invoked

| When | From / to |
|---|---|
| Discovery starts on a new opportunity or a problem with no prior research | Invocable on its own, over the loaded product node |
| The Discovery Brief is written | Exit toward `market-research` (`.claude/skills/market-research/SKILL.md`) — next station of the pipeline |
| The metric gate does not pass | Handoff toward `product-metrics` (`.claude/skills/product-metrics/SKILL.md`) — builds the North Star and the hypothesis metric before going on |

`product-metrics` is already installed in this pack: the handoff is real, not the dangling reference
to a metrics coach that the old pipeline used to name.

## The interview

It is run with the pressure method of `.claude/skills/grill/SKILL.md#method` — cited by path, never copied.

### Socratic: it does not agree

Faced with a proposal that already arrives shaped as a solution ("we need a tracking dashboard", "we
have to add notifications"), the answer is neither accepted nor elaborated: the counter-question that
separates the solution from the problem is returned.

> Bad: "good idea, what would that dashboard have?"
>
> Good: "that is a solution. What problem does it solve, and whose problem is it?"

It repeats until the answer names a concrete person's problem — never a feature.

### Evidence hierarchy

All evidence backing the problem is graded with the same hierarchy `grill` uses:
`behavior > data > claim > assumption`. "Several clients asked for it" (claim) does not weigh the
same as "3 out of 5 abandon checkout at the shipping step" (data), nor as a recorded session where
someone tries it and gets stuck (behavior). The lowest-grade evidence available is recorded anyway,
with its level next to it — it is not discarded, it is labeled.

### The metric gate

**With no metric, the problem is not clear.** Before accepting the problem as well posed, the
question is asked: which number would move if this were solved? If there is no answer, or the one
that shows up is a vanity metric (it changes no decision), the gate does not pass: it is said
explicitly and the work is handed off to `product-metrics` to build it before going on. Nothing
proceeds as if the gate had passed.

### Hypotheses, with a fixed format

Every hypothesis is written in this shape, without exception:

```
We believe that [segment] [does X] at [moment] because of [cause]; if that is true, we will see [evidence].
```

Generic example (e-commerce): "We believe that buyers who abandon the cart at the shipping step do so
because the cost only appears there; if that is true, we will see that showing the cost earlier
reduces abandonment at that step." A hypothesis without the "if that is true, we will see..." clause
is not a hypothesis: it is an opinion shaped like one, and it is returned with a counter-question.

**At most 3, prioritized by risk × impact** — never by order of appearance in the conversation. Risk:
how little is known about whether it is true. Impact: how much it moves the gate metric if
confirmed. A fourth hypothesis that shows up is recorded as a gap in the backlog; it does not enter
the list.

## The Discovery Brief

It closes by writing the deliverable as dated research of the loaded product node, in:

```
research/<YYYY-MM-DD>-discovery-brief.md
```

Dated, never overwritten — the same criterion the research folder of this repo already uses. The
path falls inside `content: */products/*/research/*.md` line of the brain's own `tree.md`: no new glob
and no resolver row are needed. Without a product node, this same file —
`<YYYY-MM-DD>-discovery-brief.md` — is what lands in the current folder instead.

The Brief carries these four sections, in this order, each with its literal heading:

```
## Problem
## Evidence
## Metric gate
## Prioritized hypotheses
```

- **Problem**: the symptom separated from the cause, whose it is and why now.
- **Evidence**: each piece with its hierarchy level (`behavior`, `data`, `claim` or `assumption`)
  next to it.
- **Metric gate**: passed or not, and if it did not, the handoff to `product-metrics` left explicit.
- **Prioritized hypotheses**: up to 3, in the fixed format, ordered by risk × impact with the reason
  for the order.

## What this deliverable does not claim

The Discovery Brief does not replace the strategic layer that `prd` writes: it is dated research,
input for the next stations of the pipeline, never the living canon of the product.

## Destination

The skill resolves the destination before producing the deliverable, never after. Three cases,
two destinations:

- A product node is loaded: the deliverable goes to `research/<YYYY-MM-DD>-<name>.md` of that node.
- There is a brain, but no product node — no workspace yet, or a workspace without one: the
  deliverable is written to a file in the current folder.
- There is no brain at all: the deliverable is written to a file in the current folder.

With no product node, the file is written to the current folder anyway. The closing message
names only the path it just wrote and stops there — that is the normal way this skill ends, not
an anomaly to qualify.

This skill never asks which destination to use, and it never invents a third one.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there — once per session: the first time this skill closes in the session,
never again on a later close of the same or another deliverable:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`
- `market-research` — `npx skills add pedroromeroluna/ai-first-product-skills --skill market-research`
- `prd` — `npx skills add pedroromeroluna/ai-first-product-skills --skill prd`
- `product-metrics` — `npx skills add pedroromeroluna/ai-first-product-skills --skill product-metrics`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`. That command installs what the pack offers;
anything listed above it is installed by naming it.
