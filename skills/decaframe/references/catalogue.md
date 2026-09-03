# The catalogue, in full

Generated from the code by `pnpm skill`. What `list_blocks` and `describe_block` say, on one page.

## `box` — Icon-led boxes, as a grid or a list. At one, a callout.

Archetype `items` · items 1–9 · draws: icon, meta, title, body

Parallel things with no order and no dates — features, capabilities, sources, destinations. The default when items are a set rather than a sequence. Pick the `arrangement` for how much each one has to say: `grid` for captions, `list` for real prose. A body may hold a short list — lines led by "- " become bullets, which is how a feature card or a comparison column carries its points. `meta` is an optional EYEBROW — a small label above the title naming its kind or category; give it to every box or to none. Prefer `steps` when the order is the point, since this block draws no numbers and implies no sequence.

Shapes:

- **grid** (1–9): The default. Boxes side by side, three to a row, so a set reads as a set. At a count of ONE it is a callout — a single point set apart. At TWO or THREE it is also how a COMPARISON is written: one column per option, the title naming it and the body holding that option's points, one per line — a newline in a body is a line break. Note that FOUR is two rows of two rather than four columns, so a four-way comparison reads as a square; keep one to three columns or use `table` when the options share their criteria.
- **list** (2–6): One box per line, each the whole width of the frame — so it holds about HALF AGAIN what a grid cell does at two or three entries. The shape for FEW things said at LENGTH: propositions with a paragraph each, principles, objections and answers. Prefer the grid once there are four or more: by six a row holds LESS than a cell, not more. At five and six the body moves BESIDE the title instead of under it, so keep titles to a few words.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, header-band, accent-header.

## `steps` — A numbered sequence — across, as a staircase, a funnel, a pyramid, or a ring.

Archetype `items` · items 2–6 · draws: title, body, icon

Ordered stages where the order is the point — a process, an onboarding, a how-it-works. It draws its own numbering, so do NOT put "1." or "Step 1" in the titles. Pick the `arrangement` for what the sequence MEANS: `across` when each step has real prose, `staircase` when the progression is the point, `funnel` when each stage narrows the last, `pyramid` when each level rests on the one below it, `ring` when the last step feeds the first. `funnel` and `pyramid` hold the same amount and differ in where the long text goes — the top of a funnel, the bottom of a pyramid. `ring` holds the least of the five.

Shapes:

- **across** (2–6): The default. Numbered steps side by side with a line running between them, so the eye reads left to right. The most room per step of the three, and the only shape that keeps the frame's full height — prefer it whenever each step has a sentence or more to say. At six it wraps to two rows of three.
- **list** (2–6): Steps stacked down the page at the FULL width, one per line, with the numeral beside the title. The plain stack: it says the steps are in order and claims nothing else, which is what makes it the one to reach for when the sequence is ordinary — a procedure, a set-up, an agenda. It holds MORE than any other stacked shape at the same count, because a full-width band wraps its body in fewer lines, and it is the only shape here that runs to six. Use `staircase` instead when the progression itself is the message, and `across` when there are few steps and each has a paragraph to say.
- **staircase** (2–5): Steps stacked down the page, each one offset further across than the last, so the shape itself says "and then". Every tread is the same size, so every step holds the same. It holds about HALF what `across` does at the same count — a band is shorter than a full-height column and the offset costs width on top — so use it when the SEQUENCE is the message and each step is a short label with a line of explanation. At five, that is literally one line each; at two and three there is room for two or three.
- **funnel** (2–5): Stacked bands, each NARROWER than the one above, for a sequence that filters something down — a pipeline, a qualification flow, an audience narrowing to a customer. The bottom band is about half the width of the top, so the size below is what the NARROWEST step holds and every step is safe at it; the top band will take nearly twice that. Put the long text at the TOP. If the steps are not narrowing something, use `across`.
- **pyramid** (2–5): Stacked bands, each WIDER than the one above, for a structure that rests on what is underneath it — a hierarchy of needs, a foundation-then-refinement argument, a maturity model. Item one is the apex and the LAST item is the base, which is both the widest band and the most foundational thing you are saying. Put the long text at the BOTTOM. It holds exactly what `funnel` holds, so pick between them on what the sequence MEANS: a funnel filters something down, a pyramid builds something up.
- **ring** (2–5): A closed cycle, for a sequence whose last step feeds the first — a feedback loop, a flywheel, a lifecycle. The steps sit round a circle with the connector closing it, so the shape itself says "and then it starts again"; use one of the other shapes if the sequence ENDS, because a ring claims it does not. It holds the least of any shape here by a wide margin — a circle in a wide frame leaves the sides empty, and the room goes to the diameter — so each step is a label and a line, never a paragraph.
- **road** — a figure (3–4, a limit): A winding path with a stop for each item, for a journey or a plan with a beginning and an end — prefer this over `arrangement` when the picture itself is part of the point, never for a process where the steps are interchangeable in order. Setting a figure clears any stored arrangement — the two are exclusive, never combined.
- **climb** — a figure (3–5, a limit): A rise to a goal — each stop stands higher than the last on a slope that climbs to the right, so the picture itself says the final item is the summit. Use it when the ASCENT is the message: growth, a maturity model, levels of a plan, a target being approached. Prefer `road` when the point is a journey with stops rather than a rise, and the `staircase` arrangement when you want plain boxes and no drawing. Setting a figure clears any stored arrangement — the two are exclusive, never combined.
- **core** — a figure (3, a limit): Layers around a core, for things that CONTAIN one another — a platform with what is built on it, a team inside a company inside a market, a scope widening outward. Item one is the CORE and sits innermost; each item after it wraps around the one before, so put the most fundamental thing FIRST. Prefer `climb` when the last item is the goal rather than the outside, and the `pyramid` arrangement when levels REST on each other instead of surrounding each other. The INNERMOST layer is the smallest circle and holds the least — a short title and one line — so put the longest words on the OUTER layers. Setting a figure clears any stored arrangement — the two are exclusive, never combined.

