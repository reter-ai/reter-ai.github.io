---
layout: doc
title: Features
---

# Tools

Codeine provides MCP tools for code reasoning and analysis.

## Thinking & Reasoning

| Tool | Description |
|------|-------------|
| `thinking` | Record reasoning steps, analysis, decisions |
| `session` | Manage reasoning sessions (start, context, end) |
| `items` | Query and manage thoughts, requirements, tasks |
| `project` | Project analytics (health, critical path, impact) |

### thinking

Record structured reasoning steps with thought chains.

```javascript
await thinking({
  thought: "Analyzing the authentication module",
  thought_number: 1,
  total_thoughts: 3,
  thought_type: "analysis"
})
```

### session

Manage reasoning sessions with persistence.

```javascript
// Start a new session
await session({ action: "start", goal: "Refactor auth module" })

// Get current context
await session({ action: "context" })

// End session
await session({ action: "end" })
```

## Code Analysis

| Tool | Description |
|------|-------------|
| `code_inspection` | Python code analysis (26 actions) |
| `recommender` | Refactoring and test coverage recommendations |
| `diagram` | Generate UML diagrams (class, sequence, etc.) |

### code_inspection

Analyze code structure with 26 available actions:

- `list_modules` - List all modules
- `list_classes` - List all classes
- `describe_class` - Get detailed class info
- `get_class_hierarchy` - Inheritance hierarchy
- `find_usages` - Find where code is used
- `find_callers` - Find all callers
- `find_callees` - Find all callees
- `analyze_dependencies` - Module dependencies
- `get_complexity` - Complexity metrics
- `get_architecture` - Architecture overview

```javascript
await code_inspection({
  action: "list_classes"
})

await code_inspection({
  action: "describe_class",
  target: "MyClass"
})
```

### recommender

Get refactoring and test coverage recommendations.

```javascript
await recommender({
  recommender_type: "refactoring"
})

await recommender({
  recommender_type: "test_coverage"
})
```

### diagram

Generate UML diagrams in Mermaid format.

**Diagram types:**
- `class_hierarchy` - Inheritance tree
- `class_diagram` - Class with methods
- `sequence` - Method call sequence
- `dependencies` - Module dependencies

```javascript
await diagram({
  diagram_type: "class_hierarchy",
  target: "BaseClass"
})
```

## Instance Management

| Tool | Description |
|------|-------------|
| `instance_manager` | Manage RETER instances and sources |

### instance_manager

Manage multiple RETER instances for different projects.

```javascript
await instance_manager({
  action: "list"
})
```

## Supported Languages

| Language | Extensions |
|----------|------------|
| Python | `.py` |
| C# | `.cs` |
| C++ | `.cpp`, `.hpp`, `.h`, `.cc` |
| JavaScript | `.js` |
