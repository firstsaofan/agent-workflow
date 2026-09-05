# Concurrency Level 2: Branch-Lock + Ownership Tags

For medium teams (6-20 people) with module-based organization.

## How It Works
Each module or domain has a designated owner. Changes to shared
resources (interfaces, configs, shared libraries) go through a
review step.

## Branch Strategy
```
main
  +-- feat/auth-jwt-refresh      (Alice's branch)
  +-- feat/dashboard-charts      (Bob's branch)
  +-- fix/api-rate-limit         (Carol's branch)
```

## Ownership Rules
1. Module files: only the module owner's agent modifies them
2. Shared files: require human approval before modification
3. Interface contracts: versioned, changes require all affected
   teams to acknowledge

## PLAN.md Organization
```markdown
## Module: Auth (Owner: Alice)
- [ ] [auth] Task description

## Module: Dashboard (Owner: Bob)
- [ ] [dashboard] Task description

## Shared (Requires approval)
- [ ] [shared] Modify auth middleware -- affects auth + api
```

## Branch Locking Protocol
1. Agent picks a task from its module section in PLAN.md
2. Agent creates a feature branch (if git is available)
3. Agent works within that branch
4. Agent marks task as IN REVIEW in PLAN.md
5. Human reviews and merges
6. If conflict: human resolves, updates PLAN.md

## When to Upgrade
Upgrade to Level 3 (distributed-locking) when:
- More than 20 agents/people
- Multiple sub-teams with overlapping file domains
- Need for automated ownership tracking

## Module Ownership Table
Maintain in PLAN.md or a separate OWNERS.md:
```markdown
| Module | Owner | Approver | Files |
|--------|-------|----------|-------|
| auth | Alice | Alice | src/auth/** |
| dashboard | Bob | Bob | src/dashboard/** |
| shared | Carol | Carol | src/shared/** |
```
