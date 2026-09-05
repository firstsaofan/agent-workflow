# 示例项目

本目录包含不同技术栈的配置示例。

## 目录结构

```
examples/
├── react-node/          # React + Node.js 全栈应用
│   └── project-config.md
├── python-django/       # Python Django Web 应用
│   └── project-config.md
└── dotnet/              # .NET ASP.NET Core 应用
    └── project-config.md
```

## 使用方法

### 1. 选择匹配的示例

根据你的技术栈选择最接近的示例。

### 2. 复制配置文件

```bash
# 例如：React + Node.js 项目
cp examples/react-node/project-config.md /path/to/your/project/
```

### 3. 根据项目调整

编辑 `project-config.md`，根据你的实际项目调整：
- 文件模式
- 测试命令
- 构建命令
- 需保护的文件

### 4. 验证配置

让 AI 帮你验证：

```
请检查我的 project-config.md 配置是否正确。
项目路径：[你的项目路径]
```

## 添加新示例

欢迎添加更多技术栈示例！

1. 创建新目录：`examples/your-stack/`
2. 复制模板：从现有示例复制
3. 修改配置：根据技术栈调整
4. 提交 PR

参见 [CONTRIBUTING.md](../CONTRIBUTING.md) 了解更多。
