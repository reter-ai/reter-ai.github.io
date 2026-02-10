---
layout: home
title: Home
---

<div class="announcement-bar">
  <p>MCP Server for Claude Code and Claude Desktop</p>
</div>

<div class="hero-modern hero-stacked">
  <div class="hero-content-modern hero-content-centered">
    <div class="badge">Code Ontology | CADSL Pipelines | RAG + ML</div>
    <h1 class="hero-title-modern">
      Turn Vibe Coding into<br>
      <span class="gradient-text">AI Aided Software Engineering</span>
    </h1>
    <p class="hero-subtitle-modern">
      Your AI agent writes code. RETER makes sure it follows your architecture, design patterns, and security boundaries.<br>
      A <strong>code ontology</strong> with 70+ inference rules, semantic search, and 130 analysis pipelines &mdash; exposed as an <strong>MCP server</strong> for Claude Code, Claude Desktop, or any MCP client.
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

  <div class="terminals-grid">
    <div class="terminal-column">
      <div class="use-case-label" style="text-align:center; margin-bottom:0.75rem;">RETER SERVER</div>
      <div class="code-preview rich-console">
        <div class="code-header">
          <span class="code-dot"></span>
          <span class="code-dot"></span>
          <span class="code-dot"></span>
          <span class="code-header-title">reter</span>
        </div>
        <div class="console-body">
          <div class="console-title-bar">
            <span class="ct-name">RETER Server</span> <span class="ct-version">v0.1.3</span>&nbsp;&nbsp;<span class="ct-addr">[tcp://127.0.0.1:5555]</span>
          </div>
          <div class="console-panels">
            <div class="console-panel panel-blue">
              <div class="panel-label panel-label-blue">Status</div>
              <div class="panel-content">
                <div class="panel-row"><span class="pl">Uptime</span><span class="pv-cyan">4h 4m</span></div>
                <div class="panel-row"><span class="pl">Sources</span><span class="pv-green">3,346</span></div>
                <div class="panel-row"><span class="pl">Facts</span><span class="pv-green">1,374,937</span></div>
                <div class="panel-row"><span class="pl">Vectors</span><span class="pv-green">15,497</span></div>
                <div class="panel-spacer"></div>
                <div class="panel-row"><span class="pl">Queries</span><span class="pv">10</span></div>
                <div class="panel-row"><span class="pl">Errors</span><span class="pv">0</span></div>
                <div class="panel-row"><span class="pl">Avg Time</span><span class="pv-green">135ms</span></div>
              </div>
            </div>
            <div class="console-panel panel-blue">
              <div class="panel-label panel-label-blue">Query Log</div>
              <div class="panel-content">
                <div class="panel-row qlog-header"><span class="ql-time">Time</span><span class="ql-method">Method</span><span class="ql-results">Results</span><span class="ql-dur">Time</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:07</span><span class="ql-method pv">system</span><span class="ql-results pv">0</span><span class="ql-dur pv-green">32ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:09</span><span class="ql-method pv">reql</span><span class="ql-results pv">47</span><span class="ql-dur pv-green">18ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:12</span><span class="ql-method pv">cadsl</span><span class="ql-results pv">12</span><span class="ql-dur pv-green">340ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:15</span><span class="ql-method pv">cadsl</span><span class="ql-results pv">8</span><span class="ql-dur pv-green">285ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:18</span><span class="ql-method pv">diagram</span><span class="ql-results pv">1</span><span class="ql-dur pv-green">92ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:20</span><span class="ql-method pv">reql</span><span class="ql-results pv">23</span><span class="ql-dur pv-green">11ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:24</span><span class="ql-method pv">cadsl</span><span class="ql-results pv">42</span><span class="ql-dur pv-yellow">1.2s</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:31</span><span class="ql-method pv">nlq</span><span class="ql-results pv">5</span><span class="ql-dur pv-green">480ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:33</span><span class="ql-method pv">diagram</span><span class="ql-results pv">1</span><span class="ql-dur pv-green">92ms</span></div>
                <div class="panel-row"><span class="ql-time pv-cyan">19:21:35</span><span class="ql-method pv">search</span><span class="ql-results pv">15</span><span class="ql-dur pv-green">64ms</span></div>
              </div>
            </div>
          </div>
          <div class="console-panel panel-yellow panel-full">
            <div class="panel-label panel-label-yellow">Progress</div>
            <div class="panel-content">
              <span class="pv-green">Ready</span> <span class="pv-dim">&mdash; Server is idle, waiting for queries</span>
              <div style="margin-top:0.4rem"><span class="pv-dim">Add MCP to Claude Code:</span></div>
              <div><span class="pv-white">claude mcp add reter -- reter_code</span></div>
            </div>
          </div>
          <div class="console-footer">
            <span class="key-tag">[K]</span><span class="key-label">ompact</span>
            <span class="key-tag">[D]</span><span class="key-label">ebug log</span>
            <span class="key-tag">[N]</span><span class="key-label">lq log</span>
            <span class="key-tag">[S]</span><span class="key-label">ources</span>
            <span class="key-tag">[Ctrl+C]</span><span class="key-label"> Exit</span>
          </div>
        </div>
      </div>
      <p class="terminal-caption">Stateful server: holds the RETE network, code ontology, and RAG embeddings. Stays alive across Claude sessions.</p>
    </div>

    <div class="terminal-column">
      <div class="use-case-label" style="text-align:center; margin-bottom:0.75rem;">CLAUDE + MCP TOOLS</div>
      <div class="code-preview">
        <div class="code-header">
          <span class="code-dot"></span>
          <span class="code-dot"></span>
          <span class="code-dot"></span>
          <span class="code-header-title">claude</span>
        </div>
        <pre><code><span class="code-function">● reter &ndash; system</span> <span class="code-comment">(MCP)</span><span class="code-string"> action: "status"</span>

● RETER is live with <span class="code-keyword">3,346</span> sources, <span class="code-keyword">9,937</span> WMEs, and <span class="code-keyword">15,497</span> RAG vectors. Let me start a fresh session and run all 8 detectors.

<span class="code-function">● reter &ndash; session</span> <span class="code-comment">(MCP)</span>
  <span class="code-string">action: "start", goal: "OpenClaw security audit"</span>

<span class="code-function">● reter &ndash; execute_cadsl</span> <span class="code-comment">(MCP)</span> <span class="code-comment">&times;8</span>
  <span class="code-string">script: "god_class_detector.cadsl"</span>
  <span class="code-string">script: "dead_code_detector.cadsl"</span>
  <span class="code-string">script: "complex_gateway.cadsl"</span>
  <span class="code-comment">... +5 more running in parallel</span>

<span class="code-function">● reter &ndash; natural_language_query</span> <span class="code-comment">(MCP)</span>
  <span class="code-string">"Find classes that handle both network I/O and crypto operations"</span>

<span class="code-function">● reter &ndash; diagram</span> <span class="code-comment">(MCP)</span><span class="code-string"> type: "class", filter: "security"</span>

● Found <span class="code-keyword">23</span> issues across <span class="code-keyword">8</span> detectors. Created <span class="code-keyword">42</span> review tasks.</code></pre>
      </div>
      <p class="terminal-caption">AI agent calls MCP tools to query the ontology, run CADSL pipelines, and create refactoring tasks.</p>
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
    <div class="stat-number">15</div>
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
      <p>Multi-language code analysis across 15 languages including Python, Java, C#, C++, Go, Rust, Swift, and more. List classes, find callers, analyze dependencies, get complexity metrics.</p>
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
      <h3>reter</h3>
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
