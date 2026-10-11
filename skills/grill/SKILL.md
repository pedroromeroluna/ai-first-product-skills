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
ten ingredients come in two groups. 1-5 are how a single fact is pressured. 6-10 are how the whole
interview runs. In the order they are applied:

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

### 6. Rounds over the decision tree

The decisions of the interview are ordered as a tree, by what each one depends on. Each round brings
together, numbered, every question that can already be answered. A question that depends on another
one still open in the same round goes to the next round. After each round, what became answerable is
recomputed.

Format of a round (plain text, readable in a terminal without formatting):

```
Round 1

1. Who pays for the product, the person who uses it or their manager?
   Recommended: the manager pays, the analyst uses it.

2. Does the first version include a free tier?
   Recommended: no, a free tier is not part of the first version.
```

The person answers with "yes" to take every recommendation, or by number to change some. A question
number, the question and its recommendation are always on separate lines.

> Bad: one long message with six questions, three of which depend on the answer to the first.
>
> Good: round 1 asks who the buyer is and what they use today. Round 2, once those are answered,
> asks about pricing, which depends on both.

### 7. A recommended answer that "yes" accepts

Every question carries the answer the agent recommends, worded so that "yes" accepts it. Agreeing
never requires answering "no" to anything.

> Bad: "Recommended: don't limit it to one segment?" (agreeing takes a "no")
>
> Good: "Recommended: limit the first version to one segment, the finance teams of mid-size
> companies."

### 8. Facts are looked up, decisions are asked

A fact the environment can answer (files, earlier research, the body repo, another tool) is looked up
by the agent and never asked of the person. If what is found contradicts what the person said, the
contradiction is shown to them. The counter-question of ingredient 1 stays for the facts only the
person has. Decisions are always the person's.

If the environment offers helpers that can take a search, the search goes to one and the round
continues with the questions that do not depend on that fact. If it offers none, the search happens
before the round that needs it.

> Bad: "How many customers does the research say you interviewed?" (the research file says it)
>
> Good: "The research file says 8 interviews, 5 of them with finance leads. You mentioned 'a dozen
> conversations': do the extra four sit outside that file?"

### 9. The glossary is challenged and written as terms settle

Before the first round, the glossary is read if it exists. If the person uses a word that clashes
with it, they are stopped right then, naming the definition that clashes. A vague word, or one with
two meanings, is resolved by proposing the precise term and an edge case that tests it.

A term is written the moment the person accepts its exact text in a round, never at the end. The
glossary lives in `context/glossary.md` of the loaded product node; without a product node, in
`product-context/glossary.md` of the current folder. The file is created when the first term is
agreed. Each entry has the term, one or two sentences saying what it is, and the words to avoid. It
carries no implementation detail: a glossary is not a spec.

```
**Account** — The company that signs the contract and pays for the seats. _Avoid_: client, customer.
```

> Bad: the person says "customer" and the glossary defines it as the end user; the interview goes on.
>
> Good: "The glossary defines Customer as the end user, and you just used it for the company that
> pays. Proposed term: Account, the company that signs. Edge case: a freelancer who pays for
> themselves, is that an Account? Recommended: yes."

### 10. The interview closes when nothing is open and the operator confirms

It ends when no answerable question is left unanswered and the person confirms that both understand
the same thing. Before that confirmation, the only things written are glossary terms (ingredient 9),
gaps (ingredient 5) and decisions; no deliverable is produced and nothing agreed is acted on.

> Bad: the last question is answered and the agent starts writing the deliverable.
>
> Good: "Nothing answerable is left open. Two gaps recorded. Do we understand the same thing: a
> per-team product for finance leads, sold to the manager? Yes to close."

## Invocable face

It runs on its own over the node that is already loaded. It pressures its facts with the method
above and distributes what comes out across the canonical files that already exist — it invents
none:

| What comes out | Where it goes |
|---|---|
| A decision | `decisions.md` of the loaded node — the organization's if that is where the work is happening, the root's if the loaded node is the operator's own work |
| A gap | The backlog of the loaded node (`backlog.md` of the organization), recorded as open with who closes it named in the text — the same free-text, verbatim line format the session close already uses |
| A term the operator accepted | The product glossary (`glossary.md`), at the destination and in the format of ingredient 9 |
| A gap, if the loaded product node declares its own open-questions layer | That layer (`context/open-questions.md` of the node), instead of the backlog |

The decision and gap destinations exist before this tool; the glossary is born when the first term
is agreed. If pressuring a fact were to lead to writing into a destination that is not in this table,
`grill` does not invent it: it says so and stops — that row is added by the operator, not by the session.

## Key decisions

Every decision is recorded. A **key decision** is one that is also marked as key where it is
recorded, so whoever opens the work next reads it before the rest instead of waiting for a search to
find it. **It is key only when all three conditions hold; two out of three is not key:**

1. **Hard to reverse**: undoing it costs real work, money or trust.
2. **Surprising without context**: someone who arrives without this conversation would not guess it.
3. **Born of a real trade-off**: a real alternative was on the table and was discarded.

> Key: "The company sells B2B first" — undoing it means rewriting pricing and the pitch (1), a
> newcomer would assume B2C (2), and the B2C path was weighed and dropped (3).
>
> Not key: "The weekly report goes out on Mondays" — trivial to change (fails 1), nobody is
> surprised by it (fails 2), no alternative was weighed (fails 3).

**The mark is proposed by the agent and confirmed by the operator.** Before marking a decision as
key, show the operator the decision with the three conditions side by side, say which holds and which
does not, and mark it only if they accept. A decision that fails one condition is not proposed: say
which one fails and leave it unmarked.
