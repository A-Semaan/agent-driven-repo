---
name: task-definition
description: Define task files in docs/phases/ with full specification including status, context, execution plan, boundaries, and verifications. Use when defining new tasks within a phase.
---

# Task Definition

Defines task files in `docs/phases/phase[x]-<yyyy-MM-dd>/`.

## Directory Structure

```
docs/phases/
  phase1-2024-03-15/
    01-setup-database.md
    02-create-models.md
  phase2-2024-03-20/
    01-implement-api.md
```

## File Naming

Format: `<ordinal-task-number>-<hyphen-separated-task-name>.md`

## Required Template

```markdown
# Task: [Title]

## Metadata

| Field | Value |
|-------|-------|
| Status | defined |
| Date defined | yyyy-MM-dd HH:mm |
| GUID | [UUID4] |

## Summary

**Current state:** [What exists now]

**Required outcome:** [What needs to be done]

## Context

### Files to read
- [explicit file paths with purpose]

### Documentation to reference
- [explicit doc paths]

### Code to understand
- [explicit code paths]

## To Do

- [ ] [Specific actionable item]
- [ ] [Specific actionable item]
- [ ] [Specific actionable item]

## Execution Plan

### Step 1: [Name]
[Detailed instructions]
- Files affected: [list]
- Actions: [create/modify/delete]

### Step 2: [Name]
[Detailed instructions]

## Tests

### Unit tests to create
- [test file path] — [what it tests]

### Tests to update
- [test file path] — [what changes]

## Documentation

### To create
- [doc path] — [purpose]

### To update
- [doc path] — [what changes]

## Boundaries

**The agent MUST NOT:**
- [Explicit boundary]
- [Explicit boundary]

## Out of Scope

This task does NOT include:
- [Explicit exclusion]
- [Explicit exclusion]

## Verifications

### Build checks
- [ ] [specific check]

### Test runs
- [ ] [specific test command]

### Manual checks
- [ ] [specific verification]

## Dependencies

| Task | Status Required |
|------|-----------------|
| [task-name] | executed |
```

## Validation Before Finalizing

- [ ] All file paths are explicit and correct
- [ ] To-do list matches execution plan
- [ ] Boundaries are clear and complete
- [ ] Out of scope is explicitly stated
- [ ] All dependencies are listed
- [ ] GUID is a valid UUID4
