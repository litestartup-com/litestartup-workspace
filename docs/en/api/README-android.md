# Litestartup API Documentation

> Client API v2 - RESTful API for email and marketing operations

## Base URL

```
https://api.litestartup.com/android/v2
```

## Authentication

API requests can be authenticated using:

**JWT Token**:
```
Authorization: Bearer YOUR_JWT_ACCESS_TOKEN
```

---

## API Endpoints

### Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/auth/request-auth-code](auth-request-auth-code.md) | Request auth code via email （通过邮件验证码登录或注册） |
| POST | [/auth/verify-auth-code](auth-verify-auth-code.md) | Verify auth code via email （通过邮件验证码验证身份） |
| POST | [/auth/request-forgot-password](auth-request-forgot-password.md) | Request password reset （申请重置密码） |
| POST | [/auth/submit-reset-password](auth-submit-reset-password.md) | Submit new password （提交新密码） |
| POST | [/auth/token](auth-token.md) | Get JWT token(refresh token and access token) using email and password （使用邮箱与密码登录并获取 JWT Refresh/Access令牌） |
| POST | [/auth/refresh](auth-refresh-token.md) | Refresh access token （Access令牌过期，获取新的Access令牌） |
| POST | [/auth/revoke](auth-revoke-token.md) | Revoke token (logout) （撤销令牌并退出登录） |
| GET  | [/auth/oauth-config](auth-oauth-config.md) | Get google and github client id and callback url （获取 Google/GitHub ClientId 与回调地址） |

### Emails List (Folders)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/inbox](emails-inbox-list.md) | List inbox emails （获取收件箱邮件列表） |
| GET | [/emails/sent](emails-sent-list.md) | List sent emails （获取已发送邮件列表） |
| GET | [/emails/draft](emails-draft-list.md) | List draft emails （获取草稿邮件列表） |
| GET | [/emails/trash](emails-trash-list.md) | List trash emails （获取回收站邮件列表） |
| GET | [/emails/spam](emails-spam-list.md) | List spam emails （获取垃圾邮件列表） |

### Outbound Emails (Sending)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/emails](email-send.md) | Send email （发送邮件） |
| GET | [/emails](email-list.md) | List sent emails （列出已发送邮件） |
| GET | [/emails/{id}](email-get.md) | Get email details （获取邮件详情） |
| DELETE | [/emails/{id}](email-delete.md) | Delete email （删除邮件） |

### Inbound Emails (Receiving)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/receiving](email-list-inbound.md) | List received emails （列出收到的邮件） |
| GET | [/emails/receiving/{id}](email-get-inbound.md) | Get received email details （获取收到的邮件详情） |
| DELETE | [/emails/receiving/{id}](email-delete-inbound.md) | Delete received email （删除收到的邮件） |
| POST | [/emails/receiving/{id}/reply](email-reply.md) | Reply to email （回复邮件） |
| POST | [/emails/receiving/{id}/forward](email-forward.md) | Forward email （转发邮件） |

### Attachments

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/receiving/{id}/attachment](email-list-attachments.md) | List attachments （列出附件） |
| GET | [/emails/receiving/{id}/attachment/{attachmentId}](email-download-attachment.md) | Download attachment （下载附件） |
| DELETE | [/emails/receiving/{id}/attachment/{attachmentId}](email-delete-attachment.md) | Delete attachment （删除附件） |

### Contacts

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/contacts/list](contacts-list.md) | List contacts （获取联系人列表） |
| POST | [/contacts/add](contacts-add.md) | Add contact （新增联系人） |
| GET | [/contacts/search](contacts-search.md) | Search contacts （搜索联系人） |
| GET | [/contacts/get](contacts-get.md) | Get contact （获取联系人详情） |
| PUT | [/contacts/update](contacts-update.md) | Update contact （更新联系人） |
| DELETE | [/contacts/delete](contacts-delete.md) | Delete contact （删除联系人） |
| POST | [/contacts/import](contacts-import.md) | Import contacts （导入联系人） |
| GET | [/contacts/export](contacts-export.md) | Export contacts （导出联系人） |

