# Scenario D: Testing and Bug Fixing

## Condition
- Project already exists
- In testing phase
- Features mostly complete
- Focus on finding and fixing bugs

## Workflow

### 1. Testing Cycle
1. Human tests the application
2. Find a bug
3. Write to BUG-BOARD.md (TODO section)
4. Tag with role: 【前端】or【后端】
5. Agent fixes the bug
6. Agent updates status to DONE
7. Human verifies the fix
8. If pass: remove entry
9. If fail: add reason, send back

### 2. BUG-BOARD.md Format
```markdown
# Bug 看板

## 待修复 (TODO)
<!-- 格式：## [角色] 问题描述 -->
## 【前端】登录按钮点击无响应
## 【后端】API 返回 500 错误

## 修复中 (IN PROGRESS)

## 已修复待验证 (DONE)
```

### 3. Regression Testing
After each batch of fixes:
```
Run the full test suite to confirm no regressions.
List any new failures.
```

### 4. Verification Checklist
- [ ] Bug is actually fixed
- [ ] No new bugs introduced
- [ ] Related functionality still works
- [ ] Tests pass
- [ ] Code follows conventions

## Key Patterns
- BUG-BOARD.md is the primary file
- One bug at a time per agent
- Always verify fixes
- Track regression introduction
