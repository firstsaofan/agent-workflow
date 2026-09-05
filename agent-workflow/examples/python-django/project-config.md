# 项目配置 - Python Django 示例

## 基本信息
- 项目名称：Django Web 应用
- 项目路径：/path/to/your/project
- 版本控制：Git

## 技术栈
- 编程语言：Python
- 框架/库：Django 4+
- 包管理器：pip + venv
- 运行环境：Python 3.10+

## 文件范围

### 后端 Agent
- 可修改文件模式：
  - **/*.py
  - **/*.html
  - **/*.css
  - **/*.js (Django 模板中的 JS)
- 不可修改文件：
  - static/**/*.js (如果有分离的前端)
  - docker-compose.yml
  - requirements.txt (不要随意添加依赖)
- 测试命令：pytest
- 构建命令：python manage.py collectstatic

### 前端 Agent（如果有分离的前端）
- 可修改文件模式：
  - static/**/*.js
  - static/**/*.css
  - templates/**/*.html
- 不可修改文件：
  - **/*.py
  - manage.py
- 测试命令：npm test
- 构建命令：npm run build

## 项目检测
- 配置文件：requirements.txt, pyproject.toml, manage.py, settings.py
- 入口文件：manage.py, wsgi.py, asgi.py

## 常用命令
- 安装依赖：pip install -r requirements.txt
- 运行测试：pytest
- 代码检查：flake8 || black --check
- 构建项目：python manage.py collectstatic
- 数据库迁移：python manage.py migrate
- 创建超级用户：python manage.py createsuperuser

## 需保护的文件
- .env (环境变量)
- settings/production.py (生产配置)
- db.sqlite3 (数据库文件)
- migrations/ (数据库迁移，不要随意修改)
- requirements.txt (不要随意添加依赖)

## 团队角色
- 后端开发：负责 Django 视图、模型、API
- 前端开发：负责模板和静态文件
- 全栈开发：负责集成和配置
