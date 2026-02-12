---
agent: agent
---
# Prompt: Analyze Codebase for Gaps and Improvements

## Role

You are a Technical Analyst examining a codebase to identify gaps between documentation and implementation, and to recommend improvements in both approach (design/architecture) and implementation (code quality).

## Technical Standards Reference

When evaluating code quality and suggesting improvements, reference the established standards in `.github/instructions/`:
- **dotnet-core.instructions.md**: .NET development standards, project structure, coding conventions
- **neo4j-cypher.instructions.md**: Neo4j integration, Cypher query patterns, graph modeling
- **redis-caching.instructions.md**: Redis caching patterns, cache service implementation
- **rabbitmq.instructions.md**: Message queue patterns, publisher/consumer implementation
- **background-services.instructions.md**: Worker services, hosted services, background processing
- **mcp-protocol.instructions.md**: MCP server and tool implementation standards
- **roslyn-code-analysis.instructions.md**: Code parsing and analysis with Roslyn
- **observability.instructions.md**: Logging, metrics, health checks, distributed tracing
- **testing-dotnet.instructions.md**: Unit testing, integration testing, test patterns
- **docker-containerization.instructions.md**: Dockerfile and docker-compose patterns
- **diagram.instructions.md**: Diagram creation standards and organization
- **documentation.instructions.md**: Documentation structure and cross-referencing

## Objective

Analyze the codebase to:

**Part 1 - Gap Analysis:**
- Features documented but not implemented
- Features implemented but not documented
- Inconsistencies between documented behavior and actual behavior
- Missing documentation for public APIs or interfaces
- Stale or outdated documentation

**Part 2 - Improvement Analysis:**
- Architectural and design patterns that could be improved (compare to patterns in instruction files)
- Code quality issues and refactoring opportunities (evaluate against coding standards)
- Developer experience friction points
- Quick wins vs long-term investments

## Analysis Process

### Step 1: Discover Documentation

Locate all documentation sources:
- README files (README.md, README.rst, etc.)
- Documentation directories (docs/, documentation/, wiki/)
- API documentation (OpenAPI specs, JSDoc, docstrings, XML comments)
- Architecture documents (ARCHITECTURE.md, design docs)
- Configuration documentation
- Inline code comments describing behavior

### Step 2: Discover Implementation

Examine the actual codebase:
- Entry points (main files, index files, app entry)
- Public APIs and interfaces
- Exported functions, classes, and modules
- Configuration files and environment variables
- Database schemas and migrations
- Build and deployment configurations

### Step 3: Gap Analysis

Compare documentation against implementation:

**1. Feature Gaps:**
- Documented features with no corresponding implementation
- Implemented features with no documentation
- Partially implemented documented features

**2. API Gaps:**
- Public functions/methods without documentation
- Documented API endpoints that don't exist
- Parameter mismatches between docs and code
- Return type discrepancies

**3. Configuration Gaps:**
- Environment variables used but not documented
- Documented configuration options not implemented
- Default values that differ from documentation

**4. Behavioral Gaps:**
- Documented behavior that differs from implementation
- Edge cases handled in code but not documented
- Error handling not matching documented error responses

### Step 4: Quality Assessment

Evaluate overall documentation health:
- Documentation coverage percentage
- Documentation freshness (last updated vs code changes)
- Documentation clarity and completeness

### Step 5: Improvement Analysis

After completing gap analysis, evaluate areas for improvement:

**1. Approach Improvements (Design & Architecture):**
- Architecture patterns that could be simplified or modernized
- Component boundaries that are unclear or poorly defined
- Coupling issues between modules or services
- Missing abstractions that would improve maintainability
- Over-engineering or unnecessary complexity
- Scalability concerns in the current design
- Security architecture gaps
- Error handling strategy improvements
- Data flow and state management patterns

**2. Implementation Improvements (Code Quality):**
- Code duplication that should be refactored
- Functions/methods that are too long or complex
- Inconsistent coding patterns across the codebase
- Missing or inadequate error handling
- Performance bottlenecks or inefficient algorithms
- Resource management issues (memory, connections, file handles)
- Test coverage gaps and testing strategy
- Dependency management (outdated, unused, or risky dependencies)
- Build and deployment pipeline improvements
- Logging and observability gaps

**3. Developer Experience Improvements:**
- Setup and onboarding friction
- Development workflow inefficiencies
- Missing tooling or automation opportunities
- CI/CD pipeline gaps
- Local development environment issues

## Output Format

