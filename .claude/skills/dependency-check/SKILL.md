# Dependency Check

Validates that all dependencies declared in a task or plan are satisfied before execution.

## Invocation

This skill is invoked by:
- `/definetask` — to validate dependency declarations
- `/executetask` — to verify execution prerequisites

## Execution Steps

1. **Read dependency declarations** from task file or plan
2. **For each dependency:**
   - Locate the task file in `docs/phases/`
   - Read the task file
   - Check the `Status` field
3. **Validate all dependencies** have `Status: executed`
4. **Report results**

## Validation Rules

Each dependency must satisfy ALL conditions:
- Task file exists in `docs/phases/`
- Task file is readable and well-formed
- Status field equals `executed`

## Failure Conditions

HALT and report if:
- Dependency task file does not exist
- Dependency task file is malformed
- Dependency status is `defined` (not yet executed)
- Dependency status is missing or invalid

## Output Format

### All Dependencies Satisfied

```markdown
## Dependency Check: PASSED

All dependencies are in executed status:
- [task-name] — executed
- [task-name] — executed
```

### Dependencies Not Satisfied

```markdown
## Dependency Check: FAILED

The following dependencies are not satisfied:

| Dependency | Issue |
|------------|-------|
| [task-name] | Status is 'defined' — must be executed first |
| [task-name] | Task file not found |

**Action required:** Execute or resolve the above dependencies before proceeding.
```

## Post-Check

- NEVER proceed with execution if any dependency fails
- ALWAYS surface the specific failure to the user
- PROVIDE clear guidance on what needs to be resolved
