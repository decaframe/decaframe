---
name: decaframe
description: Author presentations, slide decks, reports and one-pagers with the decaframe MCP tools. Use when asked for a deck, slides, a pitch, a presentation, a visual report or a document page, or whenever the decaframe tools are connected. Describes what a decaframe document is, how a page is built from rows and columns, every block with its styles and shapes, the templates, how a deck moves when it is presented, and what each tool reply reports back.
license: UNLICENSED. Commercial; see the decaframe package licence.
metadata:
  author: decaframe
  version: "2"
---

# Decaframe, described

A decaframe document is a sequence of fixed-size pages — 16:9 unless `set_document` says
otherwise — each holding blocks that flow down it. The theme owns every value: colour, font,
size, spacing. The document holds names: which block, which style, which shape, which picture,
which surface. A name means the same thing under every theme, so swapping the theme repaints a
deck without touching it. Everything is addressed by a stable id that `get_document` reports; a
position or an index is never an address.

This file describes what exists. The tools do the work, and nothing exists until a tool reply
says so.

## How a page is built

A page is a stack of rows in reading order. At the top sits its chrome — an eyebrow, a title, a
subtitle — set by `add_blank_page` or `set_page`; below that come its blocks, each a row of its
own at the full width of the frame.

A row can instead be a layout of columns. `add_layout` divides one row into `two-cols`,
`three-cols`, `four-cols` or `five-cols`; each column is a region holding its own stack of one or
more blocks, and the columns are addressed col-1 onward in reading order. Nothing nests: a
layout holds blocks and never another layout. A block whose arrangement is a grid — a `box` at
three, a `stat-row`, `steps` `across` — already lays its items side by side, so a layout is for
a row whose columns each need a block of their own: a picture beside its words, a chart beside
the sentence about it, a heading and list against another. Two columns hold a pair of equal
weight; at four and five a column is narrow enough that it holds a mark and a line rather than a
paragraph.

A page accent is a picture pane, not a column. `lead` and `trail` reserve one side of the page
for a picture and text does not enter it; `top` is a banner; `full` puts the picture behind
everything with the words over it. A page also carries a surface — `subtle`, `muted` or
`accent` — and a mode, `light` or `dark`, of its own, or inherits the document's.

## Page and document properties

