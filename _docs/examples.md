---
layout: doc
title: Examples
---

# Examples

Real-world examples of using Reter Code for codebase analysis, redundancy detection, and refactoring.

## Finding Redundant Code

The most common workflow — scan the codebase for duplicate code and create review tasks.

```python
# Dry run first — see what would be detected without creating tasks
execute_cadsl(
    script="cadsl/tools/good/redundant_code_tasks.cadsl",
    params={"min_similarity": 0.75, "limit": 50, "dry_run": True}
)

# Create review tasks for detected duplicates
execute_cadsl(
    script="cadsl/tools/good/redundant_code_tasks.cadsl",
    params={"min_similarity": 0.75, "limit": 50, "dry_run": False}
)
```

The pipeline:
1. RAG pairwise duplicate detection across all files
2. Filters false positives (boilerplate, visitors, tests)
3. Ranks by similarity score
4. Creates review tasks with file locations and classification guidance

## Finding Extraction Opportunities

Use DBSCAN density-based clustering to find groups of similar methods that could be extracted.

```python
execute_cadsl(
    script="cadsl/tools/good/extraction_opportunities_dbscan.cadsl",
    params={"eps": 0.5, "min_samples": 2, "file_filter": ".py", "dry_run": False}
)
```

DBSCAN finds natural clusters of redundant implementations without specifying cluster count upfront — it discovers how many groups exist automatically.

## Detecting Code Smells

```python
# God classes — too many methods
execute_cadsl(
    script="cadsl/tools/smells/god_class.cadsl",
    params={"min_methods": 15}
)

# Long methods
execute_cadsl(
    script="cadsl/tools/smells/long_method.cadsl",
    params={"min_lines": 50}
)

# Large files
execute_cadsl(
    script="cadsl/tools/smells/large_file_tasks.cadsl",
    params={"max_lines": 500, "max_classes": 1, "dry_run": False}
)

# Dead code
execute_cadsl(script="cadsl/tools/smells/dead_code.cadsl")

# Feature envy
execute_cadsl(script="cadsl/tools/smells/feature_envy.cadsl")
```

## Asking Questions in Natural Language

No need to learn CADSL or REQL — just ask in plain English.

```python
# Structural questions
natural_language_query("Which classes have more than 20 methods?")
natural_language_query("Find all classes that inherit from BaseService")
natural_language_query("Show methods that call both database and HTTP services")

# Redundancy questions
natural_language_query("Find duplicate code that could be extracted into shared functions")
natural_language_query("Which methods have similar implementations across different files?")

# Architecture questions
natural_language_query("Show me the call graph for the authentication module")
natural_language_query("Find circular dependencies between modules")
natural_language_query("What are the entry points to the system?")

# Testing questions
natural_language_query("Find untested public methods in the services layer")
natural_language_query("Which classes have no test coverage?")
```

The Claude subagent:
1. Classifies the question as REQL, CADSL, or RAG
2. Searches 130 example pipelines for the closest match
3. Generates a new query using the grammar and schema
4. Tests it against the live knowledge graph
5. Retries on errors — up to 5 attempts

## Semantic Search

Find code by meaning, not just keywords.

```python
# Find code related to authentication
semantic_search("authentication and JWT tokens")

# Find error handling patterns
semantic_search("error handling", entity_types=["method", "function"])

# Search specific directory
semantic_search("database connection", file_filter="src/db/**")

# Find documentation sections
semantic_search("installation guide", search_scope="docs")
```

## Generating Architecture Diagrams

```python
# Architecture diagram from semantic annotations
execute_cadsl(
    script="cadsl/tools/good/architecture_diagram.cadsl",
    params={"columns": 4, "max_classes_per_layer": 12}
)

# Class diagram
execute_cadsl(
    script="cadsl/tools/inspection/class_diagram.cadsl",
    params={"class_name": "AuthService"}
)

# Dependency graph
execute_cadsl(script="cadsl/tools/inspection/dependency_graph.cadsl")

# Call graph
execute_cadsl(
    script="cadsl/tools/inspection/call_graph.cadsl",
    params={"method_name": "process_request"}
)
```

## REQL Queries

Query the knowledge graph directly with SPARQL-like syntax.

```python
# Find all classes with their method counts
reql(query="""
    SELECT ?class_name ?method_count
    WHERE {
        ?class type class .
        ?class has-name ?class_name .
        ?class has-method-count ?method_count .
        FILTER(?method_count > 10)
    }
    ORDER BY DESC(?method_count)
""")

# Find inheritance relationships
reql(query="""
    SELECT ?child ?parent
    WHERE {
        ?c type class .
        ?c has-name ?child .
        ?p type class .
        ?p has-name ?parent .
        ?c subclass-of ?p
    }
""")

# Find classes in a specific layer
reql(query="""
    SELECT ?class_name ?layer
    WHERE {
        ?class type class .
        ?class has-name ?class_name .
        ?class is-in-layer ?layer
    }
    ORDER BY ?layer ?class_name
""")
```

## Classifying Review Tasks

After detection pipelines create tasks, classify each one:

```python
# List pending review tasks
items(action="list", category="smell-review", status="pending")

# Get task details
items(action="get", item_id="TASK-001", include_relations=True)

# Classify as true positive — creates follow-up implementation task
items(
    action="classify",
    item_id="TASK-001",
    classification="TP-EXTRACT",
    notes="Both methods parse CSV with identical logic, extract to shared utility",
    create_followup=True
)

# Classify as false positive
items(
    action="classify",
    item_id="TASK-002",
    classification="FP-INTERFACE",
    notes="Same interface pattern but different implementations — Template Method"
)
```

## Session Management

```python
# Restore state at the start of every conversation
session(action="context")

# Start a new refactoring session
session(action="start", goal="Reduce code redundancy in auth module")

# Record reasoning steps
thinking(
    thought="Found 3 clusters of duplicate auth validation logic",
    thought_number=1,
    total_thoughts=4,
    thought_type="analysis",
    section="context"
)

# End session
session(action="end")
```