### Tags

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/tags/list](tags-list.md) | List tags （获取标签列表） |
| POST | [/tags/create](tags-create.md) | Create tag （创建标签） |
| PUT | [/tags/update](tags-update.md) | Update tag （更新标签） |
| DELETE | [/tags/delete](tags-delete.md) | Delete tag （删除标签） |

### Marketing Campaigns

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/marketing/list](marketing-list.md) | List campaigns （获取营销活动列表） |
| GET | [/marketing/{id}](marketing-get.md) | Get campaign detail （获取营销活动详情） |
| GET | [/marketing/{id}/report](marketing-report.md) | Get campaign report （获取营销活动报告） |
| POST | [/marketing/create](marketing-create.md) | Create campaign （创建营销活动） |
| PUT | [/marketing/update/{id}](marketing-update.md) | Update campaign （更新营销活动） |
| POST | [/marketing/copy/{id}](marketing-copy.md) | Copy campaign （复制营销活动） |
| DELETE | [/marketing/delete/{id}](marketing-delete.md) | Delete campaign （删除营销活动） |
| POST | [/marketing/test](marketing-test.md) | Send test email （发送测试邮件） |

### Templates

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/templates/list](templates-list.md) | List templates （获取模板列表） |
| GET | [/templates/{id}](templates-get.md) | Get template detail （获取模板详情） |
| POST | [/templates/create](templates-create.md) | Create template （创建模板） |
| PUT | [/templates/update/{id}](templates-update.md) | Update template （更新模板） |
| POST | [/templates/copy/{id}](templates-copy.md) | Copy template （复制模板） |
| GET | [/templates/content/{id}](templates-get-content.md) | Get template content （获取模板内容） |
| DELETE | [/templates/delete/{id}](templates-delete.md) | Delete template （删除模板） |

### Domains

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/domains/list](domains-list.md) | List domains （获取域名列表） |
| GET | [/domains/{slug}](domains-get.md) | Get domain detail （获取域名详情） |
| POST | [/domains/add](domains-add.md) | Add domain （新增发信域名） |
| POST | [/domain/submit-domain-verify](domains-verify.md) | Submit domain verification （提交域名验证） |
| GET | [/domain/domain-verify-polling](domains-verify-polling.md) | Poll verification status （轮询验证状态） |
| PUT | [/domain/config/{domainSlug}](domains-config.md) | Configure domain （配置域名） |
| PUT | [/domain/update/{domainSlug}](domains-update.md) | Update domain （更新域名） |
| DELETE | [/domain/{domainSlug}](domains-delete.md) | Delete domain （删除域名） |

### Domain Emails

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/domain-emails/list](domain-emails-list.md) | List domain emails （获取域名邮箱列表） |
| GET | [/domain-emails/{id}](domain-emails-get.md) | Get domain email detail （获取域名邮箱详情） |
| POST | [/domain-emails/add](domain-emails-add.md) | Add domain email （新增域名邮箱） |
| PUT | [/domain-emails/{emailId}](domain-emails-update.md) | Update domain email （更新域名邮箱） |
| DELETE | [/domain-emails/{emailId}](domain-emails-delete.md) | Delete domain email （删除域名邮箱） |

### Team

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/team/create](team-create.md) | Create team （创建团队） |
| POST | [/team/invite](team-invite.md) | Invite member （邀请成员） |
| PUT | [/team/set-default](team-set-default.md) | Set default team （设置默认团队） |
| DELETE | [/team/member/{userId}](team-remove-member.md) | Remove member （移除成员） |
| PUT | [/team/member/{userId}/role](team-update-member-role.md) | Update member role （更新成员角色） |

