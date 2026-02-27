---
name: context-gathering
description: Systematically read all files relevant to the current operation. Use when preparing for roadmap creation, planning, task definition, or task execution. Invoked by commands that require comprehensive context before proceeding.
---

# Context Gathering

Systematically reads all files relevant to the current operation before any planning or execution.

## Invocation

This skill is invoked automatically by commands that require context:
- `/roadmap` — gather documentation and code context
- `/plan` — gather documentation and code context
- `/definetask` — gather phase-specific context
- `/executetask` — gather task-specific context

## Execution Steps

1. **Identify context sources** from the invoking command or task file
2. **Read all referenced files** in priority order:
   - Task file (highest priority)
   - Documentation files
   - Code files (lowest priority)
3. **Validate all sources exist** — if any referenced file is missing or incomplete, halt and surface to user
4. **Report conflicts** — if sources conflict, report the conflict and ask for resolution

## Priority Order

When conflicts arise between sources, prioritize:

1. **Task file** — authoritative for current operation
2. **Documentation** — authoritative for requirements and contracts
3. **Code** — authoritative for current implementation state

## Validation Rules

- NEVER infer context not explicitly present in gathered sources
- NEVER proceed if a referenced file does not exist
- NEVER proceed if a referenced file is incomplete without user acknowledgment
- ALWAYS surface missing or ambiguous context before proceeding

## Output

After gathering, report:
- Files read successfully
- Any missing files
- Any conflicts detected
- Readiness to proceed (or blockers)
