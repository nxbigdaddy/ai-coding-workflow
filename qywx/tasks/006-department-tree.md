# Task-006：部门树展示

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 006 |
| 优先级 | P0 |
| 依赖任务 | 005 |
| 设计文档引用 | design.md §7.1 通讯录页、§6 departments API |

## 目标

实现通讯录页面左侧部门树，支持展开折叠，点击部门筛选右侧成员。

## 范围

### 只改

- `app/api/departments/route.ts`
- `app/(dashboard)/contacts/page.tsx`
- `components/contacts/DepartmentTree.tsx`

### 不改

- 成员列表 API 细节（Task-007 可补充）
- 发消息页

## 实现要点

- GET `/api/departments`：从 DB 构建嵌套树 JSON
- 树组件：递归渲染；选中高亮；点击触发 `onSelect(departmentId)`
- 页顶「立即同步」按钮：调 POST /api/sync + 轮询 + 完成后 refresh 树

## 验收标准

- [ ] 同步后部门树层级与企微一致
- [ ] 展开/折叠正常
- [ ] 点击部门可触发选中状态
- [ ] 同步中按钮禁用并显示状态

## 禁止事项

- 不从企微实时拉树
- 不实现编辑部门

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
