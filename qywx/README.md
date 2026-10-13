# 企业微信管理工具（qywx）

> 本目录是 **AI 编程工作流完整模拟示例**：从一句想法到可开发任务的全套文档。

## 项目简介

面向中小企业 IT 管理员的 Web 系统，用于配置企业微信应用、同步通讯录、查看组织架构，并向成员发送应用消息。

## 文档导航

### 工作流产物（按阶段顺序阅读）

| 阶段 | 文档 | 说明 |
|------|------|------|
| Phase 0 | [docs/idea.md](docs/idea.md) | 想法捕获 |
| Phase 1 | [docs/spec.md](docs/spec.md) | 需求规格 |
| Phase 2 | [docs/decision.md](docs/decision.md) | 方案决策 |
| Phase 3 | [docs/design.md](docs/design.md) | 详细设计 |
| Phase 4 | [tasks/](tasks/) | 开发任务拆解 |
| Phase 7 | [docs/retrospective.md](docs/retrospective.md) | 交付复盘（模拟） |

### 过程记录（AI 对话模拟）

| 阶段 | 文档 |
|------|------|
| Phase 1 澄清 | [docs/process/01-clarify.md](docs/process/01-clarify.md) |
| Phase 2 方案 | [docs/process/02-solutions.md](docs/process/02-solutions.md) |
| Phase 3 设计评审 | [docs/process/03-design-review.md](docs/process/03-design-review.md) |

### 工具配置

| 文件 | 说明 |
|------|------|
| [.cursor/rules/core.mdc](.cursor/rules/core.mdc) | 项目核心约束 |
| [.cursor/rules/typescript.mdc](.cursor/rules/typescript.mdc) | TypeScript 规范 |
| [.cursor/rules/wecom-api.mdc](.cursor/rules/wecom-api.mdc) | 企业微信 API 约定 |

## 任务列表（Phase 4）

| ID | 任务 | 依赖 |
|----|------|------|
| [001](tasks/001-project-init.md) | 项目初始化 | 无 |
| [002](tasks/002-database-schema.md) | 数据库 Schema | 001 |
| [003](tasks/003-admin-auth.md) | 管理员登录 | 002 |
| [004](tasks/004-wecom-config.md) | 企微凭证配置 | 003 |
| [005](tasks/005-sync-contacts.md) | 通讯录同步 | 004 |
| [006](tasks/006-department-tree.md) | 部门树展示 | 005 |
| [007](tasks/007-member-list.md) | 成员列表 | 005 |
| [008](tasks/008-send-message.md) | 发送应用消息 | 007 |

## 如何使用本示例

1. **学习工作流**：按 Phase 0 → 7 顺序阅读 `docs/` 目录
2. **复制到新项目**：把 `docs/` + `tasks/` + `.cursor/rules/` 作为模板
3. **开始开发**：从 Task-001 起，将任务文档 + design.md 相关章节交给 Cursor Agent

## 状态

- [x] Phase 0～4 文档已完成（模拟）
- [x] Cursor Rules 已提炼
- [ ] Phase 5 代码实现（本示例仅到任务拆解，不含实际代码）
