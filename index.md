---
layout: home
title: Home
---

<div class="announcement-bar">
  <p>MCP Server for Claude Code and Claude Desktop</p>
</div>

<div class="hero-modern">
  <div class="hero-content-modern">
    <div class="badge">Code Ontology | CADSL Pipelines | RAG + ML</div>
    <h1 class="hero-title-modern">
      <span class="gradient-text">Architectural</span><br>
      <span class="gradient-text-alt">Visibility</span>
      for AI Agents
    </h1>
    <p class="hero-subtitle-modern">
      The name comes from the <strong>RETE algorithm</strong> &mdash; the forward-chaining pattern matching engine at its core.
      RETER <em>RETEs your code</em>: it feeds source files through a RETE network of 70+ OWL 2 RL inference rules
      and what comes out the other end is a formal code ontology.
    </p>
    <div class="hero-buttons-modern">
      <a href="/docs/getting-started" class="btn-modern btn-primary-modern">Get Started</a>
      <a href="https://github.com/reter-ai/reter_code" class="btn-modern btn-secondary-modern">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
        </svg>
        View on GitHub
      </a>
    </div>
    <div class="social-proof">
      <p>Code Ontology | 130 CADSL Pipelines | RAG Embeddings | Refactoring Workflow</p>
    </div>
  </div>
  <div class="hero-visual">
    <div class="code-preview">
      <div class="code-header">
        <span class="code-dot"></span>
        <span class="code-dot"></span>
        <span class="code-dot"></span>
      </div>
      <pre><code><span class="code-comment"># Terminal 1: Start the RETER server</span>
<span class="code-comment">$</span> <span class="code-keyword">reter_server</span> <span class="code-string">--project /my/project</span>
  ✓ RETE network initialized
  ✓ 234 sources loaded into ontology
  ✓ RAG embeddings built (FAISS)
  ✓ ZeroMQ bound on tcp://127.0.0.1:5555

<span class="code-comment"># Terminal 2: Use Claude as usual</span>
<span class="code-comment">$</span> <span class="code-keyword">claude</span>
<span class="code-comment">&gt;</span> Find redundant code across the codebase

<span class="code-function">● reter:execute_cadsl</span>
  <span class="code-string">script="redundant_code_tasks.cadsl"</span>
  Created 42 review tasks</code></pre>
    </div>
  </div>
</div>

