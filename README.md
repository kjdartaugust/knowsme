<p align="center">
  <img src="https://knowsme.dev/icon-512.png" width="96" alt="knowsme">
</p>

<h1 align="center">knowsme</h1>

<p align="center"><b>One memory for you and your AI agents.</b><br>
One memory of you and your work, shared by ChatGPT, Claude, Gemini, Grok, Codex, Cursor, OpenCode and any AI agent that speaks MCP.</p>

<p align="center"><a href="https://knowsme.dev">knowsme.dev</a> · <a href="https://knowsme.dev/privacy">Privacy &amp; terms</a> · <a href="https://knowsme.dev/#pricing">Pricing</a></p>

---

## Why

Every fresh AI session forgets you. You hit your limit, your laptop dies, the context gets too
expensive, or you switch to another AI, and you start from zero again.

knowsme is a hosted [MCP](https://modelcontextprotocol.io) memory server. Every AI you connect
reads the same memory before it answers, and writes to it as you work: decisions, where a project
stands, how you want to be worked with. Open a new chat in a different AI on a different machine,
ask "can we continue?", and it already knows.

## What makes it different

- **Your rules go everywhere.** One file, `rules.md`, says how you want to be worked with
  ("one step at a time", "real answer first"). Every AI reads it before it answers you. Only you can
  change it: an AI can suggest rules, and they wait for your OK.
- **We can't read your notes.** Lock your notes with a passphrase and every note is locked before it
  is stored: the words, the titles, even which project it belongs to. Lock them before you connect an
  AI, and keep your recovery code safe.
- **Every AI and agent, not one.** Chat apps, coding agents on your computer (Claude Code, Codex,
  Cursor, OpenCode, Gemini CLI), agents that run in the cloud (Claude Code on the web, Cursor cloud
  agents, Devin, GitHub Copilot's coding agent) and your own scripts or bots with a key of their
  own. One agent picks up exactly where another left off.
- **You decide what each AI can reach.** Read-only keys, keys limited to one project, keys that
  expire, and one-press cut-off from your dashboard.
- **Hosted, nothing to run yourself.** No key goes into a command or a settings file.

## Connect your AI

No sign-up first: the first sign-in creates your account. Your browser opens once.

**Claude, ChatGPT, Grok, Le Chat and other AI apps** — Settings → Connectors → Add custom
connector, and paste:

```
https://mcp.knowsme.dev/mcp
```

**Claude Code**

```
claude mcp add knowsme --scope user --transport http https://mcp.knowsme.dev/mcp
```

Then start Claude Code, type `/mcp`, choose knowsme and sign in.

**Codex CLI** (two lines, run one at a time)

```
codex mcp add knowsme --url https://mcp.knowsme.dev/mcp
node -e "fetch('https://knowsme.dev/get/codex.js').then(r=>r.text()).then(eval)"
```

The second line makes Codex check your memory before its first reply.

**OpenCode** (two lines, run one at a time)

```
opencode mcp add knowsme --url https://mcp.knowsme.dev/sse
opencode mcp auth knowsme
```

**Gemini CLI** — add to `~/.gemini/settings.json`, then restart:

```json
{ "mcpServers": { "knowsme": { "url": "https://mcp.knowsme.dev/sse" } } }
```

**Cursor, VS Code and others** — one-click buttons and every other client are on
[knowsme.dev](https://knowsme.dev).

**A client that can only launch a local command:**

```json
{ "mcpServers": { "knowsme": { "command": "npx", "args": ["-y", "mcp-remote@0.15.2", "https://mcp.knowsme.dev/mcp"] } } }
```

Then ask your AI: *"what do you know about me?"*

## Tools

| Tool | What it does |
|---|---|
| `list_memories` | Lists your notes, newest first |
| `recall` | Reads one note |
| `search_memories` | Searches your notes |
| `remember` | Saves a note |
| `forget` | Removes a note (kept in your undo history) |
| `history` | Earlier versions of a note |
| `propose_rules` | Suggests rules; they wait for your approval |
| `propose_tidy` | Suggests moving or removing notes; waits for your approval |

Scripts and bots that can't speak MCP can use the plain HTTP API: [openapi.json](https://knowsme.dev/openapi.json).

## Pricing

Free to start: every AI, every device, up to 200 notes. Pro and Teams are on the way.
See [knowsme.dev/#pricing](https://knowsme.dev/#pricing).

## Remove knowsme

One line takes knowsme out of every AI app on a computer. It backs up every file it changes.

Windows (PowerShell):

```
irm https://knowsme.dev/get/uninstall.ps1 | iex
```

Mac, Linux or WSL:

```
curl -fsSL https://knowsme.dev/get/uninstall.sh | sh
```

## Contact

Questions, teams, or press: Venturesgodspeed@gmail.com

Made by Godspeed Digital Ventures.
