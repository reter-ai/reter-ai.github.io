---
layout: doc
title: Getting Started
---

# Installation

Reter Code runs as **two separate processes** connected via ZeroMQ: a stateful RETER server that holds the code ontology, and a stateless MCP client that runs inside Claude.

## Prerequisites

All platforms require:
- [**uv**](https://docs.astral.sh/uv/) — fast Python package manager
- [**git**](https://git-scm.com/) — required to fetch packages from GitHub
- **Claude Code** (CLI or Desktop)

### Python version

| Platform | Supported Python |
|----------|-----------------|
| Windows (x64) | 3.10 – 3.14 |
| Windows (WSL2) | 3.10 – 3.14 |
| macOS (Apple Silicon) | 3.10 – 3.14 |
| macOS (Intel x86_64) | 3.11 – 3.12 |
| Linux (x64) | 3.10 – 3.14 |

> **macOS Intel note:** PyTorch dropped x86_64 macOS support in 2.5+, and older versions don't have Python 3.13 wheels. Use `--python 3.12` when installing with uv.

### Windows

Install with [Chocolatey](https://chocolatey.org/install):

```powershell
choco install uv git vcredist140
```

Or install manually:
- **uv** — `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
- **git** — download from [git-scm.com/download/win](https://git-scm.com/download/win)
- **VC++ Redistributable** — download from [aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)

> The VC++ Redistributable is required by PyTorch (used for code embeddings). Without it you'll get a `c10.dll` error on startup.

### Windows (WSL2)

Works the same as native Linux. Inside your WSL2 terminal:

```bash
# uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# git (Ubuntu/Debian — default WSL distro)
sudo apt update && sudo apt install git
```

### macOS

```bash
brew install uv git
```

Or without Homebrew:

```bash
# uv
curl -LsSf https://astral.sh/uv/install.sh | sh
# git — included with Xcode Command Line Tools
xcode-select --install
```

### Linux

```bash
# uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# git (Debian/Ubuntu)
sudo apt install git

# git (Fedora/RHEL)
sudo dnf install git
```

## Quick Start

### Option A: Persistent Install (Recommended)

Install once — commands stay available:

```bash
uv tool install --from git+https://github.com/reter-ai/reter_code \
  --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html \
  reter_code
```

**macOS Intel (x86_64)** — add `--python 3.12` to avoid PyTorch resolution failures:

```bash
uv tool install --python 3.12 \
  --from git+https://github.com/reter-ai/reter_code \
  --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html \
  reter_code
```

> **Troubleshooting:**
> - **swig/cmake errors** — `uv` is building `faiss-cpu` or `pyarrow` from source. Add `--no-build-package faiss-cpu --no-build-package pyarrow` to force pre-built wheels.
> - **`c10.dll` not found (Windows)** — Install the VC++ Redistributable (see [Prerequisites](#windows)) and restart your terminal.
> - **torch resolution error (macOS Intel)** — PyTorch has no wheels for x86_64 macOS + Python 3.13. Use `--python 3.12`.

Then start the server and add MCP:

```bash
cd /path/to/your/project
reter
```

```bash
claude mcp add reter -e RETER_PROJECT_ROOT=/path/to/your/project -- reter_code --stdio
```

### Option B: No Install (uvx)

Run directly without installing — uvx creates a temporary environment each time:

```bash
cd /path/to/your/project
uvx --from git+https://github.com/reter-ai/reter_code \
  --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html \
  reter
```

```bash
claude mcp add reter -- uvx \
  --from git+https://github.com/reter-ai/reter_code \
  --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html \
  reter_code --stdio
```

### What Happens

The server will:
1. Initialize the RETE network and load your codebase into the ontology
2. Build RAG embeddings (FAISS index)
3. Bind ZeroMQ on `tcp://127.0.0.1:5555`
4. Write a discovery file at `.reter_code/server.json`
5. Display a console UI showing status, config, and queries

**Keep the server terminal open** — the MCP client connects to it via ZeroMQ.

The `-e RETER_PROJECT_ROOT=...` tells the MCP client where to find the server's discovery file.

**Server options:**

| Flag | Description |
|------|-------------|
| `--project, -p` | Project root directory (default: current directory) |
| `--port` | ZeroMQ query port (default: 5555) |
| `--no-console` | Disable rich console UI |
| `--verbose, -v` | Enable debug logging |

## Configure with Claude Desktop

**Config file location:**
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **Linux**: `~/.config/Claude/claude_desktop_config.json`

After `uv tool install`:

```json
{
  "mcpServers": {
    "reter": {
      "command": "reter_code",
      "args": ["--stdio"],
      "env": {
        "RETER_PROJECT_ROOT": "/path/to/your/project"
      }
    }
  }
}
```

Or without installing (uvx):

```json
{
  "mcpServers": {
    "reter": {
      "command": "uvx",
      "args": [
        "--from", "git+https://github.com/reter-ai/reter_code",
        "--find-links", "https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html",
        "reter_code", "--stdio"
      ],
      "env": {
        "RETER_PROJECT_ROOT": "/path/to/your/project"
      }
    }
  }
}
```

**Important:** The RETER server must be running before starting Claude.

## How It Works

```
┌──────────────────────────────────┐     ZeroMQ      ┌──────────────────────────────────┐
│  RETER Server (reter)            │   REQ/REP       │  MCP Client (reter_code)         │
│                                  │   tcp://         │                                  │
│  • Holds RETE network + RAG      │◄────────────────►│  • Stateless FastMCP proxy        │
│  • Builds code ontology          │   127.0.0.1:5555 │  • Registers MCP tools            │
│  • Processes all queries         │   msgpack        │  • Runs inside Claude             │
│  • Runs in separate console      │                  │  • Forwards requests to server    │
└──────────────────────────────────┘                  └──────────────────────────────────┘
```

The server is **stateful** — it initializes the C++ RETE engine, loads the codebase into the ontology, builds RAG embeddings, and processes all queries. The MCP client is **stateless** — it registers tools with Claude and forwards every request to the server over ZeroMQ.

This means the expensive ontology and RAG index stay alive across Claude sessions, and multiple MCP clients can connect to the same server.

## Configuration

### reter_code.json

Place a `reter_code.json` in your project root to configure the server. All settings are optional — defaults are used for anything not specified. Environment variables always take precedence over config file values.

The loaded config is displayed in the server console UI.

```json
{
    "project_include": "**/*.*",
    "project_exclude": "**/__pycache__/*,**/node_modules/*",
    "tools_available": "full",
    "rag_embedding_model": "flax-sentence-embeddings/st-codesearch-distilroberta-base",
    "rag_markdown_include": "**/*.md",
    "rag_markdown_exclude": "node_modules/**"
}
```

#### Project Settings

| Key | Env Variable | Description | Default |
|-----|-------------|-------------|---------|
| `project_include` | `RETER_PROJECT_INCLUDE` | Glob patterns for files to analyze | `**/*.*` |
| `project_exclude` | `RETER_PROJECT_EXCLUDE` | Glob patterns for files to skip | `**/__pycache__/*` |
| `tools_available` | `TOOLS_AVAILABLE` | Tool set: `"default"` or `"full"` | `"default"` |

#### RAG Settings

| Key | Env Variable | Description | Default |
|-----|-------------|-------------|---------|
| `rag_enabled` | `RETER_RAG_ENABLED` | Enable/disable RAG indexing | `true` |
| `rag_embedding_model` | `RETER_RAG_MODEL` | Sentence-transformers model for embeddings | `flax-sentence-embeddings/st-codesearch-distilroberta-base` |
| `rag_embedding_cache_size` | `RETER_RAG_CACHE_SIZE` | Embedding cache size | `1000` |
| `rag_max_body_lines` | `RETER_RAG_MAX_BODY_LINES` | Max lines per method body for embedding | `50` |
| `rag_batch_size` | `RETER_RAG_BATCH_SIZE` | Batch size for embedding computation | `32` |

#### Markdown Indexing

| Key | Env Variable | Description | Default |
|-----|-------------|-------------|---------|
| `rag_index_markdown` | `RETER_RAG_INDEX_MARKDOWN` | Index markdown files into RAG | `true` |
| `rag_markdown_include` | `RETER_RAG_MARKDOWN_INCLUDE` | Glob for markdown files to index | `**/*.md` |
| `rag_markdown_exclude` | `RETER_RAG_MARKDOWN_EXCLUDE` | Glob for markdown files to skip | `node_modules/**` |
| `rag_markdown_max_chunk_words` | `RETER_RAG_MARKDOWN_MAX_CHUNK_WORDS` | Max words per markdown chunk | `500` |
| `rag_markdown_min_chunk_words` | `RETER_RAG_MARKDOWN_MIN_CHUNK_WORDS` | Min words per markdown chunk | `50` |

#### Code Chunking

| Key | Env Variable | Description | Default |
|-----|-------------|-------------|---------|
| `rag_code_chunk_enabled` | `RETER_RAG_CODE_CHUNK_ENABLED` | Enable code chunking for large methods | `true` |
| `rag_code_chunk_size` | `RETER_RAG_CODE_CHUNK_SIZE` | Chunk size in lines | `30` |
| `rag_code_chunk_overlap` | `RETER_RAG_CODE_CHUNK_OVERLAP` | Overlap between chunks in lines | `10` |
| `rag_code_chunk_min_size` | `RETER_RAG_CODE_CHUNK_MIN_SIZE` | Min chunk size in lines | `15` |

### Environment Variables

#### Server

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Path to project for auto-loading code | Auto-detected from CWD |
| `RETER_HOST` | Server bind address | `127.0.0.1` |
| `RETER_QUERY_PORT` | ZeroMQ query port | `5555` |

#### MCP Client

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Project path for server discovery | Auto-detected from CWD |
| `RETER_SERVER_HOST` | Server host (fallback if no discovery) | `127.0.0.1` |
| `RETER_SERVER_QUERY_PORT` | Server port (fallback if no discovery) | `5555` |

## Next Steps

- [Features](/docs/features) - Learn about all available tools and pipelines
- [Examples](/docs/examples) - See CADSL pipelines and refactoring workflows in action