<div class="stats-section">
  <div class="stat-item">
    <div class="stat-number">130</div>
    <div class="stat-label">CADSL Pipelines</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">70+</div>
    <div class="stat-label">OWL 2 RL Rules</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">4+</div>
    <div class="stat-label">Languages</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">12</div>
    <div class="stat-label">Analysis Categories</div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">The Problem</span>
    <h2>AI Agents Are<br><span class="gradient-text">Architecturally Blind</span></h2>
  </div>

  <div class="tech-grid">
    <div class="tech-item">
      <h4>They Duplicate Code</h4>
      <p>Code that already exists three directories away gets written again.</p>
    </div>
    <div class="tech-item">
      <h4>They Reinvent Patterns</h4>
      <p>Instead of following established patterns, they create new ones.</p>
    </div>
    <div class="tech-item">
      <h4>They Cross Layers</h4>
      <p>Calling infrastructure from presentation, mixing concerns freely.</p>
    </div>
    <div class="tech-item">
      <h4>They Create God Classes</h4>
      <p>Adding methods to whatever file is open rather than finding the right home.</p>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">The Solution</span>
    <h2>Code Ontology +<br><span class="gradient-text">RAG & ML</span></h2>
  </div>

  <div class="features-grid-modern">
    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-diagram-project"></i></div>
      <h3>Code Ontology</h3>
      <p>Parses source code into a formal semantic model using OWL 2 RL Description Logic. The RETE engine applies 70+ inference rules to derive implicit relationships &mdash; if A calls B which inherits from C, the ontology knows A depends on C.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-brain"></i></div>
      <h3>RAG & ML Enhancement</h3>
      <p>FAISS vector embeddings capture semantic similarity between code fragments. DBSCAN clustering groups redundant implementations across the codebase &mdash; catching duplication that structural analysis alone misses.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-gears"></i></div>
      <h3>CADSL Pipelines</h3>
      <p>130 pre-built pipelines chain ontology queries with ML-powered enrichment to detect code smells, find duplicates, identify extraction opportunities, and create ranked refactoring task lists.</p>
    </div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">MCP Tools</span>
    <h2>Refactoring Pipeline<br><span class="gradient-text">for AI Agents</span></h2>
  </div>

  <div class="features-grid-modern">
    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-bolt"></i></div>
      <h3>execute_cadsl</h3>
      <p>Run CADSL pipelines &mdash; the primary tool for batch codebase analysis. Chain REQL queries with RAG, ML clustering, and task creation in a single pass.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-language"></i></div>
      <h3>natural_language_query</h3>
      <p>Ask questions in plain English. A Claude subagent translates to CADSL/REQL, tests against the knowledge graph, and retries on errors &mdash; up to 5 attempts.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-magnifying-glass"></i></div>
      <h3>semantic_search</h3>
      <p>Find semantically similar code using FAISS vector similarity. Search by natural language across the entire codebase.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-database"></i></div>
      <h3>reql</h3>
      <p>Execute REQL queries directly against the code knowledge graph. SPARQL-like triple patterns over classes, methods, calls, inheritance.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-code"></i></div>
      <h3>code_inspection</h3>
      <p>Multi-language code analysis for Python, JavaScript, C#, and C++. List classes, find callers, analyze dependencies, get complexity metrics.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-wand-magic-sparkles"></i></div>
      <h3>recommender</h3>
      <p>Generate refactoring and redundancy reduction recommendations. Test coverage analysis and extraction opportunities.</p>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">Workflow</span>
    <h2>Detect &rarr; Classify<br>&rarr; <span class="gradient-text">Implement</span></h2>
  </div>

  <div class="use-cases-grid">
    <div class="use-case-card">
      <div class="use-case-label">PHASE 1</div>
      <h3>Detect</h3>
      <p>CADSL pipelines scan the entire codebase for redundant code, extraction opportunities, code smells, and architectural violations. Each detector creates review tasks with file locations and classification guidance.</p>
      <a href="/docs/examples" class="use-case-link">See Examples &rarr;</a>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">PHASE 2</div>
      <h3>Classify</h3>
      <p>The AI agent reads actual code and classifies each finding: TP-EXTRACT, TP-PARAMETERIZE, FP-INTERFACE, FP-LAYERS, FP-STRUCTURAL, or FP-TRIVIAL. True positives generate follow-up implementation tasks.</p>
      <a href="/docs/features" class="use-case-link">Learn More &rarr;</a>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">PHASE 3</div>
      <h3>Implement</h3>
      <p>For each true positive, choose an extraction strategy: private helper, module-level function, base class, utility module, or Template Method pattern. The ontology guides where the code belongs.</p>
      <a href="/docs/features" class="use-case-link">Learn More &rarr;</a>
    </div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">130 Pipelines</span>
    <h2>Built-in Analysis<br><span class="gradient-text">Across 12 Categories</span></h2>
  </div>

  <div class="tech-grid">
    <div class="tech-item">
      <h4>Refactoring (26)</h4>
      <p>Extract method/class, move field, inline class, pull up/push down.</p>
    </div>
    <div class="tech-item">
      <h4>Code Smells (24)</h4>
      <p>God class, long method, feature envy, dead code, shotgun surgery.</p>
    </div>
    <div class="tech-item">
      <h4>Inspection (21)</h4>
      <p>Class hierarchy, callers/callees, API docs, complexity metrics.</p>
    </div>
    <div class="tech-item">
      <h4>RAG Semantic (15)</h4>
      <p>Cross-file duplicates, DBSCAN clusters, orphan helpers, semantic dead code.</p>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">Architecture</span>
    <h2>Two Processes,<br><span class="gradient-text">Connected by ZeroMQ</span></h2>
  </div>

  <div class="use-cases-grid">
    <div class="use-case-card">
      <div class="use-case-label">RETER SERVER</div>
      <h3>reter_server</h3>
      <p>Runs in a separate terminal. Holds the RETE network, builds the code ontology, indexes RAG embeddings, and processes all queries. Stays alive across Claude sessions.</p>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">ZEROMQ</div>
      <h3>tcp://127.0.0.1:5555</h3>
      <p>Binary MessagePack protocol over ZeroMQ REQ/REP sockets. Auto-discovery via <code>.reter_code/server.json</code>. Multiple MCP clients can connect to one server.</p>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">MCP CLIENT</div>
      <h3>reter_code</h3>
      <p>Stateless FastMCP proxy that runs inside Claude. Registers MCP tools and forwards every request to the RETER server. Lightweight, no local state.</p>
    </div>
  </div>
</div>

<div class="cta-modern">
  <h2>Give your AI agent<br>architectural visibility.</h2>
  <p>Install the Reter Code MCP server. Build a code ontology. Stop the spaghetti.</p>
  <div class="cta-buttons">
    <a href="/docs/getting-started" class="btn-modern btn-primary-modern btn-large">Get Started</a>
    <a href="https://github.com/reter-ai/reter_code" class="btn-modern btn-secondary-modern btn-large">View on GitHub</a>
  </div>
</div>
