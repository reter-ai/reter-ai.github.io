---
layout: page
title: About
---

# About Codeine

Codeine is an AI-powered code reasoning MCP server that gives Claude Code deep understanding of your codebase.

## What is Codeine?

Codeine combines:

- **RETER Engine** - A RETE-based reasoning engine for semantic knowledge graphs
- **MCP Protocol** - Model Context Protocol for Claude Code integration
- **Multi-Language Parsing** - ANTLR4-based parsers for 7 languages
- **RAG Search** - FAISS vector embeddings for semantic code search

## Architecture

Codeine uses a three-layer architecture:

```
┌─────────────────────────────────────────┐
│           Claude Code (Client)          │
└────────────────────┬────────────────────┘
                     │ MCP Protocol
┌────────────────────▼────────────────────┐
│         Codeine MCP Server              │
│   (Python: tools, resources, prompts)   │
└────────────────────┬────────────────────┘
                     │
┌────────────────────▼────────────────────┐
│         RETER Python Wrapper            │
│   (Reasoning API, REQL queries)         │
└────────────────────┬────────────────────┘
                     │
┌────────────────────▼────────────────────┐
│          RETER C++ Core                 │
│   (RETE algorithm, OWL 2 RL, SWRL)      │
└─────────────────────────────────────────┘
```

## Key Technologies

| Component | Technology |
|-----------|------------|
| Reasoning Engine | RETER (RETE algorithm) |
| Knowledge Representation | OWL 2 RL, SWRL rules |
| Query Language | REQL (SPARQL-like) |
| Language Parsing | ANTLR4 |
| Vector Search | FAISS |
| MCP Server | Python asyncio |

## Supported Languages

- **Python** - Full semantic analysis with 70+ refactoring detectors
- **JavaScript/TypeScript** - Classes, functions, modules, React components
- **C#** - Classes, interfaces, namespaces, generics
- **C++** - Classes, templates, namespaces, inheritance
- **Go** - Structs, interfaces, packages
- **Rust** - Structs, traits, modules, implementations
- **HTML** - DOM structure, scripts, forms

## Statistics

When analyzing a typical codebase, Codeine extracts:

- **Modules** - Package and file structure
- **Classes** - With inheritance relationships
- **Functions/Methods** - With parameters and return types
- **Call Graph** - Who calls whom
- **Dependencies** - Import relationships

## Open Source

Codeine is open source and available on GitHub:

- [GitHub Repository](https://github.com/codeine-ai/codeine)
- [Issue Tracker](https://github.com/codeine-ai/codeine/issues)
- [Documentation](https://codeine.ai/docs)

## License

Codeine is released under the MIT License.
