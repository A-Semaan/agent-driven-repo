# /plan Command

Defines an execution plan for a given scope of work and exports to `docs/plans/`.

## Trigger

User message starts with `/plan` followed by detailed context.

## Execution Steps

1. **Invoke `context-gathering` skill**
   - Read `.claude/skills/context-gathering/SKILL.md`
   - Gather all relevant documentation
   - Gather all relevant code context

2. **Analyze the prompt**
   - Identify the scope of work
   - List all ambiguities or missing information

3. **Resolve ambiguities**
   - If ambiguities exist, surface them to user
   - Wait for clarification
   - Do NOT make assumptions
   - Do NOT proceed until all ambiguities are resolved

4. **Define the plan**
   - Create structured plan document
   - Include: scope, steps, dependencies, deliverables
   - Export to `docs/plans/`

## Plan Structure

```markdown
# Plan: [Name]

**Date:** yyyy-MM-dd HH:mm
**Scope:** [brief scope description]

## Context
[What was gathered and understood]

## Steps
1. [Step with details]
2. [Step with details]

## Dependencies
- [List dependencies]

## Deliverables
- [List deliverables]

## Risks/Concerns
- [Any identified risks]
```

## Rules

- NEVER proceed with ambiguous requirements
- NEVER make assumptions — ask explicitly
- ALWAYS document what is out of scope
- ALWAYS wait for ambiguity resolution before creating plan
