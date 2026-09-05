# Tier: Individual / Solo Developer

## Agent Window Count
1-2 windows maximum. You are the human judge; the agent is your
executor. No coordination overhead needed.

## File Organization
- Single PLAN.md with linear task list (no module splitting needed)
- Single BUG-BOARD.md with 3 columns (TODO / IN PROGRESS / DONE)
- No assignee columns needed -- you assign by switching windows

## Concurrency
No special concurrency handling needed. You control which window
works on what. If using git, standard commit practices suffice.

See `references/concurrency/simple.md` if you want basic file markers.

## Agent Prompt Structure
One generic agent prompt. All role-specific constraints come from
the project-config.md file scopes.

## Operational Loop
1. You write task to PLAN.md
2. Tell agent: "Read PLAN.md, work on [task name]"
3. Agent completes, updates PLAN.md status
4. You verify
5. Bug found -> write to BUG-BOARD.md, tell agent to fix

## Time-Saving Patterns
- Batch similar tasks: "Fix all TODO items in BUG-BOARD.md marked [backend]"
- Use agent for exploration: "Read the project and tell me how [X] works"
- Let agent write tests: "Write tests for [module]"

## What to Skip
- No module assignment columns
- No ownership registries
- No branch locking (unless desired)
- No status report generation (just read the files yourself)