Marks: numeral, icon, none (the first is the default).

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, marked.

## `timeline` — Dated milestones on a vertical rail.

Archetype `items` · items 3–8 · draws: meta, title, body, icon

Events anchored to a date or period, in chronological order. The date goes in `meta`. If the items are ordered but undated, use `steps` instead.

Marks: dot, icon (the first is the default).

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, marked.

## `stat-row` — A row of large figures.

Archetype `stats` · items 2–5 · draws: value, label, note

Headline numbers — metrics, traction, results. `value` is the large figure and is the only required slot in the whole catalogue; `label` names it, `note` qualifies it. Write `value` SHORT — about five or six characters sit on one line, so `1.2M`, `340ms` and `99.98%` read as figures where `1,200,000` and `$18,400` wrap onto a second.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `image` — One picture, with an optional caption.

Archetype `media` · items 1 · draws: src, alt, caption

A photograph, screenshot or diagram that carries the point on its own. `src` is the full web address of an image that is ALREADY online — there is no upload, and a file path or a relative path is refused. `alt` describes the picture for someone who cannot see it; `caption` is printed under it and is read by everyone, so do not put the same words in both. THE EXAMPLE'S ADDRESS IS A PLACEHOLDER and serves no image: replace it with a real one, or the page renders an empty frame and the export fails.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `image-grid` — Two to six pictures in a grid.

Archetype `media` · items 2–6 · draws: src, alt, caption

Several pictures that belong together — a set of screenshots, product shots, or places. Each entry is its own picture with its own `src` and `alt`, exactly as `image` takes them, and there is no upload. `caption` is optional per picture and is printed under it; leave it out and the picture simply has none. The layout changes with the count, so send the pictures you mean and do not pad the list to reach a shape. THE EXAMPLE'S ADDRESSES ARE PLACEHOLDERS and serve no image: replace them with real ones, or the page renders empty frames and the export fails.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `image-with-text` — One picture on the left, a heading and a paragraph beside it.

Archetype `media` · items 1 · draws: src, alt, title, body, caption

A picture that needs explaining — a screenshot with the point spelled out, a photograph with its story. `title` is the heading beside the picture and `body` the paragraph under it; both are read as the content, so put the argument there rather than in `caption`. `caption` is optional and prints small under the picture, for a credit or a place and date. Use `image` instead when the picture carries the point on its own. THE EXAMPLE'S ADDRESS IS A PLACEHOLDER and serves no image.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `table` — A grid of rows and columns with a header row.

Archetype `table` · items 2–9 · draws: headers, rows

