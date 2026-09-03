# decaframe documentation

## Install

```bash
npm install -g decaframe
```

Node 22 or later. The headless browser the export renders with is downloaded once, in the background, the
first time `deca` runs, about 100 MB from Playwright's own servers. On Linux the browser needs the usual system libraries; the
export says so if they are missing.

## Connect an agent

Add the server to your client. For Claude Code, Cursor, Windsurf and most others the entry is:

```json
{ "mcpServers": { "decaframe": { "command": "npx", "args": ["-y", "decaframe", "mcp"] } } }
```

Then ask for a deck. The document is written to `document.json` in the folder the agent works in;
set `DECAFRAME_DOC` to put it elsewhere. The skill that teaches an agent to design with the tools:

```bash
npx skills add decaframe/decaframe
```

## Open a document yourself

```bash
deca open document.json
```

Serves the editor on a free port and opens it in a window. An agent and the editor may hold the
same file at once: what either saves, the other sees. `deca` alone prints help.

## Export

Ask the agent for `export_html`, or use the editor's menu. The file is one HTML page that opens by
double-click. It expects the internet for its fonts, pictures and video, and degrades gracefully
without it: a system font, a still frame, a placeholder.

## The skill

`skills/decaframe/SKILL.md` teaches composition: which block and style to choose, how to build a
page from rows and columns, how to vary a deck so it reads as designed, and the markdown grammar
that lays a whole deck down in one call. `references/` carries the catalogue and the grammar.
