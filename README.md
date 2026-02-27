# AI Agent Driven Development — Skeleton

A **reusable project skeleton** for AI agent-driven software development. Use this repo as the starting point for new projects that want evidence-based decisions, explicit task boundaries, and traceable execution with Cursor and Claude Code.

## What This Skeleton Provides

- **Folder structure** — `docs/` and `src/` layout for documentation and code
- **Guidelines** — General development rules in `docs/guidelines/`
- **Commands** — `/roadmap`, `/plan`, `/definetask`, `/executetask`, `/committask`
- **Skills** — Six skills (context-gathering, roadmap-definition, roadmap-context, task-definition, dependency-check, documentation-sync)
- **Agent config** — Cursor rules in `.cursor/` and Claude Code instructions in `CLAUDE.md` and `.claude/`

## Using This Skeleton for a New Project

1. **Copy or clone** this repo into your new project directory (or use it as a template).
2. **Customize** `docs/guidelines/general-guidelines.md` for your project’s rules.
3. **Add your code** under `src/`.
4. **Run `/roadmap`** with context for your project to create the first roadmap in `docs/roadmaps/`.
5. Use **`/plan`**, **`/definetask`**, and **`/executetask`** as needed; follow [docs/guidelines/general-guidelines.md](docs/guidelines/general-guidelines.md).

You can remove `ai-agent-driven-development-skeleton.md` after copying; it describes the skeleton itself and is not required at runtime.

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

## Core Principles

- **Evidence-first**: All decisions must be backed by concrete evidence in code or documentation
- **No assumptions**: Ambiguity must be surfaced and resolved before proceeding
- **Strict boundaries**: Tasks define explicit scope — nothing outside scope is permitted
- **Documentation sync**: Code changes require corresponding documentation updates

## Commands

| Command | Description |
|---------|-------------|
| `/roadmap` | Create or update a roadmap in `docs/roadmaps/` |
| `/plan` | Define an execution plan and export to `docs/plans/` |
| `/definetask` | Define task(s) within a phase in `docs/phases/` |
| `/executetask` | Execute a task strictly following its task file |
| `/committask` | Mark task as executed, commit changes, return to parent branch |

## Skills

| Skill | Purpose |
|-------|---------|
| `roadmap-definition` | Define or update roadmap files |
| `roadmap-context` | Gather context from current roadmap |
| `context-gathering` | Systematically read all relevant files |
| `task-definition` | Create task files with full specification |
| `dependency-check` | Validate task dependencies are executed |
| `documentation-sync` | Ensure documentation reflects code state |

## Guidelines

See [docs/guidelines/general-guidelines.md](docs/guidelines/general-guidelines.md) for development rules.
