# Scenario A: New Project Full Lifecycle

## Condition
- Project is new (from scratch)
- Not yet deployed to production

## Workflow Phases

### Phase 1: Planning
1. Human defines requirements
2. Create PLAN.md with requirements list
3. Break down into modules
4. Define interface contracts
5. Assign modules to agents

### Phase 2: Development
1. Agents work on assigned modules in parallel
2. Update PLAN.md status as tasks complete
3. Interface changes require human approval
4. Regular integration checks

### Phase 3: Testing
1. Switch to BUG-BOARD.md driven workflow
2. Human tests, finds bugs
3. Agents fix bugs by role
4. Regression testing after each fix

### Phase 4: Launch
1. Final review and approval
2. Deploy to production
3. Monitor for issues
4. Hotfix workflow if needed

## PLAN.md Template
```markdown
# 项目计划

## 当前阶段
规划期

## 需求列表
- [ ] 需求 1：
- [ ] 需求 2：

## 模块拆分
<!-- 按模块组织，每个模块分配给一个 Agent -->

## 接口契约
<!-- 前后端约定的 API 格式 -->
```

## Key Patterns
- Start with clear requirements before coding
- Define interfaces early to enable parallel work
- Regular integration to catch issues early
- Test thoroughly before launch
