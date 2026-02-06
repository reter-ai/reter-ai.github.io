---
layout: doc
title: Getting Started
---

# Installation

Reter Code runs as **two separate processes** connected via ZeroMQ: a stateful RETER server that holds the code ontology, and a stateless MCP client that runs inside Claude.

## Prerequisites

- Python 3.10 or higher
- Claude Code (CLI or Desktop)
- uv/uvx package manager

## Quick Install

### Step 1: Install

```bash
pip install reter_code
```

Or with uvx (downloads ~400MB of dependencies, cached for future runs):

```bash
uvx --from git+https://github.com/reter-ai/reter_code --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html reter_code
```

### Step 2: Start the RETER Server

Open a **separate terminal** and start the server on your project:

```bash
reter_server --project /path/to/your/project
```

The server will:
1. Initialize the RETE network and load your codebase into the ontology
2. Build RAG embeddings (FAISS index)
3. Bind ZeroMQ on `tcp://127.0.0.1:5555`
4. Write a discovery file at `.reter_code/server.json`
5. Display a console UI showing status and queries

**Keep this terminal open** — the server must be running for the MCP client to work.

**Server options:**

| Flag | Description |
|------|-------------|
| `--project, -p` | Project root directory |
| `--port` | ZeroMQ query port (default: 5555) |
| `--no-console` | Disable rich console UI |
| `--verbose, -v` | Enable debug logging |

### Step 3: Add MCP Client to Claude Code

```bash
claude mcp add reter_code -s user -- uvx --from git+https://github.com/reter-ai/reter_code --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html reter_code
```

The MCP client automatically discovers the server via `.reter_code/server.json`.

## Configure with Claude Desktop

**Config file location:**
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **Linux**: `~/.config/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "reter_code": {
      "command": "uvx",
      "args": [
        "--from", "git+https://github.com/reter-ai/reter_code",
        "--find-links", "https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html",
        "reter_code"
      ],
      "timeout": 120000
    }
  }
}
```

**Important:** The RETER server must be running before starting Claude. The MCP client connects to it via ZeroMQ.

## How It Works

```
┌──────────────────────────────────┐     ZeroMQ      ┌──────────────────────────────────┐
│  RETER Server (reter_server)     │   REQ/REP       │  MCP Client (reter_code)         │
│                                  │   tcp://         │                                  │
│  • Holds RETE network + RAG      │◄────────────────►│  • Stateless FastMCP proxy        │
│  • Builds code ontology          │   127.0.0.1:5555 │  • Registers MCP tools            │
│  • Processes all queries         │   msgpack        │  • Runs inside Claude             │
│  • Runs in separate console      │                  │  • Forwards requests to server    │
└──────────────────────────────────┘                  └──────────────────────────────────┘
```

The server is **stateful** — it initializes the C++ RETE engine, loads the codebase into the ontology, builds RAG embeddings, and processes all queries. The MCP client is **stateless** — it registers tools with Claude and forwards every request to the server over ZeroMQ.

This means the expensive ontology and RAG index stay alive across Claude sessions, and multiple MCP clients can connect to the same server.

## Environment Variables

### Server

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Path to project for auto-loading code | Auto-detected from CWD |
| `RETER_HOST` | Server bind address | `127.0.0.1` |
| `RETER_QUERY_PORT` | ZeroMQ query port | `5555` |

### MCP Client

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Project path for server discovery | Auto-detected from CWD |
| `RETER_SERVER_HOST` | Server host (fallback if no discovery) | `127.0.0.1` |
| `RETER_SERVER_QUERY_PORT` | Server port (fallback if no discovery) | `5555` |

## Next Steps

- [Features](/docs/features) - Learn about all available tools and pipelines
- [Examples](/docs/examples) - See CADSL pipelines and refactoring workflows in action
