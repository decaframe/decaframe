---
name: decaframe
description: Design and author presentations, slide decks, reports and one-pagers with the decaframe MCP tools (add_template_page, set_page, import_markdown, add_items and the rest). Use when asked for a deck, slides, a pitch, a presentation, a visual report or a document page, or whenever the decaframe tools are connected. Covers which block and style to choose, how to compose a page from rows and columns, how to vary a deck so it reads as designed, and the markdown grammar that lays a whole deck down in one call.
license: UNLICENSED. Commercial; see the decaframe package licence.
metadata:
  author: decaframe
  version: "1"
---

# Designing a deck with decaframe

A document is a sequence of fixed-size pages, each holding blocks that flow down it. **The theme
owns every value** — colour, font, size — and **you own every name**: which block, which style,
which shape, which picture, which surface. A page that merely fits is not finished. A deck whose
every page wears the shelf's defaults is the commonest failure, and it looks like a correct one.

This guide only teaches; the decaframe TOOLS do the work, and nothing exists until a tool reply
says so. There are three ways to author, and the fastest is the third:

1. **Templates.** `list_templates`, `add_template_page` per page, then `set_page` fills every slot
   in one call. Each template's `look` says what it wears; change it in the same `set_page`.
2. **Composition.** `add_blank_page`, then `add_layout` for columns and any block tool (`add_items`,
   `add_chart` and the rest) into a page or a column, with `variant`, `arrangement`, `iconPosition` and `mark` on the write.
3. **Markdown.** `import_markdown` with the grammar below lays down pages, their look and every
   block — the whole deck in one call, or two or three pages per call, since each call appends. Keep
   a call to what you can write in one go. Read `references/grammar.md` when you use it. Fix what
   the reply's diagnostics name, and stop when they stop — the document measures itself.

Names come from `list_blocks`, `describe_block` and the arguments themselves; every wrong name is
refused with the right ones listed, and nothing is written. Never guess an id; read it back.

## Organise the deck

- **One claim per page.** The title IS the claim, a sentence a reader could repeat. The eyebrow
  names the section or the number; the subtitle, when there is one, says what the page shows.
- **A page holds one or two blocks.** A lead line (`text` at `lg`) over a set, a set over a closing
  line (`text` at `sm`), a picture beside its words. `xl` is display size, for a cover's title and
  a one-sentence page; `md` is the default. Three blocks on a page is a page too many.
- **Open, divide, close.** A cover (accent picture behind display-size text, or a dark page), a
  divider for each part on a coloured surface, a closer that ends in an action or a contact.
- **Rhythm.** No two adjacent pages with the same block in the same style. Alternate a paper page
  with a tinted one; put the deck's one `solid-accent` or `gradient-card` where the numbers are;
  use `mode=dark` for the cover, the closer, or one page that must land, never for a run of pages.
- **Density is measured, not guessed.** Count ranges are what a page is designed for; text that
  overflows comes back as a diagnostic with the remedy. Prefer fewer items with a sentence each to
  many with a phrase each, and never pad a set to reach a shape.
- **Emphasis is singular.** `emphasis` on the ONE item a page is about, or on none.

## Rows and columns

- **A grid is already columns.** A `box` at three or four, a `stat-row`, `steps` across — these lay
  their items side by side. Reach for a layout only when each column needs its OWN block: a heading
  with a list against another, a chart beside the sentence about it, a picture beside its words.
- **`two-cols` for a pair of equal weight** — a claim and its evidence, before and after, ours and
  theirs. `three-cols` when each of three needs a heading of its own; at `four-cols` and
  `five-cols` a column holds a mark and a line, not a sentence. Nothing nests.
- **A column holds one or two blocks**, never a grid — a grid inside a column is a column of one.
- **Rows are the page's flow.** Blocks stack top to bottom in reading order; a stat row IS a row;
  a `list`-shaped block is one item per row at full width, which is where a paragraph per item goes.
- **A picture down one side is the page's accent, not a column.** `accent=lead` or `trail` with
  the picture on `set_page` divides the page and text cannot enter it; `top` is a banner for a wide
  photograph; `full` puts the picture behind everything with the words over it.

## Choose the block, then the style

Every block sharing an archetype takes the same content, so a `box` becomes `steps` for free with
`set_block_type` — choose by MEANING. A set with no order is a `box`; ordered stages are `steps`;
dated events a `timeline`; two to five headline numbers a `stat-row`; compared numbers a `chart`;
what connects to what a `diagram`; values at the crossing of two things a `table`; and a passage
is prose, one paragraph per block.

