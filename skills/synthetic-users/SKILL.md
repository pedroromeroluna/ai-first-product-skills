---
name: synthetic-users
description: "Pilot the v1 research guide against synthetic personas —every trait marked as evidence or assumption, at least one skeptic— to find broken questions before spending real fieldwork, and write the Diagnosis + Script v2. Manually triggered, fourth station of the discovery pipeline; it validates nothing."
---

# synthetic-users — the Diagnosis + Script v2

Fourth station of the pipeline. It pilots the guide that `ux-research` built against synthetic
personas —simulated profiles with explicit traits— before spending the first minute of real
fieldwork. Generic domain example: a B2B appointment-management app could simulate an administrator
of a small clinic and a skeptical one who already tried and abandoned a similar tool.

## When it is invoked

| When | From / to |
|---|---|
| The Research Plan from `ux-research` already has a v1 guide | Entry from `ux-research` (`.claude/skills/ux-research/SKILL.md`) |
| The Diagnosis + Script v2 is written | Exit: real fieldwork — interviews with real people, the work the operator picks up; it is not a skill of this pack |
| After real fieldwork | The raw answers are converged by `insight-engine` (`.claude/skills/insight-engine/SKILL.md`), and from there the pipeline reaches the strategic layer that `prd` writes (`.claude/skills/prd/SKILL.md`) |

## Rule number one

**This validates NOTHING.** It opens the session with this sentence and repeats it on closing: no
answer from a synthetic persona is evidence that something works with real users. It serves one
purpose —finding defects in the guide before spending fieldwork time— and no other. A Diagnosis that
reads as if it validated the hypothesis is badly written, no matter how many times the rule was
repeated in the text.

## The synthetic personas

It is run with the pressure method of `.claude/skills/grill/SKILL.md#method` — cited by path, never copied —
while building each profile: every trait proposed is pressured for its origin before entering the
profile.

Every simulated persona carries its traits with an explicit origin, marked one by one:
**(evidence)** if it comes from real research already done —an interview, a usage figure, something
the Discovery Brief or the Market Brief brings— or **(assumption)** if it is a construction with no
research behind it. A trait with no mark does not enter the profile.

**At least one skeptical persona**, with a reason: someone who already tried something similar and
abandoned it, someone with a business objection (the cost, the process change), or someone who
simply does not have the problem the hypothesis assumes. A set of personas that only confirm the
hypothesis is no use for finding defects: it is useful for confirming them.

**No "I love it!" without a cost next to it.** Every enthusiastic answer from a synthetic persona is
accompanied by its cost or its friction: what it costs them, what worries them, what they would have
to stop doing. An answer made only of enthusiasm is the signal that the guide is built to confirm,
not to learn.

## The taxonomy of question defects

Every question of the v1 script is reviewed against this list; the defect found is recorded with its
rewrite next to it, never merely pointed at:

| Defect | Example | Rewrite |
|---|---|---|
| Leading question (suggests the answer) | "Don't you think an automatic reminder would be useful?" | "How do you keep from missing an appointment today?" |
| Hypothetical question ("would you use...?") | "Would you use a feature that rescheduled appointments on its own?" | "Tell me about the last time you had to reschedule an appointment" |
| Double question | "Is the dashboard clear and fast to use?" | Split into two questions, one per attribute |
| Question with no behavior behind it | "What do you think about appointment management in general?" | "When was the last time you managed appointments for your team?" |
| Jargon the segment does not use | An internal technical term of the product team | The word the segment uses, taken from prior research |

## The Diagnosis + Script v2

It closes by writing the deliverable as dated research of the loaded product node, in:

```
context/<YYYY-MM-DD>-diagnostico-guion.md
```

Dated, never overwritten. The path falls inside `content: orgs/*/products/*/context/*.md` of
`tree.md`: no new glob and no resolver row are needed.

The Diagnosis carries these four sections, in this order, each with its literal heading:

```
## Synthetic personas
## Simulation
## Defects found and rewrites
## Script v2
```

- **Synthetic personas**: each profile, with its traits marked `(evidence)` or `(assumption)`, and
  the skeptical persona identified as such.
- **Simulation**: the simulated answers against the v1 script, every enthusiasm with its cost next
  to it.
- **Defects found and rewrites**: every defect from the taxonomy that showed up, with its rewrite.
- **Script v2**: the corrected guide, ready for real fieldwork.

The **Script v2** section opens and closes with rule number one written out: "this validates
NOTHING" — before the first question and after the last one.

## What this deliverable does not claim

The Diagnosis + Script v2 does not replace real fieldwork: it is the step that reduces how much
broken script reaches the first interview with a real person. Synthesizing what comes out of real
fieldwork —transcripts into findings— is not the job of this skill: that is `insight-engine`.

## Standalone use

Without a brain, the deliverable is written to a file in the current folder: the process is the
same, but nothing is filed into a node, a backlog or a resolver, and no session scan brings it back
later. Inside AI First OS the destinations named above are the real ones and this section does not
apply.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there — inside AI First OS they are all installed already, so nothing here
gets offered:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`
- `insight-engine` — `npx skills add pedroromeroluna/ai-first-product-skills --skill insight-engine`
- `prd` — `npx skills add pedroromeroluna/ai-first-product-skills --skill prd`
- `ux-research` — `npx skills add pedroromeroluna/ai-first-product-skills --skill ux-research`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`.

The system these skills come from is AI First OS —
`github.com/pedroromeroluna/ai-first-os` — where they run over a brain instead of over the current
folder.
