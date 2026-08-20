---
name: insight-engine
description: "Converge the raw answers of real fieldwork —clusters with their noise and their outliers, jobs to be done in three dimensions with two verbatims each, the customer profile, opportunities scored against the business outcome— and write the Insight Brief as dated research of the loaded product node. Manually triggered, fifth station of the discovery pipeline: the first one that runs after real fieldwork."
---

# insight-engine — the Insight Brief

Fifth station of the pipeline, and the first one that runs **after** real fieldwork. It takes what
real people actually said —interview transcripts, survey answers, support feedback— and converges it
into insights that carry their evidence, a customer profile, and opportunities ordered against the
business outcome. Generic domain example: a B2B appointment-management app for small clinics, with
twelve interviews of patients and administrators already done.

## When it is invoked

| When | From / to |
|---|---|
| Real fieldwork is done and the raw answers exist | Entry from real fieldwork — interviews with real people, the work the operator picks up; it is not a skill of this pack. The Diagnosis + Script v2 of `synthetic-users` (`.claude/skills/synthetic-users/SKILL.md`) is the guide those answers came from |
| The Insight Brief is written | Exit toward `ideation-engine` (`.claude/skills/ideation-engine/SKILL.md`) — the solution space starts from the profile this brief validates |
| With no prior station of the pipeline | Invocable on its own, over any set of real answers, with the business outcome as the minimum second input |

## Rule number one

**Evidence or silence.** Nothing enters the brief without a verbatim behind it, quoted with the
identifier of who said it. Where the data does not reach, the brief says "not enough evidence" and
names what would have to be researched — it never fills the gap with a plausible sentence. An
insight nobody said is an assumption with the authority of research, which is worse than no research.

## The two inputs

**The answers** (required): one or several sources, in whatever form they came. Converging sources
that were collected apart is half the value of this station.

**The business outcome** (required to prioritize): the objective the product is trying to move. It
is asked for with the pressure method of `.claude/skills/grill/SKILL.md#method` —cited by path, never
copied— before scoring anything. **Without an outcome there is no prioritization**, only a flat
list: with no outcome the opportunities are written unordered and the brief says why.

If the answers are simulated or synthetic —because they came from `synthetic-users`, or because the
source says so— the disclaimer travels into the brief: they train the method, they do not decide a
roadmap.

## The convergence, in four steps

**1. Clusters.** Group by behavior and context, never by demography alone: two people of the same
age can have opposite jobs. Each cluster carries a descriptive name, its size as a share of the
sample, and its defining traits. Two things are named apart and never quietly dropped: the **noise**
—answers too short, contradictory or empty— counted and excluded out loud, and the **outliers**,
which stay visible: an outlier is sometimes an entire opportunity.

**2. Jobs to be done**, each labeled by dimension: **[FUNCTIONAL]** the concrete task, **[EMOTIONAL]**
how the person wants to feel or avoid feeling, **[SOCIAL]** how they want to be seen. Every job is
written as *When [context], I want [motivation], so that [expected outcome]* and carries **at least
two literal verbatims** with the respondent identifier. The three dimensions are looked for; the one
the data does not support is declared missing, never invented.

**3. The customer profile.** For the prioritized cluster: jobs ordered by importance (frequency ×
intensity in the data), **pains** —costs, frictions, risks and negative emotions before, during and
after the job— and **gains**, separating expected from desired from unexpected when the data allows
it. Every item with its verbatim. **The value map —what the product does about all this— is not
written here**: it belongs to the solution space and to `ideation-engine`.

**4. Prioritized opportunities.** With the outcome as the root, each opportunity is an unmet need
expressed by users, **never a solution**. Each one carries: the statement in the user's own words,
the evidence that supports it (which clusters suffer it, which verbatims, which business figure
sizes it), and a score against the outcome with the criterion written out and the reasoning
visible, not only the number. They close ordered, as the branches that hang from the outcome.

## The Insight Brief

It closes by writing the deliverable as dated research of the loaded product node, in:

```
context/<YYYY-MM-DD>-insight-brief.md
```

Dated, never overwritten. The path falls inside `content: orgs/*/products/*/context/*.md` of
`tree.md`: no new glob and no resolver row are needed.

The brief carries these five sections, in this order, each with its literal heading:

```
## Clusters and noise
## Jobs to be done
## Customer profile
## Prioritized opportunities
## What this data does not say
```

- **Clusters and noise**: each cluster with its size and traits, the excluded noise counted, the
  outliers kept and named.
- **Jobs to be done**: every job with its dimension label and its two verbatims.
- **Customer profile**: jobs, pains and gains of the prioritized cluster, each with evidence.
- **Prioritized opportunities**: the branches hanging from the outcome, with score and reasoning.
- **What this data does not say**: the limits of the sample, the biases the collection could carry,
  and what would have to be researched before building. This section is written every time, also
  when the findings look conclusive — especially then.

## What this deliverable does not claim

The Insight Brief does not say what to build: it says what is worth attacking and with what
evidence. Turning an opportunity into ideas, and ideas into a value proposition, is the job of
`ideation-engine`. Deciding the scope and writing the strategic layer of the product is the job of
`prd` (`.claude/skills/prd/SKILL.md`).

## Standalone use

Without a brain, the deliverable is written to a file in the current folder: the process is the
same, but nothing is filed into a node, a backlog or a resolver, and no session scan brings it back
later. Inside AI First OS the destinations named above are the real ones and this section does not
apply.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`
- `ideation-engine` — `npx skills add pedroromeroluna/ai-first-product-skills --skill ideation-engine`
- `prd` — `npx skills add pedroromeroluna/ai-first-product-skills --skill prd`
- `synthetic-users` — `npx skills add pedroromeroluna/ai-first-product-skills --skill synthetic-users`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`. That command installs what the pack offers;
anything listed above it is installed by naming it.

The system these skills come from is AI First OS —
`github.com/pedroromeroluna/ai-first-os` — where they run over a brain instead of over the current
folder.
