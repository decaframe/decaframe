# decaframe documentation

## Install

```bash
npm install -g decaframe
```

Node 22 or later. The headless browser the export renders with is downloaded once, in the background, the
first time `deca` runs, about 100 MB from Playwright's own servers. On Linux the browser needs the usual system libraries; the
export says so if they are missing.

## Connect an agent

Almost every client takes the same block, in whichever file it keeps its MCP servers in:

```json
{ "mcpServers": { "decaframe": { "command": "npx", "args": ["-y", "decaframe", "mcp"] } } }
```

Some want a command instead, and Cursor, VS Code, LM Studio, Kiro and Goose each publish a one-click
install link. All of them, with the exact file path for each: **[install.md](install.md)**, or
[decaframe.com/install](https://decaframe.com/install).

Then add the skill, which teaches an agent to design rather than merely fill pages. One command
writes it into about eighty agents:

```bash
npx skills add decaframe/decaframe
```

Then ask for a deck. The document is a `.json` file named from its title the first time you give it
one. It is written in the folder your agent works in — or, when the agent starts somewhere nobody
works (a desktop app usually does), in `Documents/Decaframe`. `DECAFRAME_DOC` names it yourself.

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

`plugin/skills/decaframe/SKILL.md` teaches composition: which block and style to choose, how to build a
page from rows and columns, how to vary a deck so it reads as designed, and the markdown grammar
that lays a whole deck down in one call. `references/` carries the catalogue and the grammar.
