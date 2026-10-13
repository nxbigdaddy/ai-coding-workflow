# Task-008：发送应用消息

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 008 |
| 优先级 | P0 |
| 依赖任务 | 007 |
| 设计文档引用 | design.md §8.2、§6 messages API、§5 message_logs |

## 目标

实现文本应用消息发送：选人/选部门、userid 去重、调用企微 API、记录发送历史。

## 范围

### 只改

- `lib/wecom/message.ts`
- `lib/messages/send.ts`（去重逻辑）
- `app/api/messages/route.ts`
- `app/(dashboard)/messages/new/page.tsx`
- `app/(dashboard)/messages/page.tsx`（发送记录列表）
- `app/(dashboard)/settings/sync-logs/page.tsx`（若尚未做，仅 sync_jobs 列表）

### 不改

- 认证、同步、部门树核心逻辑

## 实现要点

- POST `/api/messages`：合并 userids + 部门成员 → Set 去重 → 企微 message/send（text）
- 写入 message_logs（content、target_userids、target_desc、status）
- GET `/api/messages`：分页列表，按 created_at DESC
- 发消息页：成员/部门多选器（可复用通讯录数据）；发送前确认人数
- 企微失败记录 error_message，status=failed

## 验收标准

- [ ] 向 1 人发消息，企微客户端可收到
- [ ] 选部门发消息，部门内成员均收到
- [ ] 同时选人和部门时 userid 去重
- [ ] 发送记录页可查看历史及失败原因
- [ ] 空内容或无人选中返回 400

## 禁止事项

- 不支持图文/图片消息
- 不实现消息模板

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