A **shape** changes how much fits and what the block claims: a `funnel` narrows, a `pyramid`
rests, a `ring` cycles, a `road` journeys, a `climb` ascends, a `core` contains. Choose the one
whose claim is true, and only then check the count. A **figure** (starred below) refuses a count
outside its range. A **style** is paint the theme resolves, the same name under every theme:
bordered or filled or lifted, a bar on the leading edge, a header on the accent. Pair a filled
style with a paper page and a bordered one with a tinted page, and let one style carry a section.

<!-- generated: do not edit between these markers; `pnpm skill` rewrites them -->

### Every block

Prose blocks — `text` (md/lg/xl/sm), `heading`, `bullets`, `numbered`, `quote`, `checklist`, `separator`, `code` — go through `add_prose` or plain markdown. The rest:

| Block | What it is | Items | Shapes (*figure = illustrated, count is a LIMIT) | Styles besides `plain` | Marks |
|---|---|---|---|---|---|
| `box` | Icon-led boxes, as a grid or a list. At one, a callout. | 1–9 | grid 1–9, list 2–6 | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, header-band, accent-header | — |
| `steps` | A numbered sequence — across, as a staircase, a funnel, a pyramid, or a ring. | 2–6 | across 2–6, list 2–6, staircase 2–5, funnel 2–5, pyramid 2–5, ring 2–5, road* 3–4, climb* 3–5, core* 3 | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, marked | numeral, icon, none |
| `timeline` | Dated milestones on a vertical rail. | 3–8 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, marked | dot, icon |
| `stat-row` | A row of large figures. | 2–5 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `image` | One picture, with an optional caption. | 1 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `image-grid` | Two to six pictures in a grid. | 2–6 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `image-with-text` | One picture on the left, a heading and a paragraph beside it. | 1 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `table` | A grid of rows and columns with a header row. | 2–9 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, banded, header-band | — |
| `people` | Two to eight people, each a portrait with a name, a role and a line. | 2–8 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `youtube` | One YouTube video, with an optional caption. | 1 | — | accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner | — |
| `chart` | A chart of one or more named series over shared categories. | 2–11 | column 2–11, bar 2–15, line 2–11, area 2–11, pie 2–6, donut 2–6, waterfall 2–11, heatmap 2–11 | — | — |
| `diagram` | A diagram, written as mermaid text. | 1 | — | — | — |

Icon position on a block that draws icons: top, lead, none. A page's accent picture sits top, lead, trail, full; its surface is subtle, muted, accent or the theme's paper; its mode is light or dark.

### What each style looks like

- `plain` — the theme's own default
- `accent-bar` — a bar down the leading edge
- `soft-fill` — a tinted plane, no border
- `outlined` — a border on four sides, no fill
- `top-rule` — a coloured line across the top
- `side-rule` — tinted, bordered, with a bar on the leading edge
- `raised-card` — a lifted card with a soft shadow
- `gradient-card` — a card over a gradient
- `solid-accent` — filled in the accent colour, ink flipped
- `leaf-corner` — three corners round, one square
- `banded` — alternate rows tinted (table)
- `header-band` — the header row on its own plane (box, table)
- `accent-header` — eyebrow and title on the accent, body on paper (box)
- `marked` — the numeral or dot in a filled disc (steps, timeline)

### What each shape claims

- `box` · `grid` (1–9): Boxes side by side, three to a row, so a set reads as a set.
- `box` · `list` (2–6): One box per line, each the whole width of the frame — so it holds about HALF AGAIN what a grid cell does at two or three entries.
- `steps` · `across` (2–6): Numbered steps side by side with a line running between them, so the eye reads left to right.
- `steps` · `list` (2–6): Steps stacked down the page at the FULL width, one per line, with the numeral beside the title.
- `steps` · `staircase` (2–5): Steps stacked down the page, each one offset further across than the last, so the shape itself says "and then".
- `steps` · `funnel` (2–5): Stacked bands, each NARROWER than the one above, for a sequence that filters something down — a pipeline, a qualification flow, an audience narrowing to a customer.
- `steps` · `pyramid` (2–5): Stacked bands, each WIDER than the one above, for a structure that rests on what is underneath it — a hierarchy of needs, a foundation-then-refinement argument, a maturity model.
- `steps` · `ring` (2–5): A closed cycle, for a sequence whose last step feeds the first — a feedback loop, a flywheel, a lifecycle.
- `steps` · `road`* (3–4, a LIMIT): A winding path with a stop for each item, for a journey or a plan with a beginning and an end — prefer this over `arrangement` when the picture itself is part of the point, never for a process where the steps are interchangeable in order.
- `steps` · `climb`* (3–5, a LIMIT): A rise to a goal — each stop stands higher than the last on a slope that climbs to the right, so the picture itself says the final item is the summit.
- `steps` · `core`* (3, a LIMIT): Layers around a core, for things that CONTAIN one another — a platform with what is built on it, a team inside a company inside a market, a scope widening outward.
- `chart` · `column` (2–11): Vertical bars, one group per category.
- `chart` · `bar` (2–15): The same comparison lying on its side.
- `chart` · `line` (2–11): A value followed ACROSS the categories rather than compared between them — months, quarters, versions, anything with an order a reader already knows.
- `chart` · `area` (2–11): The line with the ground under it filled in, for a total that ACCUMULATES rather than a value that merely moves — revenue by quarter, users by month, anything where the area under the curve is itself a quantity.
- `chart` · `pie` (2–6): ONE series, drawn as parts of a whole.
- `chart` · `donut` (2–6): The pie with its middle removed, and it says the same thing: ONE series, drawn as parts of a whole that add up.
- `chart` · `waterfall` (2–11): THE VALUES ARE STEPS, NOT TOTALS — this is the one shape on the shelf where that is true, and typing running totals into it draws the wrong picture entirely.
- `chart` · `heatmap` (2–11): THE MATRIX THE PAYLOAD HAS BEEN ALL ALONG: one ROW per series, one COLUMN per category, and each cell shaded by its value.

