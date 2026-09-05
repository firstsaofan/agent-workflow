# Scenario E: Production Hotfix

## Condition
- Project is live in production
- Urgent issue needs immediate fix
- Minimal changes, fast verification

## Workflow

### 1. Assess Severity
- **Critical**: Service down, data loss, security breach
- **High**: Major feature broken, no workaround
- **Medium**: Feature broken, workaround exists
- **Low**: Minor issue, cosmetic

### 2. Minimal Fix Only
```
URGENT: Production issue.
Fix ONLY the specific problem.
Do NOT refactor, optimize, or improve anything else.
Make the smallest possible change.
```

### 3. Fast Verification
1. Fix the issue
2. Run critical tests only (not full suite)
3. Manual verification of the specific issue
4. Deploy immediately

### 4. Post-Fix
1. Document the fix in BUG-BOARD.md
2. Schedule proper fix for later (if hotfix was incomplete)
3. Add test to prevent regression
4. Root cause analysis

## Hotfix Prompt
```
URGENT PRODUCTION ISSUE:
[Description of the problem]

Requirements:
1. Fix ONLY this specific issue
2. Minimal changes - no refactoring
3. Preserve all existing behavior
4. Run critical tests to verify
5. Document what was changed and why
```

## Key Patterns
- Speed is critical
- Minimal changes reduce risk
- Fast verification, not comprehensive testing
- Document everything for post-mortem
- Schedule proper fix later