```markdown
## Documentation-Implementation Gap Analysis

### Summary
| Category | Documented | Implemented | Gap Count |
|----------|------------|-------------|-----------|
| Features | X | Y | Z |
| APIs | X | Y | Z |
| Configuration | X | Y | Z |

### Critical Gaps (Must Address)

#### Implemented but Undocumented
1. **[Component/Feature]** - `path/to/file:line`
   - Description of what it does
   - Why documentation is needed

2. **[Component/Feature]** - `path/to/file:line`
   - Description of what it does
   - Why documentation is needed

#### Documented but Not Implemented
1. **[Feature from docs]** - `path/to/doc.md`
   - What the documentation claims
   - Evidence it's not implemented

#### Documentation-Implementation Mismatches
1. **[Component]**
   - Documentation says: "..."
   - Implementation does: "..."
   - Location: `path/to/file:line`

### Warnings (Should Address)

1. **[Issue]** - Description and location
2. **[Issue]** - Description and location

### Recommendations

1. **High Priority:** Specific action with file path
2. **Medium Priority:** Specific action with file path
3. **Low Priority:** Specific action with file path

### Documentation Health Score

| Metric | Score | Notes |
|--------|-------|-------|
| Coverage | X% | Public APIs with docs / Total public APIs |
| Freshness | X% | Recently updated docs / Total docs |
| Completeness | X% | Fully documented items / Partially documented |
| **Overall** | X% | Weighted average |

---

## Improvement Analysis

### Approach Improvements

#### Architecture & Design
| Area | Current State | Suggested Improvement | Impact | Effort |
|------|---------------|----------------------|--------|--------|
| [Area] | Description of current approach | Recommended change | High/Med/Low | High/Med/Low |

#### Specific Recommendations
1. **[Architecture Issue]** - `path/to/file`
   - Current: How it works now
   - Problem: Why this is suboptimal
   - Suggested: Better approach
   - Rationale: Why this improvement matters

2. **[Design Pattern Issue]** - `path/to/file`
   - Current: How it works now
   - Problem: Why this is suboptimal
   - Suggested: Better approach
   - Rationale: Why this improvement matters

### Implementation Improvements

#### Code Quality
| Category | Issues Found | Severity | Files Affected |
|----------|--------------|----------|----------------|
| Duplication | X instances | Medium | file1, file2 |
| Complexity | X functions | High | file3, file4 |
| Error Handling | X gaps | High | file5 |

#### Specific Recommendations
1. **[Code Issue]** - `path/to/file:line`
   - Current: Code snippet or description
   - Problem: Why this needs improvement
   - Suggested: Better implementation
   - Example: Code snippet if helpful

2. **[Performance Issue]** - `path/to/file:line`
   - Current: Code snippet or description
   - Problem: Why this needs improvement
   - Suggested: Better implementation

### Developer Experience Improvements

1. **[DX Issue]** - Area affected
   - Problem: Current friction point
   - Suggested: Improvement
   - Benefit: What this enables

### Improvement Priority Matrix

| Priority | Improvement | Category | Rationale |
|----------|-------------|----------|-----------|
| 1 | [Improvement] | Approach/Implementation | Why this should be first |
| 2 | [Improvement] | Approach/Implementation | Why this should be second |
| 3 | [Improvement] | Approach/Implementation | Why this should be third |

### Quick Wins
Low-effort improvements that can be done immediately:
1. [Quick win with file path]
2. [Quick win with file path]
3. [Quick win with file path]

### Long-term Investments
High-impact improvements requiring significant effort:
1. [Investment with scope description]
2. [Investment with scope description]
```

## Analysis Triggers

- "analyze" - Full analysis (gaps + improvements)
- "check docs" - Documentation coverage check
- "find undocumented" - Find implemented features without docs
- "find unimplemented" - Find documented features without implementation
- "gaps only" - Documentation-implementation gap analysis only
- "improvements" - Approach and implementation improvements only
- "architecture review" - Focus on design and architectural improvements
- "code quality" - Focus on implementation quality improvements
- "audit" - Complete audit with all recommendations

## Quality Criteria

- Reference specific files and line numbers
- Provide evidence for each gap or issue identified
- Prioritize by impact (Critical > Warning > Info)
- Suggest specific fixes, not just problems
- Consider the codebase's conventions when making recommendations
- Be actionable and specific
- For improvements, assess both impact and effort required
- Distinguish between quick wins and long-term investments
- Consider trade-offs when suggesting architectural changes
- Respect existing patterns unless there's clear benefit to changing them
