---
layout: doc
title: Getting Started
---

# Installation

Codeine is an MCP (Model Context Protocol) server that integrates with Claude Code to provide semantic code analysis and reasoning capabilities.

## Prerequisites

- Python 3.10 or higher
- Claude Code (Claude Desktop with CLI)
- Git

## Quick Install

### Windows

```bash
git clone https://github.com/codeine-ai/codeine
cd codeine
install.bat
```

### Linux/macOS

```bash
git clone https://github.com/codeine-ai/codeine
cd codeine
pip install -e .
```

## Configure Claude Code

Add Codeine to your Claude Code MCP configuration:

**Windows:** `%APPDATA%\Claude\claude_desktop_config.json`
**macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "codeine": {
      "command": "python",
      "args": ["-m", "codeine"],
      "env": {
        "RETER_PROJECT_ROOT": "C:/path/to/your/project"
      }
    }
  }
}
```

## Verify Installation

After restarting Claude Code, you should see Codeine's tools available:

```
Use code_inspection to analyze your codebase architecture
```

Claude will respond with information about your project structure.

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `RETER_PROJECT_ROOT` | Root directory of your project | Current directory |
| `RETER_EXCLUDE_PATTERNS` | Glob patterns to exclude | `test_*,*_test.py` |
| `RETER_MCP_LOG_LEVEL` | Log level (DEBUG, INFO, etc.) | INFO |

## Next Steps

- [Features](/docs/features) - Learn about all available tools
- [Examples](/docs/examples) - See Codeine in action
