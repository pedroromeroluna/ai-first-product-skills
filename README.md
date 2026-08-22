# Product Builder skills

11 skills for building product with an agent: discovery from a vague problem to the strategic
layer of a product —including what happens after real fieldwork: converging the evidence and
ideating the solution—, the measurement layer, and the standing crafts of a CPO and a CTO.

Each one runs on its own, in any project, with nothing else installed: a small skill, a small blast
radius, a real deliverable. Installed this way the deliverable is a file in the current folder.

## Install

The whole pack:

```
npx skills add pedroromeroluna/ai-first-product-skills
```

One skill at a time:

```
npx skills add pedroromeroluna/ai-first-product-skills --skill product-strategy
```

Either way the skills land in `.claude/skills/` of the current project, where any harness that reads
the Agent Skills standard picks them up. Nothing here activates on its own: a skill runs when you
name it.

## The suggested sequence

Discovery is a chain. Nothing enforces the order —every skill works alone and out of order— but each
station leaves written down what the next one expects to read:

1. **`product-strategy`** — Run the socratic discovery interview that separates the symptom from the cause, grades the evidence, applies the metric gate and prioritizes up to three hypotheses, and write the Discovery Brief as dated research of the loaded product node. Manually triggered, first station of the discovery pipeline.
2. **`market-research`** — Size the opportunity with secondary research only — directional TAM/SAM/SOM where every number carries its cited source and the assumption that turns it into a number for this product — and write the Market Brief as dated research of the loaded product node. Manually triggered, second station of the discovery pipeline.
3. **`ux-research`** — Design one research round against the single riskiest hypothesis — behavioral screening, one modality chosen on purpose, a guide whose every question is tied to a hypothesis or a job dimension — and write the Research Plan as dated research of the loaded product node. Manually triggered, third station of the discovery pipeline.
4. **`synthetic-users`** — Pilot the v1 research guide against synthetic personas —every trait marked as evidence or assumption, at least one skeptic— to find broken questions before spending real fieldwork, and write the Diagnosis + Script v2. Manually triggered, fourth station of the discovery pipeline; it validates nothing.
5. **Real fieldwork** — real interviews with real people, outside this pack and outside any agent.
   The synthetic pilot finds broken questions; it validates nothing.
6. **`insight-engine`** — Converge the raw answers of real fieldwork —clusters with their noise and their outliers, jobs to be done in three dimensions with two verbatims each, the customer profile, opportunities scored against the business outcome— and write the Insight Brief as dated research of the loaded product node. Manually triggered, fifth station of the discovery pipeline: the first one that runs after real fieldwork.
7. **`ideation-engine`** — Run the solution space in two modes — DIVERGE prepares the workshop (traceable How Might We, seed ideas sealed until the humans have ideated, a timeboxed agenda and the board written zone by zone) and CONVERGE reads what the team produced and voted and writes the Value Map plus the prototype brief. Manually triggered, sixth station of the discovery pipeline; it never picks the winning idea.
8. **`prd`** — Interview the operator and write the strategic layer of a product —vision, problem, users, scope, competitors, opportunities, open questions, glossary— into the `context/` of its node in the brain, never into the body repo. Manually triggered, last link of the discovery pipeline and the gate before specs.

Three more that hang off the chain rather than sitting in it:

- **`visual-designer`** — Specify any visual piece —a product interface, a presentation, an infographic— screen by screen or slide by slide: purpose, structure, hierarchy, the content of every block and the visual criteria applied, written as a dated document of the loaded product node. It closes by checking whether the session has a tool able to build it and only then offers to; with no tool it closes with the document. Manually triggered, invocable on its own.
- **`product-metrics`** — Build the measurement layer of a product — one candidate North Star, the tree of levers that hold it up with where each is measured, one metric per active hypothesis with its value today or a gap with an owner, and the antimetrics with their alarm thresholds — and write the Metric Brief. Manually triggered, or entered when the metric gate of product-strategy does not pass.

Two more that are not stations at all:

- **`cpo`** — The standing craft of a Chief Product Officer — every strategic question answered in four steps (diagnosis, at least two options with tradeoffs, a clear stance, next steps) under four golden rules. Load it as context when acting as CPO of a workspace; it is also activated by `role: cpo` in that workspace's node.
- **`cto`** — The standing craft of a Chief Technology Officer — every technical question answered in four steps (diagnosis of what exists and its constraints, at least two options with tradeoffs and long-term cost, a clear stance that always names the alternatives discarded and why, next steps that can be verified) under five golden rules for a non-developer builder. The state of the art — models, prices, capabilities — is verified live before opining, never answered from memory. Load it as context when acting as CTO of a workspace; it is also activated by `role: cto` in that workspace's node.

## The index

`npx skills add pedroromeroluna/ai-first-product-skills` also installs **`product-builder-resolver`**: one row per capability of the
pack, so an agent can route a request to the right skill instead of guessing. Load it when you do
not know which of the 11 the situation calls for.

## The system these come from

These 11 are one pack of **AI First OS**, a product operating system for a person who works with
agents: every session opens with a scan of your work, whatever comes up gets captured on the fly,
the session closes with a verdict of what got done and what is missing, and the deliverables of
these skills land in the node they belong to instead of in a loose file.

`github.com/pedroromeroluna/ai-first-os`

The sample sells the system, never the other way round: if these earn your trust on their own, that
is where they came from.

## License

MIT. See `LICENSE`.
