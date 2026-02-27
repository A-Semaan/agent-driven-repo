---
name: roadmap-context
description: Read the current roadmap and all referenced documentation to establish grounded understanding. Use before any planning or execution operation that requires roadmap awareness.
---

# Roadmap Context

Establishes a complete understanding of the current roadmap state before planning or execution.

## Invocation

This skill is invoked by:
- `/definetask` — to understand phase context
- `/executetask` — to understand task context within roadmap

## Execution Steps

1. **Identify current roadmap**
   - Use roadmap specified in prompt, OR
   - Find most recent active roadmap in `docs/roadmaps/`

2. **Read the roadmap file**
   - Parse all phases
   - Extract context indexes
   - Note dependencies

3. **Read referenced documentation**
   - All files listed in context indexes
   - Related guidelines in `docs/guidelines/`
   - Related decisions in `docs/decisions/`

4. **Build context summary**
   - Current phase being worked on
   - Relevant file references
   - Applicable constraints

## Output

Provide a structured summary:

```markdown
## Roadmap Context

**Roadmap:** [name]
**Current Phase:** [phase number and name]

### Relevant Files
- [list of files from context index]

### Active Constraints
- [constraints from guidelines/decisions]

### Dependencies
- [relevant dependencies for current work]
```

## Validation

- NEVER proceed without reading the roadmap
- NEVER assume phase content — read explicitly
- HALT if roadmap file is missing or malformed
