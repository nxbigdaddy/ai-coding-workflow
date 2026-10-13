# Phase 2 过程记录：方案对比（模拟）

> 模拟 AI 输出三种技术方案及选型讨论。

---

## 用户输入

```markdown
基于 spec.md，请给出 2～3 种可行方案。
约束：个人开发、熟悉 TypeScript、3～4 周 MVP、内网部署。
```

---

## AI 输出：方案摘要

### 方案 A：Next.js 全栈 + Prisma + PostgreSQL

- 前后端一体，App Router API Routes
- Prisma ORM，开发用 SQLite、生产切 PostgreSQL
- 前端 Tailwind + shadcn/ui
- 难度：**中** | 推荐度：⭐⭐⭐⭐⭐

### 方案 B：Vue3 + NestJS 前后端分离

- 前端 Vite + Vue3 + Element Plus
- 后端 NestJS 独立服务
- 两个仓库或 monorepo
- 难度：**中高** | 推荐度：⭐⭐⭐

### 方案 C：Python FastAPI + React

- 后端 FastAPI 调企微 API
- 前端 React Admin 模板
- 难度：**中** | 推荐度：⭐⭐⭐（用户不熟 Python）

---

## AI 推荐

推荐 **方案 A**，理由：
- 一人开发，单仓库效率最高
- TypeScript 全栈类型共享
- 内网 Docker 部署 Next.js 成熟
- shadcn/ui 适合管理后台

**应选方案 B 的情况**：团队有专职前后端、已有 NestJS 基础设施。

**应选方案 C 的情况**：团队 Python 为主。

---

## 用户决策（模拟）

```markdown
选方案 A：Next.js 全栈 + Prisma。
开发用 SQLite，生产 PostgreSQL。
UI 用 shadcn/ui。
```

---

## 产出

→ [decision.md](../decision.md)
