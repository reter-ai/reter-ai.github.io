---
layout: doc
title: Examples
---

# Examples

Real-world examples of using Reter Code for code reasoning and analysis.

## Starting a Reasoning Session

```javascript
// Start a new session with a goal
await session({
  action: "start",
  goal: "Analyze and refactor the authentication module"
})

// Record your first thought
await thinking({
  thought: "First, I need to understand the current auth structure",
  thought_number: 1,
  total_thoughts: 4,
  thought_type: "planning"
})
```

## Analyzing Code Structure

```javascript
// List all classes in the project
await code_inspection({
  action: "list_classes"
})

// Get details about a specific class
await code_inspection({
  action: "describe_class",
  target: "UserService"
})

// Find who calls a function
await code_inspection({
  action: "find_callers",
  target: "authenticate"
})
```

## Getting Recommendations

```javascript
// Get refactoring recommendations
await recommender({
  recommender_type: "refactoring"
})

// Get test coverage recommendations
await recommender({
  recommender_type: "test_coverage"
})
```

## Generating Diagrams

```javascript
// Class hierarchy diagram
await diagram({
  diagram_type: "class_hierarchy",
  target: "BaseService"
})

// Sequence diagram
await diagram({
  diagram_type: "sequence",
  target: "process_request"
})

// Module dependencies
await diagram({
  diagram_type: "dependencies"
})
```

## Recording Analysis

```javascript
// Continue reasoning with findings
await thinking({
  thought: "Found 3 classes that handle auth: UserService, AuthManager, TokenValidator",
  thought_number: 2,
  total_thoughts: 4,
  thought_type: "analysis"
})

// Record a decision
await thinking({
  thought: "Will consolidate auth logic into AuthService",
  thought_number: 3,
  total_thoughts: 4,
  thought_type: "decision"
})
```

## Ending a Session

```javascript
// Get session context at any time
await session({
  action: "context"
})

// End the session (persists all data)
await session({
  action: "end"
})
```

## Managing Instances

```javascript
// List all RETER instances
await instance_manager({
  action: "list"
})
```
