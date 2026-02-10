---
layout: doc
title: Features
---

# Features

Reter Code provides MCP tools for building a code ontology, running refactoring pipelines, and giving AI agents architectural visibility.

## Refactoring Pipeline Tools

The primary workflow tools for detecting and reducing code redundancy.

| Tool | Description |
|------|-------------|
| `execute_cadsl` | Run CADSL pipelines — the primary tool for batch codebase analysis |
| `natural_language_query` | Ask questions in plain English — translates to CADSL/REQL automatically |
| `generate_cadsl` | Generate CADSL queries from natural language without executing them |
| `reql` | Execute REQL queries directly against the knowledge graph |
| `semantic_search` | Find semantically similar code using FAISS vector similarity |
| `code_inspection` | Multi-language code analysis (15 languages) |
| `recommender` | Refactoring and redundancy reduction recommendations |

### execute_cadsl

The primary tool for batch codebase processing. Runs CADSL pipelines that chain REQL knowledge graph queries with RAG embeddings, ML clustering, content fetching, and task creation.

```python
# Find redundant code across files
execute_cadsl(
    script="cadsl/tools/good/redundant_code_tasks.cadsl",
    params={"min_similarity": 0.75, "limit": 50, "dry_run": True}
)

# Find extraction opportunities using DBSCAN clustering
execute_cadsl(
    script="cadsl/tools/good/extraction_opportunities_dbscan.cadsl",
    params={"eps": 0.5, "min_samples": 2, "file_filter": ".py"}
)

# Detect god classes
execute_cadsl(
    script="cadsl/tools/smells/god_class.cadsl",
    params={"min_methods": 15}
)

# Generate architecture diagram from semantic annotations
execute_cadsl(
    script="cadsl/tools/good/architecture_diagram.cadsl",
    params={"columns": 4}
)
```

### natural_language_query

Ask questions in plain English. A Claude subagent classifies the question, searches 130 example pipelines, generates a CADSL/REQL query, tests it against the live knowledge graph, and retries on errors — up to 5 attempts.

```python
natural_language_query("Find duplicate code that could be extracted into shared functions")
natural_language_query("Which classes have more than 20 methods?")
natural_language_query("Show me the call graph for the authentication module")
natural_language_query("Find untested public methods in the services layer")
```

### reql

Execute REQL queries directly against the code knowledge graph. SPARQL-like triple patterns over the ontology.

```
SELECT ?class ?name ?method_count
WHERE {
    ?class type class .
    ?class has-name ?name .
    ?class has-method-count ?method_count .
    FILTER(?method_count > 20)
}
```

### semantic_search

Find semantically similar code using FAISS vector embeddings. Search by natural language across the entire codebase.

```python
semantic_search("authentication and JWT tokens")
semantic_search("error handling", entity_types=["method", "function"])
semantic_search("database connection", file_filter="src/db/**")
```

### code_inspection

Multi-language code analysis across 15 languages.

Available actions include:
- `list_modules` - List all modules
- `list_classes` - List all classes
- `describe_class` - Get detailed class info
- `get_class_hierarchy` - Inheritance hierarchy
- `find_usages` - Find where code is used
- `find_callers` / `find_callees` - Call graph traversal
- `analyze_dependencies` - Module dependencies
- `get_complexity` - Complexity metrics
- `get_architecture` - Architecture overview

### recommender

Generate refactoring recommendations, test coverage analysis, and extraction opportunities.

```python
recommender(recommender_type="refactoring")
recommender(recommender_type="test_coverage")
```

## Session and Tracking Tools

| Tool | Description |
|------|-------------|
| `session` | Session lifecycle — call `context` first to restore state |
| `thinking` | Record reasoning with design doc sections (context, goals, design, tasks) |
| `items` | Track refactoring tasks, milestones, and progress |
| `diagram` | Visualize class hierarchy, dependencies, call graphs |
| `system` | Initialization status, source management, reindexing |

### session

Manage reasoning sessions with persistence.

```python
# Restore state at the start of every conversation
session(action="context")

# Start a new session
session(action="start", goal="Refactor auth module")

# End session
session(action="end")
```

