# AI Agent Driven Development

This project uses a structured workflow for AI agent-driven development with evidence-based decisions, explicit task boundaries, and traceable execution.

## Core Principles

- **Evidence-first**: All decisions must be backed by concrete evidence in code or documentation
- **No assumptions**: Ambiguity must be surfaced and resolved before proceeding
- **Strict boundaries**: Tasks define explicit scope — nothing outside scope is permitted
- **Documentation sync**: Code changes require corresponding documentation updates

## Project Structure

```
docs/
  guidelines/     # Development guidelines and rules
  roadmaps/       # High-level roadmap definitions
  plans/          # Execution plans for scopes of work
  phases/         # Phase-specific task definitions
  decisions/      # Architectural and design decisions
src/              # Source code
```

## Commands

### /roadmap
Creates or updates a roadmap in `docs/roadmaps/`.

**Usage:** `/roadmap [context describing what the roadmap covers]`

**Steps:**
1. Read `.claude/commands/roadmap.md` for full instructions
2. Invoke context-gathering skill
3. Produce roadmap using roadmap-definition skill
4. Engage user for refinement before finalizing

### /plan
Defines an execution plan and exports to `docs/plans/`.

**Usage:** `/plan [detailed context]`

**Steps:**
1. Read `.claude/commands/plan.md` for full instructions
2. Invoke context-gathering skill
3. Surface ambiguities and wait for resolution
4. Create plan document

### /definetask
Defines task(s) within a phase in `docs/phases/`.

**Usage:** `/definetask [phase reference] [task context]`

**Steps:**
1. Read `.claude/commands/definetask.md` for full instructions
2. Invoke roadmap-context skill
3. Invoke dependency-check skill
4. Create task file(s) using task-definition skill

### /executetask
Executes a task strictly following its task file.

**Usage:** `/executetask [task name]`

**Steps:**
1. Read `.claude/commands/executetask.md` for full instructions
2. Verify dependencies are satisfied
3. Get user confirmation on file changes
4. Create branch and execute

### /committask
Marks task as executed, commits changes, returns to parent branch.

**Usage:** `/committask`

**Steps:**
1. Read `.claude/commands/committask.md` for full instructions
2. Run documentation-sync skill
3. Update task status and commit

## Skills

Skills are located in `.claude/skills/`. Read the skill file before performing the associated operation.

| Skill | Path | Purpose |
|-------|------|---------|
| context-gathering | `.claude/skills/context-gathering/` | Systematically read relevant files |
| roadmap-definition | `.claude/skills/roadmap-definition/` | Define/update roadmap files |
| roadmap-context | `.claude/skills/roadmap-context/` | Gather roadmap context |
| task-definition | `.claude/skills/task-definition/` | Create task files |
| dependency-check | `.claude/skills/dependency-check/` | Validate task dependencies |
| documentation-sync | `.claude/skills/documentation-sync/` | Sync docs with code changes |

## Guidelines

Before making any changes, read `docs/guidelines/general-guidelines.md`.

## Rules

1. NEVER make decisions based on assumptions
2. NEVER proceed with ambiguous requirements
3. NEVER modify files outside task scope
4. ALWAYS read relevant documentation before coding
5. ALWAYS surface ambiguities before proceeding
6. ALWAYS verify dependencies before task execution
