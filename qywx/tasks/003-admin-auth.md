# Task-003：管理员登录

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 003 |
| 优先级 | P0 |
| 依赖任务 | 002 |
| 设计文档引用 | design.md §6.1 认证接口、§9 |

## 目标

实现管理员登录/登出/会话校验，保护 dashboard 和 API 路由。

## 范围

### 只改

- `lib/auth/`
- `app/api/auth/`
- `middleware.ts`
- `app/(auth)/login/page.tsx`
- `app/(dashboard)/layout.tsx`（鉴权跳转）

### 不改

- 企微配置与同步
- 通讯录、消息模块

## 实现要点

- POST `/api/auth/login`：校验 username/password（bcrypt），写 httpOnly Session Cookie
- POST `/api/auth/logout`：清除 Session
- GET `/api/auth/me`：返回当前管理员信息（不含密码）
- `middleware.ts`：`/api/*`（除 login）和 `/(dashboard)/*` 需登录
- 登录页：表单 + 错误提示

## 验收标准

- [ ] 正确密码可登录并跳转 `/`
- [ ] 错误密码返回 401 及提示
- [ ] 未登录访问 `/api/config` 返回 401
- [ ] 登出后会话失效

## 禁止事项

- 不使用 localStorage 存 token
- 不实现企微 OAuth

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
