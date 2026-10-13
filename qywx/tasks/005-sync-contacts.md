# Task-005：通讯录同步

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 005 |
| 优先级 | P0 |
| 依赖任务 | 004 |
| 设计文档引用 | design.md §8.1、§5 sync_jobs、§6 sync API |

## 目标

实现手动触发全量通讯录同步：拉取部门与成员写入 DB，记录 sync_job 状态。

## 范围

### 只改

- `lib/wecom/departments.ts`、`lib/wecom/members.ts`
- `lib/sync/contacts.ts`
- `app/api/sync/route.ts`
- `app/api/sync/jobs/` 路由

### 不改

- 前端树/列表 UI（Task-006/007）
- 发消息

## 实现要点

- POST `/api/sync`：若已有 running job 返回 409；否则创建 job 并异步执行
- 流程：gettoken → department/list → 逐部门 user/list → upsert
- GET `/api/sync/jobs`、`GET /api/sync/jobs/:id` 供轮询
- 失败写 error_message；成功写 dept_count、member_count

## 验收标准

- [ ] 同步完成后 departments、members 表有数据
- [ ] sync_jobs 状态从 running → success
- [ ] 重复点击同步时 running 状态返回 409
- [ ] 企微 API 失败时 job 为 failed 且有错误信息

## 禁止事项

- 不做定时自动同步
- 不实时读企微（列表仍读本地 DB）

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
