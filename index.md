---
layout: home
title: Home
---

<div class="announcement-bar">
  <p>AI-Powered Code Reasoning MCP Server for Claude Code</p>
</div>

<div class="hero-modern">
  <div class="hero-content-modern">
    <div class="badge">RETER Engine | MCP Protocol | Multi-Language Support</div>
    <h1 class="hero-title-modern">
      <span class="gradient-text">Codeine</span><br>
      <span class="gradient-text-alt">Code Intelligence</span>
    </h1>
    <p class="hero-subtitle-modern">
      MCP server for Claude Code that provides semantic code analysis, refactoring detection,
      RAG-powered search, and intelligent reasoning. Supports Python, JavaScript, C#, C++, Go, Rust, and HTML.
    </p>
    <div class="hero-buttons-modern">
      <a href="/docs/getting-started" class="btn-modern btn-primary-modern">Get Started</a>
      <a href="https://github.com/codeine-ai/codeine" class="btn-modern btn-secondary-modern">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
        </svg>
        View on GitHub
      </a>
    </div>
    <div class="social-proof">
      <p>7 Languages | 70+ Refactoring Detectors | RAG Semantic Search | UML Diagrams</p>
    </div>
  </div>
  <div class="hero-visual">
    <div class="code-preview">
      <div class="code-header">
        <span class="code-dot"></span>
        <span class="code-dot"></span>
        <span class="code-dot"></span>
      </div>
      <pre><code><span class="code-comment"># Analyze architecture with Codeine</span>
<span class="code-keyword">await</span> <span class="code-function">code_inspection</span>({
  action: <span class="code-string">"get_architecture"</span>,
  format: <span class="code-string">"mermaid"</span>
})

<span class="code-comment"># Find refactoring opportunities</span>
<span class="code-keyword">await</span> <span class="code-function">recommender</span>({
  recommender_type: <span class="code-string">"refactoring"</span>,
  detector_name: <span class="code-string">"find_large_classes"</span>
})

<span class="code-comment"># Semantic RAG search</span>
<span class="code-keyword">await</span> <span class="code-function">semantic_search</span>({
  query: <span class="code-string">"authentication logic"</span>
})</code></pre>
    </div>
  </div>
</div>

