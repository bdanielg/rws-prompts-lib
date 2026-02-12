---
title: "research-safe"
description: "Architecture analysis request for legacy codebase"
version: "1.0.0"
author: "dbaylon"
created: "2026-02-12"
tags:
  role: [developer]
  task-type: [architecture-review]
  module: [scaffolds]
  complexity: [expert]
---

# Legacy Codebase Architecture Analysis Request

Please analyze the legacy application codebase using the RWS Context Engine MCP server and produce a complete architectural overview.

## Context

The legacy codebase has been ingested into:
- Neo4j knowledge graph (code relationships, dependencies, patterns)
- MongoDB document store (code entities, metadata, annotations)

Note: Focus on the ingested legacy application, not the rws-context-engine source code itself.

## Research Approach

1. Start with broad queries to understand system structure
2. Use targeted queries for specific components and relationships
3. Traverse the graph to understand dependencies and data flow
4. Query documents for detailed entity information

Assumptions:
- Documentation may be outdated or missing
- Architecture must be inferred from indexed code, relationships, and metadata

## Deliverable Format

Single Markdown document with the following sections. Use Mermaid for all diagrams.

### 1. Executive Summary
- System purpose
- Target users
- High-level architectural style (monolith, layered, event-driven, microservices)

### 2. Codebase Overview
- Total LOC by language and major modules
- Repository structure
- Entry points (main methods, bootstraps, startup scripts)

### 3. Technology Stack
Languages, frameworks, libraries, databases, messaging systems, build tools, runtime/hosting, external services & APIs

### 4. High-Level Architecture Diagram
System-level view showing major components, interactions, data stores, and external dependencies (Mermaid diagram)

### 5. C4 Model Diagrams
Provide applicable levels:
- C1: System Context Diagram
- C2: Container Diagram  
- C3: Component Diagram (per major container)
- C4: Code Diagram (if meaningful)

Each diagram should include element responsibilities (Mermaid format)

### 6. Technical Architecture
- Layering (presentation, domain, infrastructure)
- Dependency directions
- Cross-cutting concerns (auth, logging, config, error handling)

Mermaid diagram required

### 7. Data Architecture
- Databases and schemas (high level)
- Key entities and relationships
- Data flow between components

Mermaid ER or flow diagram required

### 8. Runtime & Deployment
- Production runtime details
- Processes, services, jobs, schedulers
- Environment separation (dev/stage/prod if available)

Mermaid deployment diagram required

### 9. Integration & Communication
- Internal communication patterns (sync/async)
- External integrations
- Protocols (HTTP, messaging, file-based)

### 10. Key Workflows
2-3 critical business/technical flows with step-by-step sequences (Mermaid sequence diagrams)

### 11. Risks & Legacy Concerns
- Tight coupling
- God objects/modules
- Obsolete dependencies
- Scaling or reliability risks

### 12. Assumptions & Unknowns
- Inferred or uncertain conclusions
- Areas requiring domain expert confirmation

### 13. Research Appendix
Document:
- Key queries used to explore the knowledge graph
- Search patterns revealing insights
- Knowledge graph gaps or incomplete data areas

## Quality Guidelines

- Distinguish facts (retrieved from knowledge graph) vs assumptions
- Call out unknowns or ambiguous areas explicitly
- Use tables where appropriate
- Keep content clear, structured, and technical
- Optimize for onboarding engineers and architects
