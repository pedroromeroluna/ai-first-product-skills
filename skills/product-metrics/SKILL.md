---
name: product-metrics
description: "Build the measurement layer of a product — one candidate North Star, the tree of levers that hold it up with where each is measured, one metric per active hypothesis with its value today or a gap with an owner, and the antimetrics with their alarm thresholds — and write the Metric Brief. Manually triggered, or entered when the metric gate of product-strategy does not pass."
---

# product-metrics — the Metric Brief

The gap the old pipeline acknowledged without filling: `product-strategy` demands that "with no
metric, the problem is not clear", but no tool helped build that metric — it handed off to a metrics
coach that never existed. This is that station: it defines the candidate North Star, builds the tree
of levers that hold it up, and gives every active hypothesis a number, a way of measuring it and a
value as of today.

## When it is invoked

| When | From / to |
|---|---|
| The metric gate of `product-strategy` does not pass ("with no metric, the problem is not clear") | Entry from `product-strategy` (`.claude/skills/product-strategy/SKILL.md`) |
| The Metric Brief is written | Exit toward `prd` (`.claude/skills/prd/SKILL.md`) — the strategic `context/` of the node is completed with the metric already defined |
| With no prior gate | Invocable on its own, over the product node already loaded |

Both neighboring stations are already installed in this pack: naming them here is real, not invented
— unlike the old reference to a metrics coach with neither spec nor owner.

## The interview

It is run with the pressure method of `.claude/skills/grill/SKILL.md#method` — cited by path, never copied.
The five ingredients (counter-question with an example, pressure capped at 1-2 attempts, escape
hatches, evidence hierarchy, every gap recorded) are applied exactly as described there.

Before asking: if the loaded product node has dated research from `product-strategy` (a Discovery
Brief with hypotheses), read it — the active hypotheses come from there, they are not asked again.
If there is no prior research, they are asked directly.

Four steps, in this order:

### 1. Candidate North Star

A single candidate North Star metric, with the reason in one line: which product decision it moves,
not why "it matters". Faced with an answer that names no decision ("because it measures success",
"because it is the one everybody looks at"), grill returns it with a counter-question.

### 2. Metric tree

The North Star on top, its levers below — the variables that, if they move, move the North Star.
Every lever carries where it is measured (which event, which table, which source — the where, never
how to instrument it: that belongs to the body of the user's product, not to this tool). A lever
with no where-it-is-measured is a gap, not a complete line.

### 3. Metric per active hypothesis

For each active hypothesis (the ones `product-strategy` brings, or the ones raised here if there is
no prior research): which number validates or refutes it, measured how, against what value as of
today.

**Hard rule: no value with a source, no data.** A value as of today that the operator cannot cite
with its origin (a dashboard, a measurement, a dated figure) is not written as if they could: it is
recorded as a gap, with who closes it — the same gap format `grill` uses. Inventing the number so the
row looks complete is the same incomplete scan presented as complete that the rest of the system
forbids.

### 4. Antimetrics

What should not get worse while the North Star improves, with the threshold that triggers the alarm
— a number or a verifiable condition, never "if it gets much worse".

### The vanity metric

After every proposed metric (North Star, lever or hypothesis metric), this question is applied:
**which decision does this number change, in whichever direction it moves?**

If there is no answer, or the answer is another metric ("it changes how we see growth"), it is a
vanity metric: it is said outright — "this is a vanity metric: it changes no decision" — and the
concrete decision the metric should move is requested before accepting it into the Brief. It is
neither discarded in silence nor accepted to avoid interrupting the interview.

## The Metric Brief

It closes by writing the deliverable as dated research of the loaded product node, in:

```
context/<YYYY-MM-DD>-metric-brief.md
```

Dated, never overwritten — the same criterion the research folder of this repo already uses. The path
falls inside `content: orgs/*/products/*/context/*.md` of `tree.md`: no new glob and
no resolver row are needed.

The Brief carries these four sections, in this order, each with its literal heading:

```
## Candidate North Star
## Metric tree
## Metric per hypothesis
## Antimetrics
```

- **Candidate North Star**: the metric and the reason in one line (which decision it moves).
- **Metric tree**: the North Star on top, each lever on one line with its where-it-is-measured.
- **Metric per hypothesis**: one entry per active hypothesis — which number, measured how, value as
  of today or a gap with an owner.
- **Antimetrics**: each one with its alarm threshold.

If the interview detected a vanity metric along the way, the Brief leaves it written anyway —with the
label "(vanity: it does not change [the decision that was asked for and never got an owner, if it
was left unclosed])"— and never deletes it in silence.

## What this deliverable does not claim

The Metric Brief neither creates nor demands a new canonical file of the product node: it is dated
research, it adds to what is already there, and it neither replaces nor forces re-versioning a live
file of the `context/`. If a metrics canonical file were ever needed (a live `metrics.md` that gets
overwritten), that decision is approved by the operator — not by this tool.

## Standalone use

Without a brain, the deliverable is written to a file in the current folder: the process is the
same, but nothing is filed into a node, a backlog or a resolver, and no session scan brings it back
later. Inside AI First OS the destinations named above are the real ones and this section does not
apply.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there — inside AI First OS they are all installed already, so nothing here
gets offered:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`
- `prd` — `npx skills add pedroromeroluna/ai-first-product-skills --skill prd`
- `product-strategy` — `npx skills add pedroromeroluna/ai-first-product-skills --skill product-strategy`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`.

The system these skills come from is AI First OS —
`github.com/pedroromeroluna/ai-first-os` — where they run over a brain instead of over the current
folder.
