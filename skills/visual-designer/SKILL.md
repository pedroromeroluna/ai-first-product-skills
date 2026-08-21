---
name: visual-designer
description: "Specify any visual piece —a product interface, a presentation, an infographic— screen by screen or slide by slide: purpose, structure, hierarchy, the content of every block and the visual criteria applied, written as a dated document of the loaded product node. It closes by checking whether the session has a tool able to build it and only then offers to; with no tool it closes with the document. Manually triggered, invocable on its own."
---

# visual-designer — the visual spec, and its execution when there is a tool

It writes what a visual piece has to say and how it has to be organized, before anyone opens a design
tool. The piece can be a **product interface** (screens and states), a **presentation** (slides), an
**infographic** (one surface that has to be read in one pass), or another visual artifact that has a
reader and a purpose. Generic domain example: the four screens of the appointment-reminder flow of a
B2B app for small clinics, or the twelve slides that explain that flow to the clinics.

**The specification is the deliverable. Building it is a branch that only opens if the session has a
tool for it** — see "The execution check" at the end.

## When it is invoked

| When | From / to |
|---|---|
| The prototype brief from `ideation-engine` is written | Entry from `ideation-engine` (`.claude/skills/ideation-engine/SKILL.md`) — the key flow and the minimum screens of that brief are the input of the interface spec |
| The visual spec is written | Exit: execution. If the session has a tool able to build it, it is offered right there; if not, the document is the end of the station and whoever builds it builds it from there |
| Any piece with a reader and a purpose | Invocable on its own, with no prior station: a deck, an infographic, a screen that has to exist tomorrow |

## Rule number one

**It never invents content that the piece does not have.** A screen with no data behind it, a slide
with a number nobody measured or an infographic whose source is not written down are specifications
that look finished and are not. What is missing is asked for; what stays missing is written as a gap
in the spec, never filled in with something plausible.

## The interview

The purpose, the reader and the success condition of the piece are pressured with the method of
`.claude/skills/grill/SKILL.md#method` —cited by path, never copied— before any structure gets written. Three
questions carry the weight, and none of them is answered by the operator saying "it has to look
good":

- **Who reads it, and in what situation?** Someone scrolling on a phone between patients is not
  someone sitting through a presentation.
- **What has to happen after they read it?** One action, one decision, one thing understood. A piece
  with three purposes has none.
- **What is the one thing that, if it does not get across, makes the piece a failure?** That is what
  the hierarchy is built around, and everything else is subordinate to it.

## Method

The shared visual criteria. Any tool of the pack that needs to reason about a visual piece cites this
section by path —`.claude/skills/visual-designer/SKILL.md#method`— and never copies it.

### 1. One hierarchy per surface

Every screen, slide or surface has **one** primary element, and it is named in the spec. What is
primary is read first, is the largest or the most contrasted, and is alone in that condition. Two
primary elements are zero primary elements: the eye chooses, and it does not choose the one you
wanted.

### 2. Air is content

Empty space is not room going to waste: it is what makes the hierarchy readable. Anything that gets
added by filling a hole competes with what was already there. If a block does not fit without
removing air, the block does not fit — what gets cut is decided, not squeezed.

### 3. Contrast carries the meaning, never decoration alone

Difference in size, weight or color is used to say something —this comes first, this is a warning,
this is secondary— and every difference in the spec carries what it means next to it. Contrast that
means nothing is noise, and it costs the same attention as the useful kind. Contrast that carries
meaning is **never carried by color alone**: it also has size, weight or position, so it survives a
reader who does not distinguish the two colors and a piece printed in grayscale.

### 4. One block, one message

Every block —a section of a screen, a slide, an area of an infographic— says one thing and can be
summarized in one line. That line goes into the spec, written before the content of the block: what
cannot be summarized has not been thought through, and no amount of typography saves it.

### 5. The state that is not the happy one

An interface with no empty, loading and error state is half specified; a deck with no slide for the
objection it will get is half specified. Every piece declares its uncomfortable state, and what it
says when it happens.

## The visual spec

It closes by writing the deliverable as a dated document of the loaded product node, in:

```
context/<YYYY-MM-DD>-visual-spec.md
```

Dated, never overwritten. The path falls inside `content: orgs/*/products/*/context/*.md` of
`tree.md`: no new glob and no resolver row are needed.

The spec carries these five sections, in this order, each with its literal heading:

```
## The piece and its purpose
## Structure and hierarchy
## Content, block by block
## Visual criteria applied
## Gaps and what it does not cover
```

- **The piece and its purpose**: what kind of piece it is, who reads it and in what situation, what
  has to happen after, and the one thing that cannot fail to get across.
- **Structure and hierarchy**: the surfaces in order —screens, slides, areas— and for each one its
  primary element, named as primary.
- **Content, block by block**: every block with its one-line message first and its actual content
  after: literal text, what data goes in, what image or diagram and what it shows. Real copy, never
  filler text.
- **Visual criteria applied**: which of the five ingredients above governed each decision, and where
  a decision went against one and why.
- **Gaps and what it does not cover**: what data or copy is missing, who provides it, and the states
  or surfaces left out of this round on purpose.

## The execution check

**After writing the document, and only then**, it checks whether the session has a tool able to build
this kind of piece — a design integration connected to the harness, such as the Figma MCP, which
covers interfaces and slides.

- **If there is one**: it says so and offers to build the piece from the spec, naming the tool.
  Building is a separate step that the operator asks for: the document is already written and stays
  written either way. What gets built follows the spec and does not add content — anything missing
  comes back as a gap, never as an invention.
- **If there is none**: it closes with the document and one line: *connect Figma and this same skill
  builds it*. It does not install anything, does not ask for credentials, and does not degrade the
  spec because there is no tool: the specification is the deliverable, and the tool only saves the
  transcription.

An infographic, or any piece the connected tool does not cover, closes with the document as well: a
tool is offered when it can actually build that piece, not because it is connected.

## What this deliverable does not claim

The visual spec does not validate that the piece works: that it gets read, understood and acted on is
something only its real reader answers. And it does not decide what the product does — the flow it
specifies comes from the prototype brief of `ideation-engine`, and the scope from `prd`
(`.claude/skills/prd/SKILL.md`).

## Destination

The skill resolves the destination before producing the deliverable, never after. Three cases,
two destinations:

- A product node is loaded: the deliverable goes to `context/<YYYY-MM-DD>-<name>.md` of that node.
- There is a brain, but no product node — no organization yet, or an organization without one: the
  deliverable is written to a file in the current folder.
- There is no brain at all: the deliverable is written to a file in the current folder.

With no product node, the file is written to the current folder anyway, and this line announces it:

the file is loose, nothing filed it, and no session scan will bring it back later.

The way out is named, never taken: `new-org` gives the work an organization, `mount-repo` gives it
a product node. This skill never runs either — it may offer to move the file afterwards, but it
never creates that structure on its own.

This skill never asks which destination to use, and it never invents a third one.

The rest of the pack installs one skill at a time. Look at `.claude/skills/` first and offer only
the ones that are not there:

- `grill` — `npx skills add pedroromeroluna/ai-first-product-skills --skill grill`
- `ideation-engine` — `npx skills add pedroromeroluna/ai-first-product-skills --skill ideation-engine`
- `prd` — `npx skills add pedroromeroluna/ai-first-product-skills --skill prd`

The whole pack at once: `npx skills add pedroromeroluna/ai-first-product-skills`. That command installs what the pack offers;
anything listed above it is installed by naming it.

The system these skills come from is AI First OS —
`github.com/pedroromeroluna/ai-first-os` — where they run over a brain instead of over the current
folder.
