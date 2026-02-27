# /definetask Command

Defines one or more tasks within a phase in `docs/phases/`.

## Trigger

User message starts with `/definetask` with a phase reference and task context.

## Execution Steps

1. **Invoke `roadmap-context` skill**
   - Read `.claude/skills/roadmap-context/SKILL.md`
   - Read the current roadmap
   - Gather phase-specific context

2. **Invoke `context-gathering` skill**
   - Read `.claude/skills/context-gathering/SKILL.md`
   - Read additional relevant files
   - Read additional relevant documentation

3. **Invoke `dependency-check` skill**
   - Read `.claude/skills/dependency-check/SKILL.md`
   - Identify task dependencies
   - Validate dependency declarations

4. **Analyze scope**
   - Identify ambiguities or missing information
   - Surface ambiguities to user if any exist
   - Wait for clarification — do NOT proceed until resolved

5. **Define task(s)**
   - Read `.claude/skills/task-definition/SKILL.md`
   - Create task file(s) in `docs/phases/phase[x]-<date>/`
   - Follow naming: `<ordinal>-<task-name>.md`

## Phase Directory

Tasks go in: `docs/phases/phase[N]-<yyyy-MM-dd>/`

Create the phase directory if it doesn't exist.

## Rules

- NEVER define tasks without reading the roadmap first
- NEVER proceed with ambiguous requirements
- NEVER skip dependency validation
- ALWAYS include complete task specification per `task-definition` skill
- ALWAYS verify task boundaries are explicit
