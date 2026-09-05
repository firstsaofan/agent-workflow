# Agent Workflow

**多 Agent 协作开发工作流** - 适用于任何技术栈、任何团队规模的 AI 辅助开发方法论。

## 核心理念

这不是一个框架或工具，而是一种**工作方式**。它定义了人类开发者和 AI Agent 如何协作完成软件开发任务。

### 设计哲学

1. **人做裁判，Agent 做执行** - 人类负责决策和验证，Agent 负责编码和修复
2. **文件即通信** - 通过 PLAN.md 和 BUG-BOARD.md 实现异步协作
3. **异步优先** - Agent 之间不互相等待，通过文件协作
4. **质量先于速度** - 每次修改必须验证，不信任 Agent 的自我评估

## 快速开始

### 1. 安装

将 `agent-workflow` 目录复制到你的项目：

```bash
# 方法 1：作为项目内 skill
cp -r agent-workflow .agents/skills/agent-workflow

# 方法 2：作为用户级 skill
cp -r agent-workflow ~/.agents/skills/agent-workflow
```

### 2. 配置

在项目根目录创建 `project-config.md`：

```markdown
# 项目配置

## 技术栈
- 编程语言：JavaScript/TypeScript
- 框架/库：React + Node.js
- 包管理器：npm

## 文件范围

### 前端 Agent
- 可修改文件模式：src/**/*.jsx, src/**/*.tsx, src/**/*.css
- 不可修改文件：server/**/*.js
- 测试命令：npm test -- --testPathPattern=src/
- 构建命令：npm run build

### 后端 Agent
- 可修改文件模式：server/**/*.js, server/**/*.ts
- 不可修改文件：src/**/*.jsx, src/**/*.tsx
- 测试命令：npm test -- --testPathPattern=server/
- 构建命令：npm run build:server
```

或者让 AI 帮你生成配置（见 `config/setup-prompt.md`）。

### 3. 初始化

告诉你的 AI Agent：

```
Set up agent workflow for my project at [PROJECT_PATH]
```

AI 会：
1. 读取你的项目配置
2. 创建 PLAN.md 和 BUG-BOARD.md
3. 输出 Agent 窗口初始化 prompt
4. 提供操作指南

### 4. 开始使用

1. 打开多个 Agent 窗口（每个角色一个）
2. 在 PLAN.md 中添加任务
3. 分配任务给对应 Agent
4. Agent 完成后验证
5. 发现 bug 写入 BUG-BOARD.md

## 支持的团队规模

| 规模 | 并发方案 | 文件组织 |
|------|----------|----------|
| 个人开发者 | 文件标记 | 简单三列看板 |
| 小团队 (2-5人) | 文件标记 + 角色 | 角色标签任务 |
| 中型团队 (6-20人) | Git 分支隔离 | 模块分区 |
| 企业级 (20+人) | 所有权注册表 | 团队目录 |

## 目录结构

```
agent-workflow/
├── SKILL.md                    # 核心入口
├── README.md                   # 本文档
├── config/
│   ├── project-config.md       # 项目配置模板
│   └── setup-prompt.md         # AI 辅助配置 Prompt
├── references/
│   ├── tiers/                  # 团队层级配置
│   ├── concurrency/            # 并发方案
│   ├── scenarios/              # 项目阶段
│   └── prompts/                # Prompt 库
└── templates/                  # 可复制模板
    ├── PLAN.md
    ├── BUG-BOARD.md
    └── .editorconfig
```

## 工作流示例

### 场景：测试修复

```
你: 发现登录按钮无响应
你: 写入 BUG-BOARD.md → ## 【前端】登录按钮点击无响应
你: 切到前端 Agent 窗口 → "看 BUG-BOARD.md，修前端的那条"
Agent: 读取文件 → 修复代码 → 更新状态到 DONE
你: 验证修复 → 通过则清除条目
```

### 场景：并行开发

```
你: 更新 PLAN.md → - [ ] [前端] 实现用户页面
你: 更新 PLAN.md → - [ ] [后端] 实现用户 API
你: 切到前端 Agent → "读 PLAN.md，开发用户页面"
你: 切到后端 Agent → "读 PLAN.md，开发用户 API"
两个 Agent 并行工作
你: 分别验证
```

## 跨工具兼容

本 skill 兼容所有支持 `.agents/skills/` 发现机制的工具：
- ZCode
- Cursor
- DeepSeek
- GitHub Copilot
- 其他支持该约定的工具

## 许可证

MIT License

## 贡献

欢迎贡献新的技术栈预设、场景模板或改进建议！
