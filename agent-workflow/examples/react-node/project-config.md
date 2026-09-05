# 项目配置 - React + Node.js 示例

## 基本信息
- 项目名称：React Node.js 全栈应用
- 项目路径：/path/to/your/project
- 版本控制：Git

## 技术栈
- 编程语言：JavaScript/TypeScript
- 框架/库：React (前端), Express (后端)
- 包管理器：npm
- 运行环境：Node.js 18+

## 文件范围

### 前端 Agent
- 可修改文件模式：
  - src/**/*.jsx
  - src/**/*.tsx
  - src/**/*.css
  - src/**/*.scss
  - public/**
- 不可修改文件：
  - server/**/*.js
  - server/**/*.ts
  - *.json (配置文件)
- 测试命令：npm test -- --testPathPattern=src/
- 构建命令：npm run build

### 后端 Agent
- 可修改文件模式：
  - server/**/*.js
  - server/**/*.ts
  - migrations/**
  - seeds/**
- 不可修改文件：
  - src/**/*.jsx
  - src/**/*.tsx
  - src/**/*.css
- 测试命令：npm test -- --testPathPattern=server/
- 构建命令：npm run build:server

### 全栈 Agent（可选）
- 可修改文件模式：
  - src/shared/**
  - config/**
- 测试命令：npm test
- 构建命令：npm run build

## 项目检测
- 配置文件：package.json, tsconfig.json, .env
- 入口文件：src/index.jsx (前端), server/index.js (后端)

## 常用命令
- 安装依赖：npm install
- 运行测试：npm test
- 代码检查：npm run lint
- 构建项目：npm run build
- 开发模式：npm run dev

## 需保护的文件
- .env (环境变量)
- .env.production (生产配置)
- docker-compose.yml
- Dockerfile
- package-lock.json (不要随意更新)

## 团队角色
- 前端开发：负责 React 组件和页面
- 后端开发：负责 API 和数据库
- 全栈开发：负责共享代码和配置
