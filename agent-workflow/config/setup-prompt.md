# AI 辅助配置生成 Prompt

将以下 Prompt 发送给你的 AI Agent，让它帮你生成项目配置文件。

---

## Prompt

```
请分析我的项目并生成 agent-workflow 配置文件。

项目路径：[你的项目路径]

请执行以下步骤：

1. **识别技术栈**
   - 扫描项目根目录的配置文件（package.json, requirements.txt, go.mod, pom.xml, *.csproj 等）
   - 识别主要编程语言和框架
   - 识别包管理器

2. **分析文件结构**
   - 识别前端文件类型和位置
   - 识别后端文件类型和位置
   - 识别共享/公共文件

3. **查找测试配置**
   - 查找测试配置文件（jest.config, pytest.ini, .testrc 等）
   - 确定测试命令
   - 确定测试文件的位置和命名模式

4. **查找构建配置**
   - 查找构建脚本（Makefile, build.gradle, webpack.config 等）
   - 确定构建命令
   - 确定输出目录

5. **识别保护文件**
   - 识别不应被 Agent 随意修改的文件
   - 包括：生产配置、数据库迁移、CI/CD 配置、密钥文件

6. **生成配置文件**
   - 按照以下模板格式输出
   - 对于不确定的项，用 [待确认] 标记
   - 给出你的判断依据

请输出完整的 project-config.md 文件内容。
```

---

## 使用示例

### 示例 1：React + Node.js 项目

**AI 检测结果：**
- 发现 package.json → Node.js 项目
- 依赖中有 react → 前端框架
- 依赖中有 express → 后端框架
- 有 jest.config.js → 测试框架

**生成的配置：**
```markdown
## 技术栈
- 编程语言：JavaScript/TypeScript
- 框架/库：React (前端), Express (后端)
- 包管理器：npm

## 文件范围

### 前端 Agent
- 可修改文件模式：src/**/*.jsx, src/**/*.tsx, src/**/*.css, public/**
- 不可修改文件：server/**/*.js, *.json (配置)
- 测试命令：npm test -- --testPathPattern=src/
- 构建命令：npm run build

### 后端 Agent
- 可修改文件模式：server/**/*.js, server/**/*.ts, migrations/**
- 不可修改文件：src/**/*.jsx, src/**/*.tsx
- 测试命令：npm test -- --testPathPattern=server/
- 构建命令：npm run build:server
```

### 示例 2：Python Django 项目

**AI 检测结果：**
- 发现 requirements.txt → Python 项目
- 有 manage.py → Django 项目
- 有 pytest.ini → pytest 测试

**生成的配置：**
```markdown
## 技术栈
- 编程语言：Python
- 框架/库：Django
- 包管理器：pip

## 文件范围

### 后端 Agent
- 可修改文件模式：**/*.py, **/*.html, **/*.css
- 不可修改文件：*.js (如果有前端分离), docker-compose.yml
- 测试命令：pytest
- 构建命令：python manage.py collectstatic

### 前端 Agent（如果有分离的前端）
- 可修改文件模式：static/**/*.js, static/**/*.css, templates/**/*.html
- 不可修改文件：**/*.py
- 测试命令：npm test
- 构建命令：npm run build
```

---

## 注意事项

1. **不要猜测**：对于不确定的配置，标记为 [待确认] 让用户确认
2. **给出依据**：解释你为什么认为某个配置是这样的
3. **覆盖全面**：确保所有文件类型都被正确分类
4. **保护文件**：宁可多保护，不要漏掉关键配置文件
5. **命令验证**：对于测试和构建命令，建议用户先手动执行确认
