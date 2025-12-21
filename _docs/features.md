---
layout: doc
title: Features
---

# Features

Codeine provides a comprehensive set of tools for code analysis, refactoring detection, and semantic reasoning.

## Code Inspection

Analyze code structure and relationships with the `code_inspection` tool.

### Available Actions

| Action | Description |
|--------|-------------|
| `list_modules` | List all modules in the codebase |
| `list_classes` | List all classes, optionally filtered by module |
| `describe_class` | Get detailed class info with methods and attributes |
| `get_class_hierarchy` | Get inheritance hierarchy |
| `find_usages` | Find where a class/method/function is used |
| `find_callers` | Find all callers of a function (recursive) |
| `find_callees` | Find all functions called by a target |
| `analyze_dependencies` | Analyze module dependency graph |
| `get_complexity` | Calculate complexity metrics |
| `get_architecture` | Generate architectural overview |

### Example

```javascript
await code_inspection({
  action: "describe_class",
  target: "MyClass",
  include_methods: true
})
```

## Refactoring Detection

The `recommender` tool detects refactoring opportunities based on Martin Fowler's patterns.

### Available Detectors (70+)

**Code Smells:**
- `find_large_classes` - God classes with too many methods
- `find_long_parameter_lists` - Functions with too many parameters
- `detect_feature_envy` - Methods using other classes' data
- `find_shotgun_surgery` - Changes affecting many files
- `find_circular_imports` - Circular dependency detection

**Refactoring Opportunities:**
- `find_extract_function_opportunities`
- `find_extract_class_opportunities`
- `find_move_function_opportunities`
- `find_duplicate_code`

### Example

```javascript
await recommender({
  recommender_type: "refactoring",
  detector_name: "find_large_classes",
  params: { threshold: 20 }
})
```

## Semantic Search (RAG)

FAISS-powered vector search for finding code by natural language description.

### Tools

| Tool | Description |
|------|-------------|
| `semantic_search` | Search code by natural language query |
| `rag_status` | Check RAG index status |
| `rag_reindex` | Rebuild the semantic index |
| `find_similar_clusters` | Find similar code patterns |

### Example

```javascript
await semantic_search({
  query: "user authentication and login",
  limit: 10
})
```

## UML Diagrams

Generate visual diagrams in Mermaid format.

### Diagram Types

| Type | Description |
|------|-------------|
| `class_hierarchy` | Inheritance tree diagram |
| `class_diagram` | Class with methods and relationships |
| `sequence` | Method call sequence diagram |
| `dependencies` | Module dependency graph |
| `gantt` | Project schedule (from tasks) |

### Example

```javascript
await diagram({
  diagram_type: "class_hierarchy",
  target: "BaseClass",
  format: "mermaid"
})
```

## Thinking Tool

Structured reasoning with traceability.

### Features

- Step-by-step thought chains
- Create requirements, tasks, decisions
- Link items with traces and dependencies
- Generate Gantt charts from tasks

### Example

```javascript
await thinking({
  thought: "Analyzing the authentication module",
  thought_number: 1,
  total_thoughts: 5,
  thought_type: "analysis",
  operations: {
    task: {
      name: "Review auth flow",
      priority: "high"
    }
  }
})
```

## Multi-Language Support

Codeine supports 7 programming languages:

| Language | Extensions | Features |
|----------|------------|----------|
| Python | `.py` | Full analysis, refactoring |
| JavaScript | `.js`, `.ts`, `.tsx` | Classes, functions, modules |
| C# | `.cs` | Classes, interfaces, namespaces |
| C++ | `.cpp`, `.hpp`, `.h` | Classes, templates, namespaces |
| Go | `.go` | Structs, interfaces, packages |
| Rust | `.rs` | Structs, traits, modules |
| HTML | `.html`, `.htm` | DOM structure, scripts |

Use the `language` parameter to filter analysis:

```javascript
await code_inspection({
  action: "list_classes",
  language: "python"  // or "javascript", "csharp", etc.
})
```
