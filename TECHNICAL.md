
  THE ARCHITECTURE and WORKFLOW:

  Python based application which interact with study files and LLM.

  ┌─────────────────────────────────────────────┐
  │         INTELLIGENT PARSING LAYER           │
  ├─────────────────────────────────────────────┤
  │ • Editcheck Spec Parser (clinical specifications)      │
  │ • Rave ALS Parser (study metadata XML)           │
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
  │ • Template engine      
  │ • Knowledge injection     
  │ • Example selection   
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
