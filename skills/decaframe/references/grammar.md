# The markdown grammar

Generated from the code by `pnpm skill`. One `import_markdown` call lays down a whole deck. Every marker is a line of
its own, `::name: key=value …::`, and ends at the next marker, the next page, or `::end::`. Nothing nests. The keys are the
tools' own argument names, and a wrong one is refused by name with nothing written.

## Pages

```markdown
# The page title
::page: eyebrow="Section" subtitle="One line under the title" accent=lead src=https://… alt="…" surface=muted mode=dark::
```

A `#` heading starts a page and is its title. A `::page…::` line starts one too, so a cover needs no heading. Keys:
eyebrow, subtitle, accent (top, lead, trail, full) with src and alt, surface (subtle, muted, accent), mode (light, dark).
Presenter notes are a trailing `<!-- notes … -->` comment block.

## Blocks

A block marker — `::box::`, `::steps::`, `::timeline::`, `::stat-row::`, `::image::`, `::image-grid::`, `::image-with-text::`, `::table::`, `::people::`, `::youtube::`, `::chart::`, `::diagram::` — opens a block; what follows builds it.

```markdown
::steps: arrangement=staircase variant=top-rule::
### Dogfood {icon=users meta="April"}
Every employee on the new flow.
### Ten percent {icon=filter meta="May" emphasis}
One flag from rollback.
::end::

::stat-row: variant=solid-accent::
### 84% {label="Signup completion"}
up from 61%
::end::

::people: variant=soft-fill::
![Ada](https://…/ada.jpg) {caption="CEO"}
### Ada Lovelace
Wrote the first program.
::end::

::youtube::
https://youtu.be/… {caption="Two minutes"}
::end::

::chart: arrangement=line stack=stacked title="Revenue" axisX="Quarter" axisY="$M"::
| | North | South |
|---|---|---|
| Q1 | 12 | 9 |
| Q2 | 15 | |
::end::

::text: arrangement=xl::
A line at display size

::table: variant=banded::
| a | b |
|---|---|
| 1 | 2 |
```

- Items blocks (`box`, `steps`, `timeline`): each heading is an item, its braces carry `icon`, `meta`, `emphasis`, the
  paragraphs and lists under it are the body.
- `stat-row`: the heading is the VALUE, `{label="…"}` its label, the line under it the note.
- Media (`image`, `image-grid`, `image-with-text`, `people`): a picture line starts an entry, braces carry `caption` and
  `alt`, a heading after it is the title (a person's name), paragraphs are the words. `youtube` takes a bare address line.
- `chart`: over a table whose header names the series and whose rows are a category and its values; an empty cell is a
  gap; a header cell may carry `{as=line}` for a combo series. Marker keys: arrangement, stack, title, axisX, axisY.
- `text` and `table` markers set attributes on the block beneath; `diagram` on a ```mermaid fence.
- Block keys: variant, arrangement (a shape or a figure), iconPosition (top, lead, none), mark.

## Columns

```markdown
::layout: two-cols::
::col-1::
![A photo](https://…)
::col-2::
- a point
- another
::end::
```

Layouts: `two-cols`, `three-cols`, `four-cols`, `five-cols`. Regions are `::col-1::` … in reading order; a block marker
inside a column works as anywhere. `::end::` closes the layout; a page or another marker closes it too.
