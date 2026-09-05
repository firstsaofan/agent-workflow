# 项目配置 - .NET 示例

## 基本信息
- 项目名称：.NET Web 应用
- 项目路径：/path/to/your/project
- 版本控制：Git

## 技术栈
- 编程语言：C#
- 框架/库：ASP.NET Core / Blazor
- 包管理器：NuGet
- 运行环境：.NET 8+

## 文件范围

### 前端 Agent
- 可修改文件模式：
  - *.cshtml
  - *.razor
  - *.js
  - *.css
  - *.scss
  - wwwroot/**
- 不可修改文件：
  - *.cs
  - *.csproj
  - appsettings*.json
- 测试命令：dotnet test --filter "Category=Frontend"
- 构建命令：dotnet build

### 后端 Agent
- 可修改文件模式：
  - *.cs
  - *.csproj
  - *.sln
  - appsettings*.json
  - *.sql
  - Migrations/**
- 不可修改文件：
  - *.cshtml
  - *.razor
  - *.js
  - *.css
- 测试命令：dotnet test
- 构建命令：dotnet build

## 项目检测
- 配置文件：*.sln, *.csproj, appsettings.json, Program.cs
- 入口文件：Program.cs, Startup.cs

## 常用命令
- 安装依赖：dotnet restore
- 运行测试：dotnet test
- 代码检查：dotnet format --verify-no-changes
- 构建项目：dotnet build
- 运行应用：dotnet run

## 需保护的文件
- *.sln (解决方案结构)
- appsettings.Production.json
- *.db (SQLite 数据库)
- Migrations/ (EF Core 迁移，需要明确指令)
- *.user (用户配置)
- bin/, obj/ (编译输出)

## 团队角色
- 前端开发：负责 Razor 组件和页面
- 后端开发：负责 Controller、Service、Model
- 全栈开发：负责集成和配置
