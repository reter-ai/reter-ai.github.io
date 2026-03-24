---
layout: page
title: About
---

# About RETER

Making AI-generated code secure and maintainable.

The name comes from the **RETE algorithm** — the forward-chaining pattern matching engine at its core. RETER *RETEs your code*: it feeds source files through a symbolic reasoning engine and what comes out the other end is a formal code ontology.

## The Problem

AI coding agents are **blind** — to security and to architecture. They generate code fast, but they don't see trust boundaries, injection surfaces, class hierarchies, layer violations, or the 2,000-line god class they just made worse.

They pass untrusted input to shells. They leak credentials through HTTP headers. They build manual parsers vulnerable to request smuggling. They duplicate logic that already exists three directories away. They skip authorization checks. They create circular dependencies. They accumulate technical debt with every session — all while producing code that looks clean and passes tests.

**The root cause is simple: agents operate on text, not on structure.** They have no model of the codebase as a whole.

## The Solution

RETER gives AI agents structural visibility by building a **code ontology** — a formal semantic model of the entire codebase — and exposing it through the [Model Context Protocol](https://modelcontextprotocol.io).

The ontology is built with symbolic reasoning and enhanced with **RAG embeddings** and **ML-based clustering**, so agents can reason about trust boundaries, find existing implementations, detect vulnerabilities, and understand the architecture — before writing a single line.

## How It Works

1. **Builds a code ontology** — parses source code into a semantic knowledge graph using language-specific C++ parsers and symbolic reasoning
2. **Maps security architecture** — identifies trust boundaries, authentication flows, credential handling, and injection surfaces
3. **Detects spaghetti** — god classes, feature envy, shotgun surgery, circular dependencies, dead code, hidden duplication across the entire codebase
4. **Runs 130 analysis pipelines** — security audit (command injection, SSRF, credential leaks, OWASP Top 10), code smell detection, refactoring opportunities, architecture violations
5. **Classifies findings** — AI agent triages with CWE classification for vulnerabilities, severity ranking for code smells, separating true positives from noise
6. **Guides fixes** — the ontology directs where to add validation, which class to extract, which method to inline, which trust boundary to enforce
7. **Meta prompting** — workflow prompts orchestrate the agent through structured multi-phase analysis. Prompts and their linked scripts co-evolve through a genetic algorithm — crossover, mutation, tournament selection — getting more precise with every run

## Supported Languages

26 languages with full structural analysis: Python, JavaScript, Java, C#, C++, Go, Rust, Swift, Scala, PHP, Haskell, Kotlin, R, Ruby, Dart, Erlang, Objective-C, Visual Basic 6, Delphi, Ada, Lua, XAML, HTML, Bash, and more.
