---
layout: doc
title: Getting Started
---

# Installation

Reter Code is an MCP server that integrates with Claude Code to provide code reasoning capabilities.

## Prerequisites

- Python 3.10 or higher
- Claude Code (CLI or Desktop)
- uv/uvx package manager

## Quick Install

### Step 1: Pre-cache dependencies

Run from your project directory to download dependencies (~400MB, cached for future runs):

```bash
uvx --from git+https://github.com/reter-ai/reter_code --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html reter_code
```

This will:
1. Download dependencies (cached for future runs)
2. Sync your project files to the RETER index
3. Exit automatically

### Step 2: Add to Claude Code

```bash
claude mcp add reter_code -s user -e ANTHROPIC_API_KEY=your-api-key -- uvx --from git+https://github.com/reter-ai/reter_code --find-links https://raw.githubusercontent.com/reter-ai/reter/main/reter_core/index.html reter_code
```

Now Claude starts fast because everything is cached.

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
      "env": {
        "ANTHROPIC_API_KEY": "your-api-key"
      },
      "timeout": 120000
    }
  }
}
```

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Path to project for auto-loading code | Auto-detected from CWD |
| `ANTHROPIC_API_KEY` | API key for sampling handler | - |

## Next Steps

- [Features](/docs/features) - Learn about all available tools
- [Examples](/docs/examples) - See Reter Code in action
