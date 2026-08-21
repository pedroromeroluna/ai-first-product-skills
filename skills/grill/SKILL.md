---
name: grill
description: "Pressure the facts behind a claim before a decision closes — counter-question with a concrete example, capped attempts, escape hatches, evidence hierarchy — and route what comes out to the loaded node's decisions or backlog. Manually triggered, and also the method any other interviewing tool cites by path."
---

# grill — the pressure interview

Two faces. **Invocable on its own**: it pressures the facts of the loaded node and distributes what
comes out without inventing a new destination. **Referenceable method**: any tool that interviews
cites the section below instead of copying it — varying who it points at or which examples it uses
is parameterization by whoever cites, never a second copy of the method.

## Method

Cite this section by its heading (`.claude/skills/grill/SKILL.md#method`) from any tool that interviews. The
five ingredients, in the order they are applied:

### 1. Counter-question with a concrete example

Faced with an answer that cannot be falsified ("everybody liked it", "it was a success", "the team
is clear on it"), the answer is neither accepted nor rephrased: a counter-question is returned
asking for the fact behind it, with an example of what would count as a good answer.

> Bad: "could you give more detail?"
>
> Good: "'they liked it' by what measure — did they finish the task unassisted, did they say it, or
> did you infer it? A good answer names the data: '3 out of 5 finished without asking for help, 2
> dropped out at step 3'."

### 2. Pressure capped at 1-2 attempts

At most two rounds of counter-question on the same fact. A third one gets no more information: it
saturates the interviewee and the method stops being an interview and becomes an interrogation.

### 3. Escape hatches

Two ways out, neither of which is "keep insisting":

- **Second resistance** — the answer to the second counter-question still has no fact. The attempt
  is neither discarded nor forced into a third round: the gap is recorded, with who closes it, and
  you move on.
- **Strong evidence up front** — if the first answer already carries the fact (observed behavior,
  measured data), there is no counter-question to make: it is confirmed and you move on.

### 4. Evidence hierarchy

`behavior > data > claim > assumption`. Faced with two answers competing over the same fact, the one
higher in the hierarchy wins — an assumption does not weigh the same as observed behavior even when
both are stated with the same confidence.

### 5. Every gap is recorded, never filled in

A gap the pressure did not close is not completed with an inference so the document looks tidy. It
is recorded as open, with who closes it. Filling it in silently is the same class of incomplete scan
presented as complete that the rest of the system forbids.

## Invocable face

It runs on its own over the node that is already loaded. It pressures its facts with the method
above and distributes what comes out across the canonical files that already exist — it invents
none:

| What comes out | Where it goes |
|---|---|
| A decision | `decisions.md` of the loaded node — the organization's if that is where the work is happening, the root's if the loaded node is the operator's own work |
| A gap | The backlog of the loaded node (`backlog.md` of the organization), recorded as open with who closes it named in the text — the same free-text, verbatim line format the session close already uses |
| A gap, if the loaded product node declares its own open-questions layer | That layer (`context/open-questions.md` of the node), instead of the backlog |

The three destinations exist before this tool. If pressuring a fact were to lead to writing into a
destination that is not in this table, `grill` does not invent it: it says so and stops — that row
is added by the operator, not by the session.
