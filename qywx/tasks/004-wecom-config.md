# Task-004：企微凭证配置

## 元信息

| 项 | 内容 |
|----|------|
| 任务 ID | 004 |
| 优先级 | P0 |
| 依赖任务 | 003 |
| 设计文档引用 | design.md §5 wecom_config、§6 config API、§9 加密 |

## 目标

实现企微 corpId/agentId/secret 的配置读写，secret 加密存储，保存时验证可获取 token。

## 范围

### 只改

- `lib/crypto/`
- `lib/wecom/client.ts`（gettoken 基础）
- `app/api/config/route.ts`
- `app/(dashboard)/settings/page.tsx`

### 不改

- 通讯录同步逻辑
- 发消息逻辑

## 实现要点

- AES-256-GCM 加解密 secret，密钥 `ENCRYPTION_KEY`
- GET `/api/config`：返回 corpId、agentId、secret=`******`
- PUT `/api/config`：保存并调用企微 gettoken 验证；失败返回 400 + 原因
- 设置页：表单三字段；secret 留空表示不修改

## 验收标准

- [ ] 合法凭证保存成功，DB 中 secret 为密文
- [ ] GET 不返回 secret 明文
- [ ] 错误 secret 保存失败并有提示
- [ ] 设置页可展示已保存的 corpId/agentId

## 禁止事项

- 不在日志中打印 secret
- 不将 secret 返回给前端明文

## 状态

- [ ] 待开发
- [ ] 开发中
- [ ] 已验证
- [ ] 已完成
