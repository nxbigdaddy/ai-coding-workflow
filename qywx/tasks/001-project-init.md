# Task-001：项目初始化

> Phase 4 产物

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 001 |
| 优先级 | P0 |
| 依赖任务 | 无 |
| 设计文档引用 | design.md §4、§10 |

## 目标

初始化 Next.js 14 + TypeScript + Tailwind + shadcn/ui 项目骨架，配置 ESLint、环境变量模板和 Docker 占位。

## 范围

### 只改

- 项目根目录（`package.json`、`tsconfig.json`、`next.config.ts` 等）
- `app/` 基础布局（layout、login 占位页）
- `components/ui/`（shadcn 初始化）
- `.env.example`
- `docker-compose.yml`（postgres 服务占位）
- `README.md`（启动说明）

### 不改

- 业务 API
- Prisma schema（Task-002）
- 企微相关代码

## 实现要点

- 使用 `pnpm` 作为包管理器
- App Router 目录结构：`app/(auth)/login`、`app/(dashboard)/`
- 预装 shadcn：Button、Input、Card、Table、Dialog
- `README` 写明 `cp .env.example .env.local && pnpm install && pnpm dev`

## 验收标准

- [ ] `pnpm dev` 可启动，访问 `/login` 有占位页
- [ ] `pnpm lint` 无错误
- [ ] `.env.example` 含 DATABASE_URL、SESSION_SECRET、ENCRYPTION_KEY
- [ ] 目录结构与 design.md §4.2 模块划分一致（空目录即可）

## 禁止事项

- 不实现真实登录逻辑
- 不引入企微 SDK
- 不扩 MVP 范围

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
