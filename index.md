---
layout: home
title: Home
---

<div class="hero-modern hero-stacked">
  <div class="hero-content-modern hero-content-centered">
    <div class="badge">Symbolic Intelligence | Security Audit | Code Quality</div>
    <h1 class="hero-title-modern">
      Make AI-Generated Code<br>
      <span class="gradient-text">Secure & Maintainable</span>
    </h1>
    <p class="hero-subtitle-modern">
      AI agents write code fast. RETER makes sure it's secure and clean &mdash; catching vulnerabilities, spaghetti architecture, god classes, and hidden duplication before they ship.
    </p>
    <div class="hero-buttons-modern">
      <a href="#contact" class="btn-modern btn-primary-modern">Get Started</a>
      <a href="#contact" class="btn-modern btn-secondary-modern">Contact Us</a>
    </div>
  </div>
</div>

<div class="stats-section">
  <div class="stat-item">
    <div class="stat-number">130</div>
    <div class="stat-label">Analysis Pipelines</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">&mdash;</div>
    <div class="stat-label">Symbolic Intelligence</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">26</div>
    <div class="stat-label">Languages</div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">The Shift</span>
    <h2>The Bottleneck<br><span class="gradient-text">Has Moved</span></h2>
  </div>

  <p style="max-width: 720px; margin: 0 auto 2rem; text-align: center; font-size: 1.15rem; line-height: 1.7; color: var(--color-text-secondary, #94a3b8);">
    Writing code used to be the bottleneck. AI solved that. Now the bottleneck is <strong style="color: #000;">understanding</strong> &mdash; knowing what already exists, how it fits together, where the security boundaries are, and what will break if you change it. Agents that can't see the codebase as a whole produce code that's fast to write and expensive to maintain.
  </p>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">The Problem</span>
    <h2>AI Agents Ship<br><span class="gradient-text">Vulnerable Spaghetti</span></h2>
  </div>

  <div class="tech-grid">
    <div class="tech-item">
      <h4>They Introduce Vulnerabilities</h4>
      <p>Command injection, SSRF, credential leaks, request smuggling &mdash; AI agents produce code with security flaws they can't see.</p>
    </div>
    <div class="tech-item">
      <h4>They Cross Trust Boundaries</h4>
      <p>Mixing untrusted input with privileged operations, passing user data straight to shells and databases.</p>
    </div>
    <div class="tech-item">
      <h4>They Create God Classes</h4>
      <p>Dumping everything into whatever file is open. 2,000-line classes with 40 methods that handle auth, logging, parsing, and business logic all at once.</p>
    </div>
    <div class="tech-item">
      <h4>They Duplicate Instead of Reuse</h4>
      <p>Writing new auth handlers, HTTP parsers, and validators instead of using the hardened ones that already exist three directories away.</p>
    </div>
    <div class="tech-item">
      <h4>They Ignore Architecture</h4>
      <p>No awareness of layers, boundaries, or patterns. Calling infrastructure from presentation. Mixing concerns freely. The result is untraceable spaghetti.</p>
    </div>
    <div class="tech-item">
      <h4>They Reinvent Patterns</h4>
      <p>Every agent session starts from scratch. Established design patterns, naming conventions, and project structure are invisible to them.</p>
    </div>
    <div class="tech-item">
      <h4>They Skip Authorization</h4>
      <p>API endpoints without ownership checks. gRPC handlers without caller validation. Sandbox operations without permission gates.</p>
    </div>
    <div class="tech-item">
      <h4>They Accumulate Debt</h4>
      <p>Each session adds more code, more duplication, more coupling. Without structural awareness, every change makes the next one harder.</p>
    </div>
  </div>
</div>

