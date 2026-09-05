# Verification and Testing Prompts

## Run All Tests
```
Run the full test suite using [TEST COMMAND from project-config.md].
Report: total tests, passed, failed, skipped.
If any fail, list the failed test names and error messages.
```

## Run Module Tests
```
Run tests for [MODULE_NAME] module only.
Use command: [MODULE-SPECIFIC TEST COMMAND]
Report results and any failures.
```

## Regression Check
```
The recent changes might have introduced regressions.
1. Run the full test suite: [TEST COMMAND]
2. Compare with previous results if available
3. List any NEW failures (not pre-existing)
4. For each new failure, suggest the likely cause
```

## Code Verification
```
Review the changes made by the agent:
1. Read the modified files
2. Check for obvious issues (syntax errors, missing imports, etc.)
3. Verify the changes match the task description in PLAN.md
4. Run [TEST COMMAND] to confirm
5. Report: PASS / FAIL with details
```

## Build Verification
```
Build the project using [BUILD COMMAND from project-config.md].
Report: success/failure, warnings, errors.
If failed, list the specific errors.
```

## Manual Verification Checklist
```
After agent completes a task, verify:
1. [ ] Code changes match the task description
2. [ ] No unrelated files were modified
3. [ ] Tests pass: [TEST COMMAND]
4. [ ] Build succeeds: [BUILD COMMAND]
5. [ ] No new warnings or errors
6. [ ] Code follows project style (if linter available)
```
