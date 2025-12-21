---
layout: doc
title: Examples
---

# Examples

Real-world examples of using Codeine for code analysis and refactoring.

## Analyzing Project Architecture

Get a high-level view of your codebase:

```javascript
// Get architecture overview
await code_inspection({
  action: "get_architecture",
  format: "markdown"
})
```

This returns:
- Module count by directory
- Largest modules by class count
- Hub classes (most inherited from)
- Exception hierarchy

## Finding Code Smells

Detect potential issues in your codebase:

```javascript
// Find God classes (too many methods)
await recommender({
  recommender_type: "refactoring",
  detector_name: "find_large_classes",
  params: { threshold: 15 }
})

// Find circular imports
await recommender({
  recommender_type: "refactoring",
  detector_name: "find_circular_imports"
})

// Find feature envy
await recommender({
  recommender_type: "refactoring",
  detector_name: "detect_feature_envy"
})
```

## Understanding a Class

Deep dive into a specific class:

```javascript
// Describe the class
await code_inspection({
  action: "describe_class",
  target: "UserService",
  include_methods: true,
  include_attributes: true
})

// Find all usages
await code_inspection({
  action: "find_usages",
  target: "UserService"
})

// Get class hierarchy
await code_inspection({
  action: "get_class_hierarchy",
  target: "UserService"
})
```

## Generating UML Diagrams

Visualize code structure:

```javascript
// Class hierarchy diagram
await diagram({
  diagram_type: "class_hierarchy",
  target: "BaseService",
  format: "mermaid"
})

// Full class diagram with methods
await diagram({
  diagram_type: "class_diagram",
  classes: ["UserService", "AuthService", "DatabaseService"],
  include_methods: true
})

// Sequence diagram
await diagram({
  diagram_type: "sequence",
  target: "process_request",
  max_depth: 5
})
```

## Semantic Code Search

Find code by description:

```javascript
// Search for authentication-related code
await semantic_search({
  query: "password validation and hashing",
  limit: 5
})

// Search for error handling
await semantic_search({
  query: "exception handling and error logging"
})
```

## Planning Refactoring Work

Use the thinking tool for structured planning:

```javascript
// Start a refactoring plan
await thinking({
  thought: "Planning to refactor the large UserService class",
  thought_number: 1,
  total_thoughts: 4,
  thought_type: "planning",
  operations: {
    task: {
      name: "Extract authentication methods",
      priority: "high",
      duration_days: 2
    }
  }
})

// Create additional tasks
await thinking({
  thought: "Identifying methods to move to AuthService",
  thought_number: 2,
  total_thoughts: 4,
  thought_type: "analysis"
})

// Generate Gantt chart
await diagram({
  diagram_type: "gantt",
  format: "mermaid"
})
```

## Change Impact Analysis

Understand the impact of changes:

```javascript
// Predict impact of changing a function
await code_inspection({
  action: "predict_impact",
  target: "calculate_total"
})

// Find all callers (recursive)
await code_inspection({
  action: "find_callers",
  target: "database_query"
})
```

## Cross-Language Analysis

Analyze multi-language projects:

```javascript
// List all JavaScript classes
await code_inspection({
  action: "list_classes",
  language: "javascript"
})

// Find Python modules
await code_inspection({
  action: "list_modules",
  language: "python"
})

// Language-independent query (all languages)
await code_inspection({
  action: "get_complexity",
  language: "oo"  // Object-oriented, matches all
})
```
