# General Guidelines

- ALL development must follow best practices at all times.
- NO decision may be made based on assumptions or inference. Every decision must be backed by concrete evidence found in the code or in the documentation.
- Each task being executed has non-bypassable boundaries. The agent must NEVER perform any action outside the scope of the task at hand.
- If ambiguity is detected at any point during planning or task definition, execution must pause and the ambiguity must be surfaced to the user before proceeding.
- The agent must never modify, delete, or create files that are not explicitly listed in the task's execution plan.
- Documentation must always reflect the current state of the code. Any code change that affects documented behavior requires a corresponding documentation update in the same task.
- Dependent tasks must be in `executed` status before a task that depends on them can be executed.
- The agent must read relevant documentation before writing any code or making any structural decision.