Values that only make sense at the crossing of two things — a specification, a price list, a schedule, a set of measurements. `headers` is the top row of column headings and `rows` is a list of rows, each a list of cell text in the SAME ORDER as the headings; every row needs the same number of cells, and '' is a blank one. Send `headers` as an empty list for a table with no header row. Keep cells to a few words — a table is for scanning, and a sentence in a cell belongs in a `box` instead. You cannot join two cells into one: a person can do that in the editor, and if one has been joined its text belongs to the row and column it starts at, with the cells it covers left empty.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner, banded, header-band.

## `text` — A paragraph.

Archetype `prose` · items 1 · draws: text

Running text — an argument, a summary, a definition. The default when the content is sentences rather than a set of parallel things. Each paragraph is its own block, so send several in one add_prose call rather than packing them into one.

Shapes:

- **md** (1): The default. Body copy — the size everything else on the page is judged against.
- **lg** (1): One opening paragraph that sets up the page, or a single sentence a page is built around. It holds about half what normal text does, so it is for a lead rather than a passage — a whole page at this size does not fit.
- **xl** (1): A few words that ARE the page — a section divider, a closing line, the one sentence a deck turns on. A phrase, never a paragraph: it holds about a quarter of what large text does. Put it on a page with NO title, because at this size the block and the page heading compete and the block is the one carrying the words.
- **sm** (1): A footnote, a caveat, a source line — text that must be present and must not compete. Holds more than normal, which is not a reason to reach for it: small text nobody reads is worse than text that did not fit.

## `heading` — A heading inside the page body.

Archetype `prose` · items 1 · draws: text

Sits BELOW the page's own title, which is set with add_blank_page or set_page — use that for the title itself. This is for sectioning a long passage. `level` is 1 to 6 exactly as markdown's `#` to `######` are, and it defaults to 3 — so a document that says nothing about levels reads as it always has. Use 1 and 2 for a page that IS a section opener, and 4 to 6 only where a real outline needs the depth: they differ from each other in weight rather than size, because a 16:9 frame has no room for six visible steps.

## `bullets` — A bulleted list.

Archetype `prose` · items 2–10 · draws: text

Short parallel points that need no heading of their own — caveats, requirements, takeaways. Consecutive `bullets` lines in one add_prose call join into a single list. If each point deserves a heading AND a sentence, it is a box or steps, not a list.

## `numbered` — A numbered list.

Archetype `prose` · items 2–10 · draws: text

A sequence where the order is the point but the steps need no separate description. If each step wants a title and a sentence, use the `steps` block instead — it is designed for it.

## `quote` — A pull quote and its source.

Archetype `prose` · items 1 · draws: text, attribution

One passage worth reading slowly — a customer sentence, a principle, a finding. The speaker or source goes in this block's `attribution`, NOT in a separate block: they are one thing with two parts, and nothing should have to infer which quote a source belongs to.

## `people` — Two to eight people, each a portrait with a name, a role and a line.

Archetype `media` · items 2–8 · draws: src, title, body, caption

People, when there are several of them — a team, a board, a speaker line-up, the customers on a logo wall, the contributors to a release. `title` is the PERSON'S NAME; `caption` is their role or company, one short line, and it prints above the name; `body` is a sentence or two about them. Do not put the role in `body` as well — the two say different things and repeating one in the other is what makes a roster read as filler. The layout changes with the count: two or three get a wide picture and room for a paragraph, four to six a row of headshots, seven or eight a two-column list with a small thumbnail, so send the people you mean rather than padding to a shape. Use `image-with-text` for ONE person with a lot to say about them. `src` is the full web address of a photograph that is ALREADY online — there is no upload. THE EXAMPLE'S ADDRESSES ARE PLACEHOLDERS and serve no image: replace them with real ones, or the page renders empty frames and the export fails.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `checklist` — A list of things to tick off.

Archetype `prose` · items 3–10 · draws: text

Items with a DONE state — a checklist, an agenda you tick through live, acceptance criteria, a launch list. Set `checked` per line; it is the only prose block that reads it, and reading the document back and writing it unchanged preserves whatever a human ticked. Use `bullets` when nothing is ever completed and `numbered` when the ORDER is the point — a checklist implies neither sequence nor priority. Do not put "[ ]" or "done" in the text: the box is drawn and `checked` is what says so.

## `youtube` — One YouTube video, with an optional caption.

