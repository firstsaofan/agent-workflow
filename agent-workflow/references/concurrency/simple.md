# Concurrency Level 1: Simple File-Marker Locking

For solo developers and small teams (1-5 people).

## How It Works
Each agent declares its file scope in its init prompt. The scope is
a list of file patterns the agent is allowed to modify (from
project-config.md).

## Rules
1. Agent A only touches files matching its declared patterns
2. Agent B only touches files matching its declared patterns
3. If Agent A discovers a bug in Agent B's scope, it writes the bug
   to BUG-BOARD.md with Agent B's role tag -- it does NOT fix it
4. Only one agent works on a given file at a time (enforced by
   human coordination, not automation)

## Conflict Prevention
- Human dispatches tasks to the right window
- Agent init prompts include explicit file-scope constraints
- "Do not modify files outside your scope" is a hard rule

## Conflict Resolution
If two agents accidentally modify the same file:
1. Human notices during verification
2. One agent's changes are reverted (usually the later one)
3. The task is reassigned to the correct agent
4. Root cause: unclear scope in init prompt -- fix the prompt

## When to Upgrade
Upgrade to Level 2 (branch-locking) when:
- More than 5 agents are working simultaneously
- Files are frequently touched by multiple agents
- You need a traceable audit of who changed what

## Example Agent Prompt
```
Your file scope (ONLY modify these):
- Frontend: [patterns from project-config.md]
- Backend: [patterns from project-config.md]

Rule: If you need to modify a file outside your scope, write the
task to BUG-BOARD.md with the appropriate role tag instead.
```
