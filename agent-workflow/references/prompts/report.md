# Status Reporting Prompts

## Quick Status
```
Read PLAN.md and BUG-BOARD.md. Give me a concise status:
- Tasks completed: [count]
- Tasks in progress: [count]
- Tasks pending: [count]
- Bugs found: [count]
- Bugs fixed: [count]
- Blockers: [list or "none"]
```

## Detailed Status Report
```
Read all project files and produce a detailed status report:

## Summary
- Total tasks: X
- Completed: X (X%)
- In Progress: X
- Pending: X
- Blocked: X

## Completed This Week
- [task 1] - completed by [agent]
- [task 2] - completed by [agent]

## In Progress
- [task 1] - [agent] - [status]

## Planned for Next Week
- [task 1]
- [task 2]

## Blockers
- [blocker 1] - [impact]

## Risks
- [risk 1] - [mitigation]
```

## Module Status (Medium/Enterprise)
```
Read all files under MODULES/ or TEAM-PLANS/.
For each module, report:
- Module name
- Owner
- Tasks completed / total
- Current blockers
- Dependencies on other modules
```

## Weekly Summary
```
Generate a weekly summary:
1. Read all PLAN.md files
2. Read all BUG-BOARD.md files
3. Identify completed tasks
4. Identify new tasks added
5. Identify bugs found and fixed
6. List any cross-team dependencies
7. Suggest priorities for next week

Format as a readable report.
```

## Blocker Report
```
Scan all project files for blockers:
1. Tasks marked as blocked in PLAN.md
2. Bugs in TODO that have been there for > [TIME]
3. Cross-module dependencies waiting for resolution
4. Resource constraints

For each blocker, suggest potential solutions.
```
