# Tier: Medium Team (6-20 people)

## Agent Window Count
5-10 windows, organized by module or domain.

## File Organization
```
PROJECT-ROOT/
  PLAN.md                  # Top-level task breakdown
  BUG-BOARD.md             # Cross-module bugs
  MODULES/
    module-auth/PLAN.md    # Auth module tasks
    module-auth/BUG-BOARD.md
    module-api/PLAN.md     # API module tasks
    module-api/BUG-BOARD.md
    module-ui/PLAN.md      # UI module tasks
    module-ui/BUG-BOARD.md
  INTERFACES.md            # Shared API contracts
```

## Concurrency
Branch-locking model. Each module has a designated owner. Changes to
shared interfaces require review.

See `references/concurrency/branch.md` for details.

## Module Structure in PLAN.md
```markdown
## Module: Authentication (Owner: Alice)
- [ ] [auth] Implement JWT refresh flow
- [ ] [auth] Add rate limiting to login endpoint

## Module: Dashboard (Owner: Bob)
- [ ] [dashboard] Add chart component
- [ ] [dashboard] Connect to metrics API
```

## Coordination Rules
- Module owners approve changes within their module
- Cross-module changes require human coordinator approval
- Interface contracts are versioned in INTERFACES.md
- Weekly status: agents read MODULES/*/PLAN.md and produce summary

## Operational Loop
1. Planner breaks features into module-scoped tasks in PLAN.md
2. Module owner assigns within their section
3. Agents work in parallel, each within their module scope
4. Cross-module integration tested by coordinator
5. Bugs tagged with module name for routing

## Module Ownership Format
```markdown
| Module | Owner | Agent Window | Files |
|--------|-------|--------------|-------|
| auth | Alice | window-1 | src/auth/** |
| api | Bob | window-2 | src/api/** |
| ui | Carol | window-3 | src/ui/** |
```