<div class="section-dark">
  <div class="section-header">
    <span class="section-badge">The Solution</span>
    <h2>Symbolic Intelligence +<br><span class="gradient-text">Security Analysis</span></h2>
  </div>

  <div class="features-grid-modern">
    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-shield-halved"></i></div>
      <h3>Security Audit</h3>
      <p>Automated detection of command injection, SSRF, credential exposure, request smuggling, and OWASP Top 10 vulnerabilities &mdash; with CWE classification and proof-of-concept generation.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-diagram-project"></i></div>
      <h3>Code Ontology</h3>
      <p>A formal semantic model of your entire codebase &mdash; trust boundaries, dependency chains, class hierarchies, layer boundaries &mdash; built with symbolic reasoning.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-brain"></i></div>
      <h3>RAG & ML</h3>
      <p>Semantic similarity search finds existing implementations before the agent writes a new one. Clustering detects hidden duplication across the entire codebase.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-broom"></i></div>
      <h3>Spaghetti Untangler</h3>
      <p>God class detection, feature envy analysis, shotgun surgery tracking, long method extraction &mdash; 130 pipelines that find the mess and tell the agent exactly how to clean it up.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-layer-group"></i></div>
      <h3>Architecture Guard</h3>
      <p>Enforces layer boundaries, detects circular dependencies, and prevents cross-concern coupling. The agent sees the architecture before it writes a single line.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-magnifying-glass-chart"></i></div>
      <h3>Dead Code & Drift</h3>
      <p>Finds uncalled methods, orphaned classes, unused imports, and code that drifted from its original design intent. Less code, fewer attack surfaces.</p>
    </div>

    <div class="feature-card-modern">
      <div class="feature-icon"><i class="fa-solid fa-wand-magic-sparkles"></i></div>
      <h3>Meta Prompting</h3>
      <p>Workflow prompts that orchestrate the AI agent through structured multi-phase analysis. Prompts and their linked analysis scripts co-evolve through a genetic algorithm &mdash; crossover, mutation, selection &mdash; getting sharper with every run.</p>
    </div>
  </div>
</div>

<div class="section-light">
  <div class="section-header">
    <span class="section-badge">Workflow</span>
    <h2>Detect &rarr; Classify &rarr; <span class="gradient-text">Fix</span></h2>
  </div>

  <div class="use-cases-grid">
    <div class="use-case-card">
      <div class="use-case-label">PHASE 1</div>
      <h3>Detect</h3>
      <p>130 pipelines scan the entire codebase: injection surfaces, credential flaws, god classes, dead code, circular dependencies, duplicated logic, missing authorization.</p>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">PHASE 2</div>
      <h3>Classify</h3>
      <p>The AI agent reads actual code, triages each finding &mdash; CWE classification for vulnerabilities, severity ranking for code smells &mdash; and separates true positives from noise.</p>
    </div>

    <div class="use-case-card">
      <div class="use-case-label">PHASE 3</div>
      <h3>Fix</h3>
      <p>The ontology guides every fix: where to add input validation, which class to extract, which method to inline, which trust boundary to enforce. The agent refactors with full architectural context.</p>
    </div>
  </div>
</div>

<div class="section-dark" id="contact">
  <div class="section-header">
    <span class="section-badge">Contact</span>
    <h2>Get in <span class="gradient-text">Touch</span></h2>
  </div>
  <div class="contact-form-wrapper">
    <form action="https://formspree.io/f/xzdadwog" method="POST" class="contact-form">
      <div class="form-row">
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" name="name" required placeholder="Your name">
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" name="_replyto" required placeholder="your@email.com">
        </div>
      </div>
      <div class="form-group">
        <label for="subject">Subject</label>
        <input type="text" id="subject" name="subject" required placeholder="What is this about?">
      </div>
      <div class="form-group">
        <label for="message">Message</label>
        <textarea id="message" name="message" rows="5" required placeholder="Your message..."></textarea>
      </div>
      <input type="hidden" name="_subject" value="RETER Contact Form">
      <button type="submit" class="btn-modern btn-primary-modern">Send Message</button>
    </form>
  </div>
</div>

<div class="cta-modern">
  <h2>Secure code. Clean architecture.<br>No more spaghetti.</h2>
  <p>Give your AI agent the visibility it's missing.</p>
  <div class="cta-buttons">
    <a href="#contact" class="btn-modern btn-primary-modern btn-large">Get Started</a>
    <a href="#contact" class="btn-modern btn-secondary-modern btn-large">Contact Us</a>
  </div>
</div>
