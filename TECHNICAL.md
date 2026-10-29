
  🏗️ THE ARCHITECTURE:

  ┌─────────────────────────────────────────────┐
  │         INTELLIGENT PARSING LAYER           │
  ├─────────────────────────────────────────────┤
  │ • DVS Parser (clinical specifications)      │
  │ • ALS Parser (study metadata XML)           │
  │ • Requirement Extractor (business logic)    │
  │ • Relationship Mapper (cross-form links)    │
  └─────────────┬───────────────────────────────┘
                ↓
  ┌─────────────────────────────────────────────┐
  │       METADATA PROCESSING LAYER             │
  ├─────────────────────────────────────────────┤
  │ • Field property extraction (IsLog, types)  │
  │ • Constraint validation                     │
  │ • Cross-form relationship resolution        │
  │ • Data flow mapping                         │
  └─────────────┬───────────────────────────────┘
                ↓
  ┌─────────────────────────────────────────────┐
  │      STRUCTURED PROMPT GENERATION           │
  ├─────────────────────────────────────────────┤
  │ • Template engine (6-section format)        │
  │ • Knowledge injection (600+ page docs)      │
  │ • Example selection (from 273 production)   │
  │ • Context optimization (token efficiency)   │
  └─────────────┬───────────────────────────────┘
                ↓
  ┌─────────────────────────────────────────────┐
  │          LLM INTERFACE LAYER                │
  ├─────────────────────────────────────────────┤
  │ • Claude Code API (Opus model)              │
  │ • Streaming response handling               │
  │ • Error recovery mechanisms                 │
  │ • Rate limiting & retry logic               │
  └─────────────┬───────────────────────────────┘
                ↓
  ┌─────────────────────────────────────────────┐
  │        VALIDATION ENGINE LAYER              │
  ├─────────────────────────────────────────────┤
  │ • Syntax parser (C# AST analysis)           │
  │ • Pattern matcher (against known good)      │
  │ • Framework compliance (constraints check)  │
  │ • Business logic verifier                   │
  │ • Anti-pattern detector                     │
  └─────────────┬───────────────────────────────┘
                ↓
  ┌─────────────────────────────────────────────┐
  │           OUTPUT GENERATOR                  │
  ├─────────────────────────────────────────────┤
  │ • Code formatter                            │
  │ • Documentation generator                   │
  │ • Deployment file creator (quick edits)     │
  │ • Validation report builder                 │
  └─────────────────────────────────────────────┘

  ⚙️ TECHNICAL STACK:

  Core: Python 3.11+
  Parsing: lxml, regex, custom parsers
  LLM: Claude Code API (Opus model)
  Validation: Python AST, custom rule engine
  Templates: Jinja2 with custom extensions
  Caching: In-memory + file-based
  Logging: Structured logging with context

  📊 PERFORMANCE BENCHMARKS:

  Single Function Generation:
  ├─ Document parsing: ~5s
  ├─ Metadata extraction: ~2s
  ├─ Prompt generation: ~2s
  ├─ LLM inference: ~60s
  ├─ Validation: ~3s
  └─ Total: ~90s (vs 8-12 hours manual)