Archetype `media` · items 1 · draws: src, alt, caption

A YouTube video that carries the point — a demo, a talk, a customer saying it themselves. `src` is the address of the video, copied from the browser on its own page: a 'youtube.com/watch?v=…', a 'youtu.be/…', a '/shorts/…' or an '/embed/…' address. Only YouTube, and only ONE video — a playlist address names no single video and is refused. THE PAGE DRAWS THE VIDEO'S OWN STILL FRAME, so there is no picture to find and no `poster` to send; `alt` describes the video for someone who cannot see that frame, and `caption` prints under it and is read by everyone, so do not put the same words in both. In an exported file the still frame links out to YouTube rather than playing in place. Use `image` for a picture — a YouTube address sent there is refused by name.

Styles: plain, accent-bar, soft-fill, outlined, top-rule, side-rule, raised-card, gradient-card, solid-accent, leaf-corner.

## `separator` — A horizontal rule.

Archetype `prose` · items 1 · draws: nothing but itself

A break between two parts of one page — markdown's `---`. It holds NO TEXT: send it as a line with a `kind` and nothing else, and `text` on it is refused rather than dropped. Use it sparingly on a page that is already a fixed frame: a rule between two paragraphs is usually a second page, and a rule above a heading is what the heading already does.

## `code` — A block of code, in a monospace face.

Archetype `prose` · items 1 · draws: text

Source code, a command, a configuration snippet — markdown's fenced ``` block. Newlines in `text` are real line breaks and are kept exactly, so send the code as it should read. `language` is the fence's tag (`js`, `python`, `sql`); it is stored and travels with the document, and NOTHING COLOURS IT — we ship no syntax highlighter, so the language is metadata rather than an appearance. For a word or two of code inside a sentence, use the inline code mark instead of a block of its own.

## `chart` — A chart of one or more named series over shared categories.

Archetype `chart` · items 2–11 · draws: title, axisX, axisY

Numbers that are COMPARED rather than listed — a trend, a split, a ranking. The payload is ONE shape for every chart: `categories` are the labels along the axis, and each entry in `series` is one named line of numbers whose `values` line up with them EXACTLY, one per category, with `null` for a gap. At most six series, because that is how many colours a theme answers for. Pick the drawing with `arrangement` and the stacking with `stack`. The title and the two axis titles are ordinary editable text and are NOT part of the payload. For numbers that are only being listed, use `table`; for two or three headline figures, use `stat-row`.

Shapes:

