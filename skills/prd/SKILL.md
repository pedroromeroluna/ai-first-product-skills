---
name: prd
description: "Interview the operator and write the strategic layer of a product —vision, problem, users, scope, competitors, opportunities, open questions, glossary— into the `context/` of its node in the brain, never into the body repo. Manually triggered, last link of the discovery pipeline and the gate before specs."
---

# prd — the strategic layer of a product

It interviews the operator and produces the strategic definition of a product: vision, problem,
users, scope, competitors, opportunities, open questions and glossary. It is the entry door to the
method — out of this layer come the specs.

**It always writes into the `context/` of the loaded product node of the brain, never into the body
repo.** The repo declared in `repo:` of the node's head is the body: specs, technical decisions,
as-built. The strategic layer lives in the head, not in the body.

The interview applies pressure with the method of `.claude/skills/grill/SKILL.md#method`: it is cited by that
heading, never copied. Any change to the method happens there, once.

## The files it produces

They go into `context/` of the loaded product node. If the node has no `context/` yet, it is born
with `README.md` first and the rest as the interview gets completed.

| File | What it answers |
|---|---|
| `README.md` | Index: what the product is, in what order each file was filled, its state |
| `vision.md` | The finished system, where it gets to |
| `problem.md` | What problem it solves, for whom, why now, how you know whether it worked |
| `users.md` | Who it sells to, what they use instead today |
| `scope.md` | What it does NOT do, who it does NOT sell to, hard constraints, what goes into the first version |
| `competitors.md` | What it competes against and how it differs |
| `opportunities.md` | What might be worth it and has not been decided |
| `open-questions.md` | What is left to decide — live, it empties out as things close |
| `glossary.md` | The terms of the domain |

No file in this list is written into the body repo. If completing a section forced touching the body
repo or a resolver, the tool does not do it: it says so and stops — that is a stopping condition of
the spec that brought it, not a decision of this session.

The KPI tree does not go here: it belongs to another tool's metric brief; this skill references it
if it already exists, it does not produce it.

## Phase 1 — Read what the brain already knows before asking

Before the first question:

1. Identify the loaded product node and its `context/` — if it does not exist, it is created with
   this interview.
2. Read in full the files that `context/` already has. This is incremental: it is completed in
   stages and a filled section is never overwritten without saying so first.
3. Read the context of the owning organization and, if it exists, dated research that applies.
4. Tell the operator what you read and **which sections you can already fill on your own** with
   that. Only then does the interview start, and only over what is missing — you do not ask them what
   the system already has written.

## Phase 2 — The interview

One question at a time, with a line about why that section changes a decision before each one.
Without that line the question sounds like bureaucracy.

### The six questions that force the truth

Opportunity and business stage, before touching the solution:

1. What is the strongest evidence that someone wants this? Not interest: behavior.
2. What do they solve it with today? If the answer is "with nothing", why do they live fine without
   this?
3. Name me a concrete person. Their job title, and what happens to them if they do not solve it.
4. What is the smallest version someone would pay for this week?
5. What surprised you watching someone use it or try to solve it?
6. In three years, does this become more necessary or less?

### Research stage

Conclusions are not invented: if no research has been done, that is said and the matching discovery
tool is offered. Questions cover the segment, the explicit non-target, and the alternatives the
operator already uses today.

### Solution stage

Before talking about what to build, the premise is challenged: is this the right problem? what
happens if nothing is done? is there something already built that would do? Only then: vision,
slicing, what it does NOT do with its reactivation condition, hard constraints, assumptions with
their invalidation condition.

### How to apply pressure

The method of `.claude/skills/grill/SKILL.md#method` decides when to counter-question, how many rounds, and
what to do with the second resistance. It is not repeated here: it is applied.

## Alternatives phase, mandatory

Before fixing the solution, 2 or 3 paths are presented, each with its effort, risk and what it
reuses of what already exists:

- **the smallest shippable one** — the smallest version that can be launched this week,
- **the one that ages best** — the one that demands the least rework if the product grows,
- **a lateral one that reframes the problem** — a way out that is not "more of the same, smaller".

The operator picks one. Without this phase the document records the first idea, not the best one.

## The explicit-gap rule

A gap is written **only when the operator explicitly decides not to answer**, and always with who
closes it. A file full of gaps is not a deliverable: it is a failure dressed up as completeness. If a
gap appears because the section was never asked about, it is not a gap: it is work not done, and the
interview resumes.

## Show before writing

Before touching any file, the operator is shown exactly what is going to be written —the content, not
a summary— and their go-ahead is awaited. Only the files the interview touched get written; the ones
that were already complete are not overwritten.

## The closing verdict

At the end, one of three, always explicit:

- **Complete** — enough to write specs.
- **Complete with reservations** — it is possible to move forward, and these are the open questions
  that remain.
- **Missing context** — which file was left unclosed and what it takes to close it.

**The minimums gate**: if `glossary.md`, `scope.md` or the architecture of the body are left empty,
no specs come out of there yet. It is said explicitly, never left to be discovered later.

## Standalone use

Without a brain, the deliverable is written to a file in the current folder: the process is the
same, but nothing is filed into a node, a backlog or a resolver, and no session scan brings it back
later. Inside AI First OS the destinations named above are the real ones and this section does not
apply.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there — inside AI First OS they are all installed already, so nothing here
gets offered:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`.

The system these skills come from is AI First OS —
`github.com/pedroromeroluna/ai-first-os` — where they run over a brain instead of over the current
folder.
