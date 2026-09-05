# Code Review Prompts

## Standard Code Review
```
Please review the recent code changes. Focus on:
1. Correctness - Does the code do what it claims?
2. Edge cases - Are boundary conditions handled?
3. Error handling - Are errors handled gracefully?
4. Security - Any obvious security concerns?
5. Performance - Any obvious performance issues?
6. Readability - Is the code clear and maintainable?
7. Test coverage - Are the changes adequately tested?

Provide specific, actionable feedback.
```

## Security Review
```
Review the recent changes from a security perspective:
1. Input validation - Is user input sanitized?
2. Authentication - Are auth checks in place?
3. Authorization - Are permission checks correct?
4. Data exposure - Any sensitive data leaked?
5. Injection risks - SQL, XSS, command injection?
6. Dependencies - Any known vulnerable packages?

Report findings with severity levels: CRITICAL / HIGH / MEDIUM / LOW.
```

## Performance Review
```
Review the recent changes for performance concerns:
1. Algorithm complexity - Any O(n^2) or worse?
2. Database queries - N+1 queries? Missing indexes?
3. Memory usage - Any memory leaks or excessive allocation?
4. Caching - Appropriate use of caching?
5. Async operations - Proper async/await usage?

Report findings with impact assessment.
```

## Minimal Change Review (Hotfix)
```
Review this hotfix change:
1. Is the change minimal and focused on the issue?
2. Does it fix the root cause, not just symptoms?
3. Could it break anything else?
4. Is it safe to deploy immediately?

Keep the review brief - this is an emergency fix.
```

## Cross-Agent Review
```
Review changes from [AGENT_NAME] in [MODULE_NAME]:
1. Do changes align with the task in PLAN.md?
2. Are interface contracts maintained?
3. Could changes affect other modules?
4. Are tests adequate?

This is a cross-module review - focus on integration concerns.
```