- **column** (2–11): Vertical bars, one group per category. The default, and the right answer for comparing a handful of named things — revenue by product line, headcount by team. Set `stack` to `stacked` to put the series in ONE bar rather than side by side, or `proportional` to make every bar the same height and read the SHARES instead of the totals. Past eleven categories the axis starts hiding labels — use a bar, which has room for more.
- **bar** (2–15): The same comparison lying on its side. Reach for it when the CATEGORY NAMES are long or there are many of them — a bar grows DOWN the page, so it has room for names a column chart would hide or turn on their side, and it takes half as many again before it runs out. It is also the natural shape for a RANKING, because a reader scans a list downward.
- **line** (2–11): A value followed ACROSS the categories rather than compared between them — months, quarters, versions, anything with an order a reader already knows. The line makes the SHAPE of the change the subject: what rose, what flattened, where two series crossed. Use a column chart instead when the categories have no order, because a line drawn between unordered things invents a trend. A `null` BREAKS the line rather than being drawn through, so a month nobody recorded reads as a gap and never as a measurement. Past eleven categories the axis starts hiding labels, exactly as a column chart does.
- **area** (2–11): The line with the ground under it filled in, for a total that ACCUMULATES rather than a value that merely moves — revenue by quarter, users by month, anything where the area under the curve is itself a quantity. Use a plain line when the series are being COMPARED, because two filled areas overlap and a line never does. Set `stack` to `stacked` to show the parts adding up to a whole that changes over time — the one thing on this shelf a stacked column cannot say — or `proportional` to read the SHARES instead. It inherits the line's rule about a gap: a `null` BREAKS the band rather than being drawn through. DO NOT STACK A SERIES THAT HAS GAPS: a missing value is left OUT of the total, so every band ABOVE it drops to the baseline for that one category and the picture reads as all of the series collapsing together when only one reading is absent. Fill the gap or use a plain area. Past eleven categories the axis starts hiding labels, exactly as a line and a column do.
- **pie** (2–6): ONE series, drawn as parts of a whole. Use it only when the numbers really are shares of something and the point is that they add up — never to compare separate measures, which is what a column chart is for. A second series is REFUSED rather than quietly dropped. Past about six slices the wedges stop being tellable apart, so the count range is short on purpose; for more categories than that, use a bar.
- **donut** (2–6): The pie with its middle removed, and it says the same thing: ONE series, drawn as parts of a whole that add up. Choose it over a pie when the slices are LABELS being read rather than areas being compared — the ring is calmer on a page and the words sit further from each other — and choose the pie when a reader has to judge one share against another, because a wedge with its point cut off is harder to compare by area. A second series is REFUSED, exactly as on a pie. DO NOT PUT THE TOTAL IN THE HOLE: nothing is drawn there on purpose, because text inside the plot would scale with the drawing instead of reflowing — put it in the `title` slot, which is ordinary text. Past about six slices the ring stops being tellable apart, so the count range is short on purpose; for more categories than that, use a bar.
- **waterfall** (2–11): THE VALUES ARE STEPS, NOT TOTALS — this is the one shape on the shelf where that is true, and typing running totals into it draws the wrong picture entirely. Each bar starts where the last one ended, so `[120, 40, -25, 15]` is a balance of 120 that gains 40, loses 25 and gains 15, ending at 150. Reach for it to show how a total GOT to where it is — opening balance to closing balance, budget to actual, last year's revenue bridged to this year's — where a column chart would show the ends and hide the middle. ONE series: a second is REFUSED, because a running total has only one thread to walk. The FIRST bar rises from the baseline on its own, so type the opening balance as the first value and it draws as the full-height bar you want. There is NO automatic closing total bar — every bar is one you typed — so name the last step for what it is, or put the ending figure in the `title`. A `null` SKIPS that step and carries the total forward, so the bars after it stay where they belong. Past eleven categories the axis starts hiding labels, exactly as a column chart does.
- **heatmap** (2–11): THE MATRIX THE PAYLOAD HAS BEEN ALL ALONG: one ROW per series, one COLUMN per category, and each cell shaded by its value. Reach for it when the subject is the PATTERN across two dimensions at once — which region in which quarter, which feature on which plan, where the hot corner is — and a grouped column chart would need six sets of bars to say it. The series NAMES label the rows, so name them for what a reader is scanning down. THE TONE IS RELATIVE, NEVER ABSOLUTE: the palest cell is the smallest number in the grid and the strongest is the largest, so a heatmap says which cells are high AGAINST EACH OTHER and never how high. THE CELLS DO NOT SHOW THEIR NUMBERS — use a `table` when the figures themselves are the point. DO NOT MIX POSITIVE AND NEGATIVE VALUES: one colour at varying strength has one direction, so a loss and a small gain shade alike and nothing on the page says which is which — use a column chart, where the baseline does. A `null` leaves that cell EMPTY rather than shading it, which is why an absent reading cannot be mistaken for the lowest one. At most six rows, because that is how many series the payload carries. Past eleven categories the axis starts hiding labels, exactly as a column chart does.

## `diagram` — A diagram, written as mermaid text.

Archetype `diagram` · items 1 · draws: nothing but itself

A flowchart, a sequence, an org chart, a state machine, an entity diagram — anything whose meaning is in what connects to what. The payload is `source`: mermaid text, which is the same language GitHub and most chat clients render, and it is the ONE block here that survives markdown whole. You place nothing: the layout engine decides where every box goes, so write the RELATIONSHIPS and let it draw. THE FIRST LINE NAMES THE KIND and a wrong one is the commonest mistake, so check it first if a write is refused. The kinds worth knowing: flowchart TD (or LR) for a process, sequenceDiagram for an exchange over time, stateDiagram-v2 for states and transitions, erDiagram for things and how they relate, mindmap for one idea and its branches, gantt for bars on a calendar, quadrantChart, timeline, kanban, block-beta and venn-beta. A refusal carries the LINE the parser objected to; fix that line rather than rewriting the diagram. Labels are TEXT — no HTML tags, and nothing that loads a picture. For a chart of NUMBERS use `chart`; for a handful of steps with real prose in them use `steps`, which is themed and reads better on a slide than a flowchart of the same three boxes.

