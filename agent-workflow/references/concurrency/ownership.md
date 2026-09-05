# Concurrency Level 3: Distributed Ownership Registry

For enterprise teams (20+ people) with cross-team dependencies.

## How It Works
A centralized ownership registry maps every file pattern to an
owning team. All cross-team file modifications follow a formal
transfer-of-ownership protocol.

## Ownership Registry
Maintained in INTERFACES/ownership.md:
```markdown
| Pattern | Owner Team | Approver | Contact |
|---|---|---|---|
| src/auth/** | auth-team | Alice | @alice |
| src/api/** | api-team | Bob | @bob |
| src/shared/** | platform-team | Carol | @carol |
| *.sql | dba-team | Dave | @dave |
| docker/** | infra-team | Eve | @eve |
```

## Transfer Protocol
When Team A needs to modify a file owned by Team B:
1. Team A writes a "modification request" to BUG-BOARD.md with
   tag [TRANSFER] specifying the file and reason
2. Team B's approver reviews within 24h (SLA tracked)
3. If approved: Team B either makes the change, or transfers
   ownership temporarily by updating ownership.md
4. If rejected: Team A must find an alternative approach

## File Structure
```
PROJECT-ROOT/
  PLAN.md                          # Epic-level plan
  BUG-BOARD.md                     # Cross-team bugs + transfer requests
  INTERFACES/
    contracts.md                   # API contracts (versioned)
    ownership.md                   # File ownership registry
    transfer-log.md                # Audit trail of ownership transfers
  TEAM-PLANS/
    [team-name]/PLAN.md            # Team-specific plans
    [team-name]/BUG-BOARD.md       # Team-specific bugs
  STATUS/
    [team-name]/STATUS.md          # Team status
```

## Status Reporting
Weekly: coordinator reads all TEAM-PLANS and STATUS files to
produce a consolidated report.

Agent prompt:
"Read all files under TEAM-PLANS/ and STATUS/, produce a
consolidated status report with: completed this week,
planned next week, blockers, cross-team dependencies."

## Audit Trail
Every ownership transfer is logged in INTERFACES/transfer-log.md:
```markdown
| Date | From | To | File Pattern | Reason | Approved By |
|---|---|---|---|---|---|
| 2026-09-01 | api-team | auth-team | src/auth/middleware.* | JWT refactor | Alice |
```
