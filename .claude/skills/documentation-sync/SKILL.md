# Documentation Sync

Reviews all files touched during a task and ensures documentation reflects the current state.

## Invocation

This skill is invoked by:
- `/committask` — before committing changes

## Execution Steps

1. **List all files modified** in the current task
2. **For each modified file:**
   - Identify documentation that references this file
   - Check if the documentation describes affected behavior
3. **Cross-reference against existing documentation:**
   - `docs/` folder structure
   - API documentation
   - README files
   - Inline documentation requirements
4. **Identify documentation gaps:**
   - Changed behavior not reflected in docs
   - New behavior without documentation
   - Outdated references
5. **Update or create documentation** as needed

## Documentation Types to Check

| Type | Location | Check For |
|------|----------|-----------|
| API docs | `docs/` | Endpoint changes, parameter changes |
| Guidelines | `docs/guidelines/` | Process or rule changes |
| README | root or module | Setup, usage changes |
| Decisions | `docs/decisions/` | Architectural changes |

## Actions

### Update Required

If documentation exists but is outdated:
- Update the specific sections affected
- Preserve existing structure
- Note the change date

### Stub Required

If new behavior has no documentation:
- Create a documentation stub
- Include: purpose, basic usage, location of implementation
- Mark as needing expansion if incomplete

## Output Format

```markdown
## Documentation Sync Report

### Updated
- [doc path] — [what was updated]

### Created
- [doc path] — [stub for what]

### Verified (no changes needed)
- [doc path] — [still accurate]

### Warnings
- [any documentation concerns]
```

## Validation

- NEVER commit without running documentation sync
- NEVER leave behavior undocumented
- ALWAYS create at least a stub for new behavior