## Layouts

- **two-cols** (col-1, col-2): Two things of equal weight side by side — a claim and its evidence, before and after, or a picture beside the words about it. Prefer this over two pages when the pair is the point.
- **three-cols** (col-1, col-2, col-3): Three parallel things that each need a block of their own rather than one entry. If each is only a title and a sentence, a box grid at three holds more and reads better.
- **four-cols** (col-1, col-2, col-3, col-4): Four parallel things, each about a QUARTER of the frame — a logo row, four figures, a quarter-by-quarter split. A column this narrow holds a title and a line; a `box` grid at four holds more and stays readable, so reach for this when each column needs its own BLOCK.
- **five-cols** (col-1, col-2, col-3, col-4, col-5): Five parallel things. Each column is about a FIFTH of the frame, which is a mark, a figure or two or three words — not a sentence. A block inside one reflows to it and will stack.

## Templates, and what each wears

- **Cover** (`cover`) — accent full · text·xl, text·md, text·sm. THE TITLE PAGE. The occasion or organisation as the eyebrow; the title as the FIRST TEXT BLOCK — this page has no title field, its title is that block, set at display size and centred; one line saying what the document is; and a byline naming who and when. It ships with a `full` accent and no picture, so it is plain paper until set_page is given an accentSrc — one call puts a photograph behind the words under a scrim. It is ALSO the closing page: the ask as the title, how to reach you as the byline. For a section break, use Divider.
- **Title and figures** (`title-and-figures`) — stat-row·side-rule ×3. The page after the title, where three facts frame the whole document — a period, a scale, a duration. The figures are a stat-row, so each is a value with a label and a note. If the opener needs a picture down one side, use Title pane; for the title page itself, use Cover.
- **Title pane** (`title-pane`) — accent lead · bullets. An opening page with a picture down one side and three to five lines saying what the document covers. The picture is a PAGE accent, so it divides the page into two panes and content cannot sit on it. If the lines are ordered parts rather than points, use Agenda.
- **Agenda** (`agenda`) — accent lead · steps·list ×5. The contents page: FOUR OR FIVE parts, in ORDER, each a title and a line saying what that part covers, stacked beside a picture pane. Ordered because the SEQUENCE carries meaning — if it does not, use Title pane and its bullets. For a coloured section break with no list, use Divider.
- **Divider** (`divider`) — surface accent · text·xl, text·md, text·sm. A section break on a coloured page: the part number as the eyebrow, the section's title as the FIRST TEXT BLOCK (this page has no title field — its title is that block, set at display size and centred), one line saying what changes from here, and a byline naming the pages it covers. Nothing else belongs on it. To list what the section contains, use Agenda; for the title page itself, use Cover.
- **Checklist and line** (`checklist-and-line`) — checklist, text·lg. The closing page that ends in ACTIONS: three to five things that happen next, as a checklist each a person can tick, and one line underneath saying what is being asked and of whom. For a closer that is only the ask and how to reach you, use Cover; for actions in ORDER with a line each, use Lead and sequence.
- **Claim and set** (`claim-and-set`) — text·xl, box·soft-fill·icons ×3. One sentence worth a whole page, with three things underneath that hold it up. The claim is a text block at `xl`, the only size at or above the page title. If the three each need a paragraph rather than a sentence, use Set at length; if the support is numbers, use Claim beside figures.
- **Claim beside figures** (`claim-beside-figures`) — two-cols[ text·lg | stat-row·solid-accent ×3 ]. A claim on one side and the two or three numbers that back it on the other. Reach for this when the numbers ARE the argument and need no explaining; when they do need it, use Figures and reading. The two columns are a layout, so each side holds its own block.
- **Quote and source** (`quote-and-source`) — accent trail · quote, text·sm. One quotation given a whole page, with a portrait pane down one side and the speaker named underneath. ONE quote only — for several voices, use Set at length with each speaker as an entry. The portrait is a page accent, not a block.
- **Lead and set** (`lead-and-set`) — text·lg, box·outlined·icons ×6. Four to six parallel things, each a title and a sentence, under one line saying what they add up to. If three of them each need a paragraph, use Set at length; if each side needs its own BLOCK rather than an entry, use Two sides.
- **Set at length** (`set-at-length`) — box·list·accent-bar·icons ×3, text·sm. Three things said at LENGTH — a paragraph each, which a grid cell has no room for. The `list` shape holds about half again what a grid does. For more than four things, or for a sentence each, use Lead and set.
- **Two sides** (`two-sides`) — two-cols[ heading, bullets | heading, bullets ], text·lg. Two positions of equal weight, each needing its own heading and its own list — before and after, ours and theirs, one option against another. If each side is only a title and a sentence, a box grid at two holds more and reads better, so use Lead and set instead.
- **Table and lead** (`table-and-lead`) — text·lg, table·header-band. A comparison across three or four criteria, under one line saying what to look for. A table is for values you would otherwise repeat in prose. For three things with a sentence each, use Lead and set; for two things at length, use Two sides.
- **Reading in columns** (`reading-in-columns`) — two-cols[ heading, text, text | heading, numbered ], text·lg. A page of PROSE in two columns, the page a report or a hand-out needs: a heading and two short paragraphs on one side, a heading and a numbered list on the other. For two positions argued against each other, use Two sides; for one sentence worth the page, use Claim and set.
- **Lead and sequence** (`lead-and-sequence`) — text·lg, steps·top-rule ×4. Three to five stages in ORDER, each a title and a line, under one sentence framing them. The shape is the block's and it CLAIMS something — a staircase progresses, a funnel narrows, a pyramid rests on what is under it — so change it if another is truer. For dated events, use Timeline and notes.
- **Timeline and notes** (`timeline-and-notes`) — timeline·marked ×5, text·sm. Four to eight DATED events running down the page — a date, a title and a line each — with a closing note beneath. Reach for this when WHEN matters; when only the order does, use Lead and sequence. The events run top to bottom, so it fills a page on its own.
- **Figures and reading** (`figures-and-reading`) — stat-row·banded ×4, text·md. Three or four numbers with a paragraph saying what they mean TOGETHER. If the numbers speak for themselves, use Claim beside figures; if they are one series over time, use Chart and takeaway.
- **Chart and takeaway** (`chart-and-takeaway`) — chart, text·lg. One chart with the sentence a reader should leave with. ALWAYS write the takeaway — a chart without one asks the reader to find the point themselves. For three or four standalone numbers, use Figures and reading; for what connects to what, use Diagram and legend.
- **Diagram and legend** (`diagram-and-legend`) — diagram, box·list·side-rule·icons ×3. A diagram whose parts need naming underneath — a flow, an architecture, a state machine. The payload is mermaid text and the layout engine places every box. For a handful of steps with real prose in them, Lead and sequence reads better on a slide than a flowchart of the same three boxes.
- **Code and reading** (`code-and-reading`) — code, text·md. A block of CODE with a short paragraph under it saying what to look at — a query, a config, a call. Six to ten lines is what a page holds with the reading; nothing colours it, so the words under it are what carry the point. For a word of code inside a sentence, use the inline mark in any text block; for what connects to what, use Diagram and legend.
- **Picture band and captions** (`picture-band-and-captions`) — image-grid·raised-card ×4, text·sm. Three or four pictures shown as a SET, under one line saying what they have in common. Pictures arrive with no address and render an "Add picture" frame, which is the affordance that fixes them. For ONE picture with words beside it, use Picture and words.
- **People and roles** (`people-and-roles`) — text·lg, people·soft-fill ×4. Three to six people, each a portrait, a name, a role and a line, under one sentence framing the group. For ONE person quoted rather than introduced, use Quote and source.
- **Picture and words** (`picture-and-words`) — image-with-text·outlined, text·sm. ONE picture with two or three sentences beside it — a screenshot and what to look at, a photograph and what it shows. For several pictures as a set, use Picture band and captions; for a picture that should fill one side of the whole page, use Title pane.
- **Picture and line** (`picture-and-line`) — text·sm, image·raised-card. ONE picture that IS the page, with a line above saying why it is here and a caption under it saying what to look at. The picture arrives with no address and renders an "Add picture" frame. For a picture with real sentences beside it, use Picture and words; for a picture that should sit behind a title, use Cover.
- **Video and framing** (`video-and-framing`) — text·sm, youtube·raised-card. One video, with a line above saying what it shows and why to watch it. A video keeps its 16:9 shape, so it takes most of a page and nothing else fits beside it. For a still picture with words, use Picture and words.
