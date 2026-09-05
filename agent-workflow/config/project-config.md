# 项目配置

## 基本信息
- 项目名称：
- 项目路径：
- 版本控制：Git / 其他 / 无

## 技术栈
- 编程语言：
- 框架/库：
- 包管理器：
- 运行环境：

## 文件范围

### 前端 Agent
- 可修改文件模式：
  - （示例：*.html, *.css, *.js, *.jsx, *.tsx, *.vue）
- 不可修改文件：
  - （示例：*.py, *.java, *.go, *.cs）
- 测试命令：
  - （示例：npm test, jest, vitest）
- 构建命令：
  - （示例：npm run build, yarn build）

### 后端 Agent
- 可修改文件模式：
  - （示例：*.py, *.java, *.go, *.cs, *.sql）
- 不可修改文件：
  - （示例：*.html, *.css, *.js, *.jsx）
- 测试命令：
  - （示例：pytest, mvn test, go test, dotnet test）
- 构建命令：
  - （示例：python -m build, mvn package, go build）

### 全栈 Agent（可选）
- 可修改文件模式：
  - （示例：所有文件，或特定共享文件）
- 测试命令：
- 构建命令：

## 项目检测
- 配置文件（用于识别项目类型）：
  - （示例：package.json, requirements.txt, go.mod, pom.xml, *.csproj）
- 入口文件：
  - （示例：main.py, index.js, main.go, Program.cs）

## 常用命令
- 安装依赖：
  - （示例：npm install, pip install -r requirements.txt）
- 运行测试：
  - （示例：npm test, pytest, go test ./...）
- 代码检查：
  - （示例：eslint, flake8, golint）
- 构建项目：
  - （示例：npm run build, python -m build）

## 需保护的文件
- （Agent 不应随意修改的文件，如：）
  - 生产环境配置文件
  - 数据库迁移文件
  - CI/CD 配置
  - 密钥/凭证文件

## 团队角色
- 前端开发：
- 后端开发：
- 全栈开发：
- 测试：
- 运维：