### thinking

Record structured reasoning steps with design doc sections.

```python
thinking(
    thought="Analyzing the authentication module for redundant code",
    thought_number=1,
    total_thoughts=3,
    thought_type="analysis",
    section="context"
)
```

## CADSL Pipelines (130 built-in)

CADSL (Code Analysis DSL) chains knowledge graph queries with transformation steps. Pipeline steps include: `reql`, `rag` (duplicates/dbscan/enrich), `filter`, `select`, `map`, `join`, `order_by`, `limit`, `unique`, `fetch_content`, `rag_enrich`, `python`, `file_scan`, `render_mermaid`, `create_task`, `emit`.

| Category | Count | Examples |
|----------|-------|---------|
| **Refactoring** | 26 | extract method/class, move field, inline class, pull up/push down |
| **Code Smells** | 24 | god class, long method, feature envy, dead code, shotgun surgery |
| **Inspection** | 21 | class hierarchy, callers/callees, API docs, complexity |
| **RAG (Semantic)** | 15 | cross-file duplicates, DBSCAN clusters, orphan helpers |
| **Testing** | 11 | untested classes/methods, shallow tests, coverage gaps |
| **Diagrams** | 6 | call graph, class diagram, dependency graph, sequence diagram |
| **Patterns** | 6 | singleton, factory, decorator, interface implementations |
| **Dependencies** | 3 | circular imports, unused imports, external deps |
| **Exceptions** | 5 | silent exceptions, generic raise, error codes |
| **File Search** | 5 | TODOs, debug statements, hardcoded secrets |
| **Inheritance** | 4 | collapse hierarchy, extract superclass, replace with delegate |
| **Good Practices** | 4 | architecture diagram, redundant code detection, extraction opportunities |

## Refactoring Workflow

### Phase 1: Detect

Run pipelines to scan the codebase and create review tasks.

### Phase 2: Classify

For each task, the AI reads the actual code and classifies it:

- **TP-EXTRACT** — Real duplication, extract to shared function
- **TP-PARAMETERIZE** — Similar with small variations, extract with parameters
- **PARTIAL-TP** — Some extractable fragments within larger methods
- **FP-INTERFACE** — Same interface pattern, different implementations
- **FP-LAYERS** — Same params through architectural layers (proper layering)
- **FP-STRUCTURAL** — Similar Python idioms, different logic
- **FP-TRIVIAL** — Too short to extract

True positives automatically generate follow-up implementation tasks.

### Phase 3: Implement

For each TP, choose an extraction strategy:

| Situation | Strategy |
|-----------|----------|
| Same class | Extract private helper method |
| Same file | Extract module-level function |
| Related classes | Extract to base class |
| Unrelated classes | Extract to utility module |
| Same structure, different details | Template Method pattern |

## Semantic Annotations

Classes can be annotated with `:::` CNL statements that become part of the knowledge graph:

```python
class AuthService:
    """
    ::: This is-in-layer Service-Layer.
    ::: This is-in-process Main-Process.
    ::: This is stateful.
    ::: This depends-on `UserRepository`.
    """
```

These annotations enable architectural queries — find all stateful classes, map process boundaries, detect layer violations, generate architecture diagrams.

## Supported Languages

| Language | Extensions | Status |
|----------|-----------|--------|
| Python | `.py` | Full support |
| JavaScript | `.js`, `.mjs`, `.jsx`, `.ts`, `.tsx` | Full support |
| Java | `.java` | Full support |
| C# | `.cs` | Full support |
| C++ | `.cpp`, `.cc`, `.cxx`, `.hpp`, `.h` | Full support |
| Go | `.go` | Full support |
| Rust | `.rs` | Full support |
| Swift | `.swift` | Full support |
| Scala | `.scala`, `.sc` | Full support |
| PHP | `.php` | Full support |
| Haskell | `.hs`, `.lhs` | Full support |
| Erlang | `.erl`, `.hrl` | Full support |
| Objective-C | `.m`, `.mm` | Full support |
| Visual Basic 6 | `.bas`, `.cls`, `.frm` | Full support |
| HTML | `.html`, `.htm` | Full support |
