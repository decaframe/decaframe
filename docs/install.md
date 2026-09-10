# Installing decaframe

Decaframe is two things: the **tools** your agent builds a deck with, and a **skill** that
teaches it to use them well. You need Node 22 or later.

**Decaframe runs on your computer.** Your agent starts it as a program, so it works in apps
that can start one — desktop apps and coding agents — and not on a website or a phone.

- **The Claude website and the Claude phone apps** — Use the Claude desktop app.
- **ChatGPT on the web and on your phone** — Use the ChatGPT desktop app.
- **Claude in Chrome, and Gemini in Chrome** — A browser extension cannot start a program.
- **Anything that reaches a server over the internet** — Decaframe runs beside you, not in a data centre. That is what keeps it free and your work yours.

## The short version

Almost every agent takes the same block, in whichever file it keeps its MCP servers in:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

And the skill, which one installer writes into about eighty agents:

```bash
npx skills add decaframe/decaframe
```

Full instructions for each agent: https://decaframe.com/install

## Apps you chat with

### Claude Desktop (and Cowork)

Open Customize › Plugins in the sidebar, choose Add marketplace and paste:

The marketplace:

```bash
decaframe/decaframe
```

Then install decaframe from it. The plugin carries both halves — the tools and the skill — so there is nothing else to add.

The desktop app is the whole of it: plugins that run a program on your computer do not work on the Claude website or on your phone.

### ChatGPT (desktop app only)

Open Settings › MCP servers › Add server, choose STDIO, name it decaframe and give it this command:

The command:

```bash
npx -y decaframe mcp
```

Restart the app. For the skill, see the Codex panel — the two share their settings.

The desktop app only. ChatGPT on the web and on your phone reach servers over the internet and cannot start one here.

### OpenClaw

The tools:

```bash
openclaw mcp add decaframe --command npx --arg -y --arg decaframe --arg mcp
```

The skill:

```bash
npx skills add decaframe/decaframe
```

Check it with openclaw mcp doctor decaframe --probe. OpenClaw also keeps its servers under mcp.servers in its config, if you would rather write it there.

### Hermes (Nous Research)

Add this to your config — `~/.hermes/config.yaml`:

```json
mcp_servers:
  decaframe:
    command: npx
    args: ["-y", "decaframe", "mcp"]
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Raycast (Raycast Pro)

Settings › MCP › Install MCP Server. Name it decaframe, set the command to npx and the arguments to -y decaframe mcp.

The skill:

```bash
npx skills add decaframe/decaframe
```

### Warp

Add decaframe to that file — `~/.warp/.mcp.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Goose (by Block)

[Add to Goose](goose://extension?type=stdio&id=decaframe&name=Decaframe&description=Decks%2C%20reports%20and%20one-pagers&cmd=npx&arg=-y&arg=decaframe&arg=mcp)

Or add it by hand — Goose keeps its servers in YAML, not JSON:

The tools — `~/.config/goose/config.yaml`:

```json
extensions:
  decaframe:
    enabled: true
    type: stdio
    cmd: npx
    args: ["-y", "decaframe", "mcp"]
```

The skill:

```bash
npx skills add decaframe/decaframe
```

## Apps that run models on your machine

### LM Studio

[Add to LM Studio](https://lmstudio.ai/install-mcp?name=decaframe&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsImRlY2FmcmFtZSIsIm1jcCJdfQ%3D%3D)

Or open the Program tab, choose Install › Edit mcp.json and add:

The tools — `mcp.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

LM Studio does not read skills, so the deck is built from the tools alone. A larger model makes a better job of it.

### Jan

Settings › MCP Servers › +. Name it decaframe, command npx, arguments -y decaframe mcp.

The skill:

```bash
npx skills add decaframe/decaframe
```

### AnythingLLM

In your storage folder, under plugins — `anythingllm_mcp_servers.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

### Cherry Studio

Settings › MCP › MCP Servers › Add. Command npx, arguments -y decaframe mcp.

Then turn the server on and bind it to your agent under Work › your agent › Edit › MCP — Cherry Studio keeps the two steps apart, and a server nobody has bound is a server your agent cannot see.

## Coding agents

### Claude Code

Add the marketplace:

```bash
claude plugin marketplace add decaframe/decaframe
```

Install the tools and the skill together:

```bash
claude plugin install decaframe@decaframe
```

Or the tools on their own, with no skill:

The tools alone:

```bash
claude mcp add --scope user decaframe -- npx -y decaframe mcp
```

### Cursor

[Add to Cursor](https://cursor.com/install-mcp?name=decaframe&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsImRlY2FmcmFtZSIsIm1jcCJdfQ%3D%3D)

Or add it by hand:

Add decaframe to that file — `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### VS Code (with Copilot)

[Add to VS Code](https://insiders.vscode.dev/redirect/mcp/install?name=decaframe&config=%7B%22name%22%3A%22decaframe%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22decaframe%22%2C%22mcp%22%5D%7D)

Or from a terminal:

The tools:

```bash
code --add-mcp '{"name":"decaframe","command":"npx","args":["-y","decaframe","mcp"]}'
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Codex (CLI and the IDE extension)

The tools:

```bash
codex mcp add decaframe -- npx -y decaframe mcp
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Gemini CLI

The tools:

```bash
gemini mcp add -s user decaframe npx -- -y decaframe mcp
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Devin Desktop (formerly Windsurf)

The tools:

```bash
devin mcp add decaframe -- npx -y decaframe mcp
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Cline

Add decaframe to that file — `~/.cline/data/settings/cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Zed

Zed calls them context servers — `~/.config/zed/settings.json`:

```json
{
  "context_servers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Kiro

[Add to Kiro](https://kiro.dev/launch/mcp/add/?name=decaframe&config=%7B%22decaframe%22%3A%7B%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22decaframe%22%2C%22mcp%22%5D%7D%7D)

Or by hand:

Add decaframe to that file — `~/.kiro/settings/mcp.json`:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Amp

The tools:

```bash
amp mcp add decaframe -- npx -y decaframe mcp
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### OpenCode

OpenCode takes the command as a list — `opencode.json`:

```json
{
  "mcp": {
    "decaframe": {
      "type": "local",
      "command": [
        "npx",
        "-y",
        "decaframe",
        "mcp"
      ],
      "enabled": true
    }
  }
}
```

The skill:

```bash
npx skills add decaframe/decaframe
```

### Any other agent

Almost every agent takes the same block. Find where yours keeps its MCP servers and add:

The tools:

```json
{
  "mcpServers": {
    "decaframe": {
      "command": "npx",
      "args": [
        "-y",
        "decaframe",
        "mcp"
      ]
    }
  }
}
```

The skill, for about eighty agents:

```bash
npx skills add decaframe/decaframe
```

If your agent has a different shape for it, tell us and we will add a panel for it.