<div class="stats-section">
  <div class="stat-item">
    <div class="stat-number">7</div>
    <div class="stat-label">Languages</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">70+</div>
    <div class="stat-label">Refactoring Detectors</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">699</div>
    <div class="stat-label">Classes Analyzed</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">4907</div>
    <div class="stat-label">Functions Indexed</div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">Core Capabilities</span>
    <h2>Intelligent Code<br><span class="gradient-text">Understanding</span></h2>
  </div>

  <div class="features-grid-modern">
    <div class="feature-card-modern">
      <div class="feature-icon">🔍</div>
      <h3>Semantic Code Analysis</h3>
      <p>Deep understanding of code structure using RETER reasoning engine. Extracts classes, functions, inheritance, call graphs, and dependencies.</p>
      <div class="feature-highlight">
        <code>code_inspection • describe_class • find_callers</code>
      </div>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon">🛠️</div>
      <h3>Refactoring Detection</h3>
      <p>70+ detectors based on Martin Fowler's patterns. Find God classes, feature envy, shotgun surgery, circular imports, and more.</p>
      <div class="feature-highlight">
        <code>recommender • find_large_classes • detect_feature_envy</code>
      </div>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon">🧠</div>
      <h3>RAG Semantic Search</h3>
      <p>FAISS-powered vector embeddings for natural language code search. Find relevant code by describing what you need.</p>
      <div class="feature-highlight">
        <code>semantic_search • rag_reindex • find_similar</code>
      </div>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon">📊</div>
      <h3>UML Diagrams</h3>
      <p>Generate class hierarchies, class diagrams with relationships, sequence diagrams, and dependency graphs in Mermaid format.</p>
      <div class="feature-highlight">
        <code>diagram • class_hierarchy • sequence • dependencies</code>
      </div>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon">💭</div>
      <h3>Structured Reasoning</h3>
      <p>Thinking tool for step-by-step analysis. Create requirements, tasks, decisions with traceability. Gantt charts for project planning.</p>
      <div class="feature-highlight">
        <code>thinking • items • project • traceability</code>
      </div>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon">🌐</div>
      <h3>Multi-Language Support</h3>
      <p>Analyze Python, JavaScript/TypeScript, C#, C++, Go, Rust, and HTML. Language-specific and cross-language queries.</p>
      <div class="feature-highlight">
        <code>python • javascript • csharp • cpp • go • rust</code>
      </div>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">Architecture</span>
    <h2>How Codeine Works</h2>
    <p style="color: var(--text-secondary); font-size: 1.125rem; max-width: 700px; margin: 1rem auto 0;">
      Three-layer architecture combining MCP server, Python reasoning wrapper, and C++ RETER engine for maximum performance.
    </p>
  </div>

  <div class="tech-grid">
    <div class="tech-item">
      <h4>MCP Server Layer</h4>
      <p>Claude Code integration with tools, resources, and prompts. Session management and instance coordination.</p>
    </div>
    <div class="tech-item">
      <h4>RETER Python Wrapper</h4>
      <p>High-level API for reasoning, queries, and code analysis. Manages knowledge graphs and inference rules.</p>
    </div>
    <div class="tech-item">
      <h4>RETER C++ Core</h4>
      <p>RETE algorithm implementation for fast pattern matching. OWL 2 RL and SWRL rule execution.</p>
    </div>
    <div class="tech-item">
      <h4>ANTLR4 Parsers</h4>
      <p>Language-specific parsing for Python, JavaScript, C#, C++, Go, Rust, and HTML.</p>
    </div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">Quick Start</span>
    <h2>Get Running in Minutes</h2>
  </div>

  <div class="tech-grid">
    <div class="tech-item">
      <h4>1. Clone Repository</h4>
      <p>git clone https://github.com/codeine-ai/codeine</p>
    </div>
    <div class="tech-item">
      <h4>2. Install Dependencies</h4>
      <p>pip install -e . (or use install.bat on Windows)</p>
    </div>
    <div class="tech-item">
      <h4>3. Configure Claude Code</h4>
      <p>Add MCP server to claude_desktop_config.json</p>
    </div>
    <div class="tech-item">
      <h4>4. Start Analyzing</h4>
      <p>Use code_inspection, recommender, and thinking tools</p>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">Use Cases</span>
    <h2>From Analysis<br>to Action</h2>
  </div>

  <div class="use-cases-grid">
    <div class="use-case-card">
      <div class="use-case-label">CODE QUALITY</div>
      <h3>Refactoring Guidance</h3>
      <p>Detect code smells, find refactoring opportunities, and get step-by-step guidance based on Martin Fowler's patterns.</p>
      <a href="/docs/features" class="use-case-link">Learn More →</a>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">ARCHITECTURE</div>
      <h3>Codebase Understanding</h3>
      <p>Visualize class hierarchies, dependency graphs, and module structure. Understand complex codebases quickly.</p>
      <a href="/docs/features" class="use-case-link">Learn More →</a>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">SEARCH</div>
      <h3>Semantic Code Search</h3>
      <p>Find code by describing what you need in natural language. RAG-powered search across your entire codebase.</p>
      <a href="/docs/features" class="use-case-link">Learn More →</a>
    </div>
  </div>
</div>

<div class="cta-modern">
  <h2>Make your AI assistant<br>understand your code.</h2>
  <p>Install Codeine and give Claude Code deep insight into your codebase.</p>
  <div class="cta-buttons">
    <a href="/docs/getting-started" class="btn-modern btn-primary-modern btn-large">Get Started</a>
    <a href="/docs/features" class="btn-modern btn-secondary-modern btn-large">View Features</a>
  </div>
</div>
