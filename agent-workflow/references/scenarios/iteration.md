# Scenario C: Iterative Development

## Condition
- Project already exists
- Adding new features or improvements
- Familiar with the codebase

## Workflow

### 1. Update PLAN.md
Add new tasks for the iteration:
```markdown
## 当前迭代目标
<!-- 本次迭代要完成什么 -->

## 任务列表
- [ ] 任务 1：
- [ ] 任务 2：
```

### 2. Assign Tasks
- Frontend agent: "Read PLAN.md, work on [frontend task]"
- Backend agent: "Read PLAN.md, work on [backend task]"

### 3. Development Cycle
1. Agent reads task from PLAN.md
2. Agent implements the feature
3. Agent updates PLAN.md status
4. Human verifies
5. If bug found, use BUG-BOARD.md workflow

### 4. Integration
1. Regular merges to main branch
2. Integration testing
3. Interface contract updates

## BUG-BOARD.md Integration
```
When a bug is found during iteration:
1. Write to BUG-BOARD.md with role tag
2. Agent fixes the bug
3. Return to iteration tasks
```

## Key Patterns
- Clear iteration goals
- Small, focused tasks
- Regular integration
- Test as you go
