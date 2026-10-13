# Task-002：数据库 Schema

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 002 |
| 优先级 | P0 |
| 依赖任务 | 001 |
| 设计文档引用 | design.md §5 |

## 目标

用 Prisma 定义全部数据表，完成迁移，并提供种子脚本创建初始管理员。

## 范围

### 只改

- `prisma/schema.prisma`
- `prisma/migrations/`
- `prisma/seed.ts`
- `lib/db/client.ts`

### 不改

- API 路由
- 前端页面
- 企微集成

## 实现要点

- 表：admins、wecom_config、departments、members、sync_jobs、message_logs
- 字段与 design.md §5.2 一致
- `members.department_ids` 用 Json 类型
- seed：创建默认 admin（用户名 admin，密码从 `INITIAL_ADMIN_PASSWORD` 读取，默认 `changeme`）

## 验收标准

- [ ] `pnpm prisma migrate dev` 成功
- [ ] `pnpm prisma db seed` 可创建管理员
- [ ] 所有表与 design.md ER 图一致
- [ ] `lib/db/client.ts` 导出单例 PrismaClient

## 禁止事项

- 不修改已确认表名/字段语义
- 不添加 spec 外的新表

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