A page's chrome is three optional lines — an eyebrow, a title and a subtitle — each set on
`add_blank_page` or `set_page` and removed by passing an empty string, so a page can carry no
title at all: a full-bleed picture cover, a single quotation, a closing line. A page also has
`notes` (the presenter's own markdown, shown in the presenter view and never on the slide), a
`mode` override, a `surface`, and an `accent` with its `accentSrc` and `accentAlt`; null on any
of these hands it back to the document. `before` on `add_blank_page` and `add_template_page`
places a page ahead of another by id, and on every block tool places a block ahead of another.

The document, through `set_document`: a `title` (its name, drawn on no page); a `format` — 16:9,
4:3, A4 as a portrait sheet, or fluid, where pages grow with their content and nothing can
overflow; an `align` for where blocks sit in a page's leftover height — top, middle or bottom;
and a `mode`; and motion, described in its own section below. The theme belongs to the account
and is not chosen here. Page
furniture — the footer's words and mark — is a person's setting in the editor and is not on the
tool surface.

## Motion

A document can move while it is presented — in the exported file and in the editor's presentation
mode — and never while it is edited. Motion is names, not numbers: you choose what happens and the
stylesheet decides how long it takes.

Four names on `set_document`, each with a default that is the plainest choice:

- `transition` — how one page gives way to the next: slide (the default), fade, zoom or none.
- `animate` — how blocks enter a page: none (the default), fade, rise (a fade with a small
  lift) or grow (a fade from slightly small). With animate set, blocks enter in reading order,
  one after another.
- `build` — when blocks enter: arrive (the default: every block with the page) or click (one
  block per keypress, the way a presenter walks a slide). Under click the deck advances through a
  page's blocks before it moves to the next page, and going back re-hides them one at a time; a
  page reached backwards arrives fully shown.
- `pace` — how quickly all of it plays: slow, medium (the default) or fast.

A page may override `animate`, `build` and `pace` through `set_page`; null hands the choice back
to the document. A page with build set to click and nothing set on the document is a common
shape: the deck flows, one page builds.

One name on a prose block, `reveal`, set through `add_prose` or `update_prose` and cleared with
none: words shows the text one word at a time, type types it out character by character, and
click makes each item of a list its own step, so a bulleted argument lands point by point. A
reveal obeys the page's build — under arrive it plays when the page lands, under click it plays
when the block's own click comes. The reveal's own look is the page's `animate`, or a fade when
that is none.

What a reader sees: an entrance begins only once its page has settled on screen, a block enters
exactly once, and someone who has asked their system for reduced motion gets every step and reveal
with no movement at all. The presenter view shows how many of a page's steps are revealed.
`get_document` reads every motion name back; nothing about motion is reported as a diagnostic,
because motion cannot make a page overflow.

## Three ways to author, and what each gives you

- **A template page.** `list_templates` describes every composed page the shelf holds: its
  blocks, its shape and its look, and when it suits. `add_template_page` adds one, and `set_page`
  fills every slot of it in one call — the same call can change any block's style or shape. A
  template's look is a starting arrangement, not a constraint.
- **A page of your own.** When no template suits, `add_blank_page` opens an empty page and the
  block tools — `add_items`, `add_stats`, `add_media`, `add_chart`, `add_diagram`, `add_table`,
  `add_prose` — place blocks on it or in a column of an `add_layout`, with `variant`,
  `arrangement`, `iconPosition` and `mark` on the write. A page built this way is as complete as
  a template page; the shelf is a convenience, not a boundary.
- **Markdown.** `import_markdown` lays down pages from text; its grammar is on the tool's own
  description.

Afterwards, `set_block_type` swaps a block for another of the same archetype and keeps its
content; the update tools (`update_items`, `update_prose` and the rest) rewrite content in place; `set_layout` changes a row's columns;
`remove_block` and `remove_page` take things away. Names come from `list_blocks`,
`describe_block` and the arguments themselves.

## Blocks, styles and shapes

Every block belongs to an archetype, and every block sharing one takes identical content — which
is what lets `set_block_type` turn a `box` into `steps` with nothing rewritten. A set with no
order is a `box`; ordered stages are `steps`; dated events a `timeline`; two to five headline
numbers a `stat-row`; compared numbers a `chart`; what connects to what a `diagram`; values at
the crossing of two things a `table`; a passage is prose, one paragraph per block, and a `text` block
has four sizes — `sm`, `md`, `lg` and `xl`, the last being display size for a cover's one line.

A **shape** (the `arrangement`) changes how much fits and what the block claims: a `funnel`
narrows, a `pyramid` rests, a `ring` cycles, a `road` journeys, a `climb` ascends, a `core`
contains. A **figure** is an illustrated shape, and its count range is a limit: a write outside
it is refused. A **style** (the `variant`) is paint the theme resolves, the same name under every
theme — bordered or filled or lifted, a bar on the leading edge, a header on the accent. A filled
style reads against a paper page and a bordered one against a tinted page.

<!-- generated: do not edit between these markers; `pnpm skill` rewrites them -->

### Every block

Prose blocks — `text` (md/lg/xl/sm), `heading`, `bullets`, `numbered`, `quote`, `checklist`, `separator`, `code` — go through `add_prose`, one line per block. The rest:

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

Icon position on a block that draws icons: top, lead, none. A page's accent picture sits top, lead, trail, full; its surface is subtle, muted, accent or the theme's paper; its mode is light or dark. Motion is named, never timed: a document's transition is slide, fade, zoom, none; blocks animate none, fade, rise, grow and build by arrive or click at a pace of slow, medium, fast; a prose block reveals by words, type, click.

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

An item of a `box`, `steps` or `timeline` can carry an icon from the shelves above, and a set
reads as a family when its icons come from one shelf and as unfinished when some items have one
and others none. On `steps` and `timeline` the **mark** is what the items are marked with — a
numeral, a dot, the item's own icon — and `marked` is the style that sets the mark apart in a
filled disc. `emphasis` on an item is the one the page is about.

## Pictures, video, charts, diagrams

A picture is an https address; there is no upload, and a page renders an empty frame until one
arrives. `image` carries a point alone; `image-with-text` pairs a picture with its words;
`image-grid` is a set of pictures; `people` is a roster with a name, a role and a line each;
`youtube` is one video. A chart takes `{categories, series}`, and its kind says what the numbers
do: `column` compares, `line` follows, `area` accumulates, `pie` and `donut` are one series of
shares, `waterfall` is steps rather than totals, `heatmap` is the matrix the payload already is.
A diagram is mermaid text — the relationships written down, with the engine placing the boxes.

## What the tools report back

Every reply says whether it went through. A refusal names its subject, the reason and the valid
names, and nothing is written; a wrong block, style, shape, icon or id is refused this way rather
than guessed at.

A write reply carries the page as it now stands, and its diagnostics: each names a code, the
page, the block where there is one, and a message that says what is wrong and the change that
fixes it. A missing slot, a count outside a range, an empty page and the placeholder block a new
document starts with are structural diagnostics, and while one stands the page's fit is not
measured — the reply says so in as many words.

Pages are a fixed size, so after every write the page is rendered and measured against its
frame. A page that runs over is drawn smaller to fit, down to a floor of 80% of full size, and
the reply carries an advisory saying at what size it is drawn. Past the floor the page is still
over, and a pageOverflow diagnostic says how many pixels past the frame it runs, names the
tallest slot or the block that would move to the next page, and — on the write after — says
whether that number went down, up or did not move at all. No fit field on a reply means the
page was measured and fits. A fit field means the page could not be measured: its diagnostics
are still open, the document is fluid and cannot overflow, or the renderer had a problem.

A page can also come back with a fill advisory — the page uses little of its frame — which is
information and asks for no action; a divider or a single quotation is sparse on purpose.

`get_document` returns the whole document: every page, every block with its id and archetype,
and every diagnostic at once. It is how ids are learned and how the document is confirmed — a
page that has not been read back is not known to exist. `export_html` writes one self-contained
file; `open_document` points the tools at a different document file.

Every block's complete guidance, and every template with what it wears, is in
`references/catalogue.md`.
