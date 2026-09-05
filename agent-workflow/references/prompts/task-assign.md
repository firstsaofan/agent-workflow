# Task Assignment Prompts

## Assign a Single Bug Fix
```
Read BUG-BOARD.md's TODO list. Fix the entry tagged [ROLE].
When done, move it to DONE. If the root cause is in another
scope, write a new entry in TODO with the other role's tag.
```

## Assign a Single Feature
```
Read PLAN.md. Work on [TASK NAME]. Update the task status
when complete.
```

## Batch Assign Multiple Bugs
```
Read BUG-BOARD.md's TODO list. Fix ALL entries tagged [ROLE].
Update each to DONE as you complete them. After each fix, run
[TEST COMMAND] to verify no regressions.
```

## Assign with Specific File
```
Fix the bug in BUG-BOARD.md titled [BUG TITLE]. The relevant
file is [FILE PATH]. After fixing, run [TEST COMMAND].
```

## Cross-Module Handoff
```
The [SOURCE_MODULE] has changed its interface. The new contract:
[CONTRACT DETAILS]
Please update [TARGET_MODULE] to use the new interface.
```

## Parallel Task Assignment
```
Read PLAN.md. There are multiple tasks available:
1. [TASK_1] - tagged [ROLE_1]
2. [TASK_2] - tagged [ROLE_2]
3. [TASK_3] - tagged [ROLE_1]

Work on the tasks tagged [YOUR_ROLE]. Update each status
when complete. Do not touch tasks tagged for other roles.
```

## Urgent Hotfix
```
URGENT: There is a production issue.
Read BUG-BOARD.md, find the entry tagged [URGENT].
Fix it with minimal changes. Do not refactor or improve
anything else. Run [TEST COMMAND] to verify.
```