### Layouts

- `two-cols` (2 regions): Two things of equal weight side by side — a claim and its evidence, before and after, or a picture beside the words about it.
- `three-cols` (3 regions): Three parallel things that each need a block of their own rather than one entry.
- `four-cols` (4 regions): Four parallel things, each about a QUARTER of the frame — a logo row, four figures, a quarter-by-quarter split.
- `five-cols` (5 regions): Five parallel things.

### Icons, by shelf

- Technology: cpu, database, server, cloud, terminal, network, layers, boxes, signal, zap
- Process & work: workflow, branch, route, activity, clock, calendar, clipboard, filter, package, wrench
- Trust & risk: lock, shield, alert, scale, key, bug, eye, gavel, bell, gauge
- Business & money: globe, search, trend, coin, wallet, briefcase, receipt, tag, cart, building
- People & communication: radio, user, users, handshake, message, mail, phone, megaphone, heart, award
- Ideas & direction: target, rocket, flag, compass, map, lightbulb, sparkles, puzzle, trophy, star
- Fields & sectors: book, flask, leaf, pill, truck, factory, house, plane, store, landmark

<!-- /generated -->

## Icons and marks

Give every item of a block an icon or give none; a set where some have icons reads as unfinished.
Pick from one shelf per block so they read as a family. On `steps` and `timeline` the **mark** is
what the items are marked with — a numeral, a dot, the item's own icon — and `marked` is the style
that sets the mark apart in a filled disc.

## Pictures, video, charts, diagrams

A picture needs a real https address; there is no upload, and a page renders an empty frame until
one arrives. `image` carries the point alone; `image-with-text` needs its words; `image-grid` is
a set; `people` is a roster with a name, a role and a line each; `youtube` is one video. A chart
takes `{categories, series}` — pick its kind by what the numbers DO: `column` compares, `line`
follows, `area` accumulates, `pie` and `donut` are one series of shares, `waterfall` is steps
not totals, `heatmap` is the matrix the payload already is. A diagram is mermaid text; write the
relationships and let the engine place the boxes. Always write the sentence a chart or diagram
is there to prove, above or below it.

## Write it as markdown

```markdown
# The three-stage rollout
::page: eyebrow="Rollout" surface=muted::

::text: arrangement=lg::
Each stage was a gate for the next.

::steps: arrangement=staircase variant=top-rule::
### Dogfood {icon=users meta="April"}
Every employee on the new flow.
### Ten percent {icon=filter meta="May" emphasis}
One flag from rollback.
### Everyone {icon=rocket meta="June"}
The old flow retired.
::end::
```

A `#` heading or a `::page…::` line starts a page; a block marker opens a block and the headings
under it are its items; `::end::` closes it. The full grammar, every marker and key, is in
`references/grammar.md`; every block's complete guidance is in `references/catalogue.md`.

## Before you finish

- Every page has a title that is a claim, and no page has three blocks.
- No two adjacent pages share a block and a style; the deck has a cover, dividers and a closer.
- Every set has icons on all items or none; every figure's count is inside its limit.
- Every picture has a real address; every chart and diagram has its sentence.
- `get_document` reports no diagnostic, and you did not add words to fill space.
- You read the document back and every page is in it. A page you have not read back does not
  exist, and saying it does is the one failure nothing here can catch.
