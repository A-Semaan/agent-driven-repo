# Roadmap Definition

Defines or updates roadmap files in `docs/roadmaps/`.

## File Naming

Format: `<ordinal-number>-<hyphen-separated-roadmap-name>.md`

Examples:
- `01-user-authentication.md`
- `02-payment-integration.md`

## Archiving

When a roadmap is superseded:
1. Rename old file: append `-archived-<yyyy-MM-dd>` to filename
2. Create new file with next ordinal number

## Required Sections

### Header

```markdown
# Roadmap: [Name]

**Date defined:** yyyy-MM-dd HH:mm
**Status:** active | archived
```

### Summary

A medium-sized general summary covering:
- What this roadmap addresses
- High-level goals
- Key constraints or dependencies

### Phase Definitions

Each phase must contain extensive detail for `/definetask` to work without ambiguity:

```markdown
## Phase [N]: [Phase Name]

### Overview
[What this phase accomplishes]

### Context Index

**Files to touch:**
- path/to/file.ext — [reason]

**Files to create:**
- path/to/new-file.ext — [purpose]

**Documentation to create:**
- docs/path/file.md — [what it documents]

**Documentation to update:**
- docs/path/existing.md — [what changes]

**Tests to create:**
- tests/path/test_file.ext — [what it tests]

**Projects involved:**
- [project/module name] — [role in this phase]

### Dependencies
- [List any phase dependencies]

### Success Criteria
- [Measurable criteria for phase completion]
```

## Validation

Before finalizing, verify:
- [ ] All phases have complete context indexes
- [ ] File paths are explicit and correct
- [ ] No ambiguous references
- [ ] Dependencies between phases are explicit
