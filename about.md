---
layout: page
title: About
---

# About Reter Code

Architectural visibility for AI coding agents.

The name comes from the **RETE algorithm** — the forward-chaining pattern matching engine at its core. RETER *RETEs your code*: it feeds source files through a RETE network of 70+ OWL 2 RL inference rules and what comes out the other end is a formal code ontology.

## The Problem

AI coding agents are **architecturally blind**. They see files and functions, but not the architecture — the class hierarchies, dependency graphs, layer boundaries, and patterns that hold a codebase together. Without that visibility, they duplicate code, reinvent patterns, cross architectural layers, and create god classes. Every task gets solved locally. The code works, but the architecture erodes with every change.

**The root cause is simple: agents operate on text, not on structure.** They have no model of the codebase as a whole.

## The Solution

Reter Code gives AI agents architectural visibility by building a **code ontology** — a formal semantic model of the entire codebase — and exposing it through the [Model Context Protocol](https://modelcontextprotocol.io).

The ontology is built with OWL 2 RL Description Logic and enhanced with **RAG embeddings** (FAISS + sentence-transformers) and **ML-based clustering** (DBSCAN), so agents can ask questions like *"does a utility for this already exist?"*, *"what layer is this class in?"*, *"is there similar code elsewhere?"* — before writing a single line.

## How It Works

1. **Builds a code ontology** — parses source code into a semantic knowledge graph (classes, methods, calls, inheritance, dependencies) using language-specific C++ parsers and OWL 2 RL reasoning with 70+ inference rules
2. **Enhances with RAG and ML** — indexes code into FAISS vector embeddings for semantic similarity search, pairwise duplicate detection, and DBSCAN density-based clustering to find redundancy that structural analysis alone misses
3. **Pipelines batch analysis** — CADSL pipelines chain ontology queries with ML-powered enrichment steps to detect code smells, find duplicates, identify extraction opportunities, and generate refactoring task lists across the entire codebase
4. **Synthesizes new queries on demand** — a Claude subagent translates natural language questions into CADSL/REQL queries at runtime, with access to the schema, 130 examples, and verification tools
5. **Feeds results** to AI agents for automated or assisted refactoring

## Architecture

Reter Code runs as **two separate processes** connected via ZeroMQ:

- **RETER Server** (`reter_server`) — stateful process that holds the RETE network, builds the code ontology, indexes RAG embeddings, and processes all queries. Runs in a separate terminal.
- **MCP Client** (`reter_code`) — stateless FastMCP proxy that runs inside Claude, registers MCP tools, and forwards every request to the server over ZeroMQ.

This separation means the expensive ontology and RAG index stay alive across Claude sessions, and multiple MCP clients can connect to the same server.

| Component | Command | Description |
|-----------|---------|-------------|
| RETER Server | `reter_server` | Stateful server: RETE network, RAG, CADSL pipelines, query processing |
| MCP Client | `reter_code` | Stateless FastMCP proxy: tool registration, Claude integration |
| Python API | `reter` | `Reter` class, query result sets, CLI |
| C++ Engine | `reter_core` | RETE network, OWL RL rules, language parsers (closed source) |

## MCP Tools

### Refactoring Pipeline

| Tool | Description |
|------|-------------|
| `execute_cadsl` | Run CADSL pipelines — the primary tool for batch codebase analysis |
| `natural_language_query` | Ask questions in plain English — translates to CADSL/REQL automatically |
| `reql` | Execute REQL queries directly against the knowledge graph |
| `semantic_search` | Find semantically similar code using FAISS vector similarity |
| `code_inspection` | Multi-language code analysis (Python, JS, C#, C++) |
| `recommender` | Refactoring and redundancy reduction recommendations |

### Session and Tracking

| Tool | Description |
|------|-------------|
| `session` | Session lifecycle — call `context` first to restore state |
| `thinking` | Record reasoning with design doc sections (context, goals, design, tasks) |
| `items` | Track refactoring tasks, milestones, and progress |
| `diagram` | Visualize class hierarchy, dependencies, call graphs |
| `system` | Initialization status, source management, reindexing |

## Supported Languages

| Language | Extensions | Status |
|----------|-----------|--------|
| Python | `.py` | Full support |
| C# | `.cs` | Full support |
| C++ | `.cpp`, `.hpp`, `.h`, `.cc` | Full support |
| JavaScript | `.js` | Full support |

## Open Source

Reter Code is open source under the MIT License.

- [GitHub Repository](https://github.com/reter-ai/reter_code)
- [Issue Tracker](https://github.com/reter-ai/reter_code/issues)
