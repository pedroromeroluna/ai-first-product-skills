---
name: product-builder-resolver
description: The capability index of the product-builder pack — which skill answers which capability, and where each one lives once installed. Load it to route a request to the right skill of the pack instead of guessing, and to see what the pack does not cover.
---

# product-builder — the pack resolver

One row per capability. The Tool column names the skill to load; the Path column is where that skill
lives once `npx skills add pedroromeroluna/ai-first-product-skills` has installed it.

| Capability | Tool | Path |
|---|---|---|
| Define the problem, the evidence behind it and the prioritized hypotheses of a product | `product-strategy` | `.claude/skills/product-strategy/SKILL.md` |
| Research the market with secondary research and size the opportunity | `market-research` | `.claude/skills/market-research/SKILL.md` |
| Plan the qualitative or quantitative research round on the riskiest hypothesis | `ux-research` | `.claude/skills/ux-research/SKILL.md` |
| Pilot a research script with synthetic personas before real fieldwork | `synthetic-users` | `.claude/skills/synthetic-users/SKILL.md` |
| Converge the evidence of real fieldwork into insights, the customer profile and prioritized opportunities | `insight-engine` | `.claude/skills/insight-engine/SKILL.md` |
| Prepare the ideation workshop and converge its results into the value map and the prototype brief | `ideation-engine` | `.claude/skills/ideation-engine/SKILL.md` |
| Specify a visual piece —interface, deck, infographic— and build it when a design tool is connected | `visual-designer` | `.claude/skills/visual-designer/SKILL.md` |
| Define the North Star, the metric tree and the metric of each active hypothesis | `product-metrics` | `.claude/skills/product-metrics/SKILL.md` |
| Interview and write the strategic layer of a product | `prd` | `.claude/skills/prd/SKILL.md` |
| Act as standing CPO over the product of an organization | `cpo` | `.claude/skills/cpo/SKILL.md` |
| Act as standing CTO over the technical architecture of an organization's product, software and AI systems included | `cto` | `.claude/skills/cto/SKILL.md` |

A request that no row covers is not answered by improvising one of these skills: the missing
capability is named instead. This index is the pack's own — it never routes anything outside it.
