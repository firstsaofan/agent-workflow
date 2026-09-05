# Tier: Small Team (2-5 people)

## Agent Window Count
2-4 windows: one per role (frontend, backend, fullstack, or by module).

## File Organization
- PLAN.md with role tags: `- [ ] [frontend] Task` / `- [ ] [backend] Task`
- BUG-BOARD.md with 3 columns + assignee tag: 【前端】/【后端】/【全栈】
- Shared interface contracts section in PLAN.md is critical

## Concurrency
Simple file-marker locking with role tags. Each agent only modifies
files in its declared scope (from project-config.md).

See `references/concurrency/simple.md` for details.

## Key Rules
- Agents never modify another agent's declared file scope
- Cross-role issues go to BUG-BOARD.md with the other role's tag
- Interface contract changes require human approval before agents adapt
- One person acts as "coordinator" who reads both PLAN.md and
  BUG-BOARD.md and dispatches to the right window

## Operational Loop
1. Coordinator updates PLAN.md with role-tagged tasks
2. Frontend agent: "Read PLAN.md, work on [frontend task]"
3. Backend agent: "Read PLAN.md, work on [backend task]"
4. Both agents work in parallel through files
5. Coordinator verifies each completion
6. Bugs discovered during verification go to BUG-BOARD.md

## Coordination Tips
- Use role tags consistently: [frontend], [backend], [fullstack]
- When a task spans roles, split it into sub-tasks
- Keep interface contracts up to date in PLAN.md
- Daily sync: "Read PLAN.md and BUG-BOARD.md, give me a status summary"