### Notifications

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/notifications](notifications-list.md) | List notifications （列出通知） |
| GET | [/notifications/unread-count](notifications-unread-count.md) | Get unread count （获取未读数量） |
| GET | [/notifications/all](notifications-all.md) | Get all notifications （获取全部通知） |
| PUT | [/notifications/{id}/read](notifications-mark-read.md) | Mark as read （标记为已读） |
| PUT | [/notifications/read-all](notifications-mark-all-read.md) | Mark all as read （全部标记已读） |
| DELETE | [/notifications/{id}](notifications-delete.md) | Delete notification （删除通知） |

### Settings

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/settings/usage](settings-usage.md) | Get usage data （获取用量统计） |
| GET | [/settings/billing](settings-billing.md) | Get billing data （获取账单信息） |
| GET | [/settings/team](settings-team.md) | Get team data （获取团队信息） |
| GET | [/settings/smtp](settings-smtp.md) | Get SMTP config （获取 SMTP 配置） |
| GET | [/settings/keys](settings-keys.md) | Get API keys data （获取 API Keys 信息） |
| POST | [/settings/reset-api-key](settings-reset-api-key.md) | Reset API key （重置 API Key） |
| PUT | [/settings/update-team](settings-update-team.md) | Update team settings （更新团队设置） |

### Analytics & Dashboard

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/analytics](analytics-get.md) | Get analytics data （获取分析统计数据） |
| GET | [/home/stats](home-stats.md) | Get dashboard stats （获取首页统计数据） |

### Subscription

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/subscription/create](subscription-create.md) | Create subscription (创建支付Pro计划，返回PayPal支付链接) |
| POST | [/subscription/downgrade](subscription-downgrade.md) | Downgrade plan （取消Pro计划） |

### Profile

| Method | Endpoint | Description |
|--------|----------|-------------|
| PUT | [/profile/update/{id}](profile-update.md) | Update profile （更新个人信息） |

### AI

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/ai/template/generate](ai-template-generate.md) | Generate AI template （生成 AI 模板） |
| GET | [/ai/request/{id}](ai-request-status.md) | Get request status （获取任务状态） |
| GET | [/ai/requests](ai-requests-list.md) | List AI requests （列出 AI 任务） |
| POST | [/ai/request/{id}/cancel](ai-request-cancel.md) | Cancel request （取消 AI 任务） |
| GET | [/ai/usage](ai-usage.md) | Get AI usage （获取 AI 使用量） |

### Public APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/contact/send](contact-send.md) | Send contact message （发送联系表单信息） |

---

## Response Format

All API responses follow this format:

```json
{
  "code": 200,
  "message": "Success",
  "data": { ... }
}
```

### Common HTTP Status Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Bad Request - Invalid parameters |
| 401 | Unauthorized - Invalid API key or token |
| 403 | Forbidden - Access denied |
| 404 | Not Found |
| 429 | Too Many Requests - Rate limit exceeded |
| 500 | Internal Server Error |

---

## Quick Start

### 1. Verify your API key

```bash
curl -X GET https://api.litestartup.com/client/v2/verify \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

### 2. Send your first email

```bash
curl -X POST https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "recipient@example.com",
  "from": "Your Name <sender@yourdomain.com>",
  "subject": "Hello from Litestartup!",
  "html": "<h1>Welcome!</h1><p>This is your first email via API.</p>"
}'
```

### 3. Check sent emails

```bash
curl -X GET https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

---

## SDKs & Libraries

Coming soon:
- Node.js SDK
- Python SDK
- PHP SDK

---

## Support

- Email: support@litestartup.com
- Documentation: https://docs.litestartup.com

---

## Changelog

| Date | Version | Description |
|------|---------|-------------|
| 2026-01-23 | 1.0.0 | Initial API documentation release |
| 2026-01-30 | 1.1.0 | Added list APIs for emails, contacts, tags, marketing, templates, domains, settings, analytics |

---

*Last updated: January 30, 2026*