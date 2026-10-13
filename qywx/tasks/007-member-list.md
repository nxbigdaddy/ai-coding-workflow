# Task-007：成员列表

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 007 |
| 优先级 | P0 |
| 依赖任务 | 005 |
| 设计文档引用 | design.md §6 members API、§7 通讯录页 |

## 目标

实现成员列表：按部门筛选、姓名搜索、分页（默认 20 条/页），手机号掩码展示。

## 范围

### 只改

- `app/api/members/route.ts`
- `components/contacts/MemberTable.tsx`
- `app/(dashboard)/contacts/page.tsx`（集成右侧表格）

### 不改

- 同步逻辑
- 发消息 API

## 实现要点

- GET `/api/members?departmentId&keyword&page&pageSize`
- `departmentId` 筛选 members.department_ids 包含该 id
- `keyword` 模糊匹配 name
- 默认 pageSize=20
- 手机号展示：138****8000

## 验收标准

- [ ] 不选部门时显示全部成员（分页）
- [ ] 选部门后仅显示该部门成员
- [ ] 搜索「张」可过滤姓名
- [ ] 分页 total/page 正确

## 禁止事项

- 不展示 secret 等敏感字段
- 不支持编辑成员

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
