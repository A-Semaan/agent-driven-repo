# /roadmap Command

Creates or updates a roadmap in `docs/roadmaps/`.

## Trigger

User message starts with `/roadmap` followed by context describing what the roadmap covers.

## Execution Steps

1. **Invoke `context-gathering` skill**
   - Read `.claude/skills/context-gathering/SKILL.md`
   - Read relevant documentation based on the prompt
   - Read relevant code if specified

2. **Investigate the prompt**
   - Determine what needs to be covered
   - Identify scope and boundaries

3. **Read relevant code**
   - Examine existing implementations
   - Understand current state

4. **Invoke `roadmap-definition` skill**
   - Read `.claude/skills/roadmap-definition/SKILL.md`
   - Produce the roadmap in `docs/roadmaps/`
   - Follow naming convention: `<ordinal>-<name>.md`

5. **Engage with user**
   - Present the draft roadmap
   - Refine based on feedback
   - Do NOT finalize until user confirms

## Rules

- NEVER finalize a roadmap without user confirmation
- NEVER skip the context-gathering step
- ALWAYS surface ambiguities before proceeding
- ALWAYS include complete phase definitions with context indexes
