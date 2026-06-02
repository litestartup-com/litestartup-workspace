# Web Routes to API Reference

本文档记录了从 SECTION 2 (Protected Web Pages) 抽象出的 API 接口。

## 基础信息

- **Base URL**: `/{client}/v2` (client: ios|android|partner|client|web)
- **认证**: Session/JWT Auth (AuthForWebMiddleware)
- **响应格式**:
```json
{
  "code": 200,
  "message": "Success",
  "data": {}
}
```

---

## 1. Emails 列表 API (5个)

### GET `/{client}/v2/emails/inbox`
获取收件箱邮件列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |
| label | string | - | 标签筛选 |
| type | string | - | 来源类型 |
| domainEmail | string | all | 域名邮箱筛选 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "emails": [...],
    "total": 100,
    "page": 1,
    "limit": 20,
    "folder": "inbox",
    "counts": { "inbox": 10, "draft": 5 },
    "domain_emails": [...]
  }
}
```

### GET `/{client}/v2/emails/sent`
获取已发送邮件列表 (参数同上)

### GET `/{client}/v2/emails/draft`
获取草稿邮件列表 (参数同上)

### GET `/{client}/v2/emails/trash`
获取回收站邮件列表 (参数同上)

### GET `/{client}/v2/emails/spam`
获取垃圾邮件列表 (参数同上)

---

## 2. Analytics & Dashboard API (2个)

### GET `/{client}/v2/analytics`
获取分析统计数据

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| days | int | 30 | 时间范围 (1-365) |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "stats": {
      "total_campaigns": 10,
      "completed_campaigns": 8,
      "emails_sent": 1000,
      "total_contacts": 500,
      "active_contacts": 450,
      "total_opens": 300,
      "total_clicks": 100,
      "total_unsubscribes": 5,
      "open_rate": 30.0,
      "click_rate": 10.0,
      "unsubscribe_rate": 0.5,
      "engagement_trend": [...]
    },
    "days": 30,
    "start_date": "2025-12-30 00:00:00"
  }
}
```

### GET `/{client}/v2/home/stats`
获取首页/仪表盘统计数据

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "plan": {...},
    "plan_usage": [...],
    "stats": {
      "emails_sent": 100,
      "emails_received": 50,
      "total_contacts": 200,
      "active_campaigns": 3
    }
  }
}
```

---

## 3. Contacts 列表 API (2个)

### GET `/{client}/v2/contacts/list`
获取联系人列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |
| status | string | - | 状态筛选 |
| tag | string | - | 标签筛选 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "contacts": [...],
    "total": 100,
    "page": 1,
    "limit": 20,
    "tags": [...],
    "stats": {...}
  }
}
```

### GET `/{client}/v2/tags/list`
获取标签列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "tags": [...],
    "total": 50,
    "page": 1,
    "limit": 20
  }
}
```

---

## 4. Marketing Campaigns API (3个)

### GET `/{client}/v2/marketing/list`
获取营销活动列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |
| status | string | - | 状态筛选 |
| tag | string | - | 标签筛选 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "campaigns": [...],
    "total": 20,
    "page": 1,
    "limit": 20
  }
}
```

### GET `/{client}/v2/marketing/{id}`
获取单个营销活动详情

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 1,
    "name": "Campaign Name",
    "subject": "Email Subject",
    ...
  }
}
```

### GET `/{client}/v2/marketing/{id}/report`
获取营销活动报告

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "campaign": {...},
    "stats": {
      "total_recipients": 1000,
      "delivered": 980,
      "opens": 300,
      "clicks": 100,
      "unsubscribes": 5,
      "bounces": 20,
      "open_rate": 30.6,
      "click_rate": 10.2,
      "unsubscribe_rate": 0.5,
      "bounce_rate": 2.0
    }
  }
}
```

---

## 5. Templates API (2个)

### GET `/{client}/v2/templates/list`
获取模板列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |
| category | string | - | 分类筛选 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "templates": [...],
    "total": 30,
    "page": 1,
    "limit": 20
  }
}
```

### GET `/{client}/v2/templates/{id}`
获取单个模板详情

---

## 6. Domains API (4个)

### GET `/{client}/v2/domains/list`
获取域名列表

**Query Parameters:**
| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| page | int | 1 | 页码 |
| limit | int | 20 | 每页数量 (max 100) |
| search | string | - | 搜索关键词 |

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "domains": [...],
    "total": 5,
    "page": 1,
    "limit": 20,
    "domain_status_config": {...}
  }
}
```

### GET `/{client}/v2/domains/{slug}`
获取单个域名详情

### GET `/{client}/v2/domain-emails/list`
获取域名邮箱列表

### GET `/{client}/v2/domain-emails/{id}`
获取单个域名邮箱详情

---

## 7. Settings API (5个)

### GET `/{client}/v2/settings/usage`
获取用量统计

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "plan": {...},
    "plan_usage": [...]
  }
}
```

### GET `/{client}/v2/settings/billing`
获取账单信息

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "plan": {...},
    "orders": [...]
  }
}
```

### GET `/{client}/v2/settings/team`
获取团队信息

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "team": {...},
    "members": [...],
    "my_teams": [...],
    "current_team_id": 1,
    "current_user_id": 1,
    "plan_type": "free"
  }
}
```

### GET `/{client}/v2/settings/smtp`
获取 SMTP 配置

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "host": "smtp.litestartup.com",
    "port": 587,
    "encryption": "tls",
    "username": "user@example.com",
    "has_api_key": true,
    "api_key_prefix": "sk-live-xxx"
  }
}
```

### GET `/{client}/v2/settings/keys`
获取 API Keys 信息

**Response:**
```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "active_key": {
      "id": 1,
      "name": "Default API Key",
      "prefix": "sk-live-xxx",
      "status": "active",
      "last_used_at": "2025-01-29 12:00:00",
      "created_at": "2025-01-01 00:00:00"
    },
    "all_keys": [...],
    "has_api_key": true
  }
}
```

---

## 8. Applications API (暂未实现)

> **注意**: Website/Blog/Docs 功能较复杂，建议后期开发。

| 端点 | 方法 | 描述 |
|------|------|------|
| `/website/list` | GET | 获取网站列表 |
| `/website/{slug}` | GET | 获取网站详情 |
| `/blog/posts` | GET | 获取博客文章列表 |
| `/blog/post/{id}` | GET | 获取博客文章详情 |
| `/blog/tags` | GET | 获取博客标签列表 |

---

## 错误码说明

| Code | 说明 |
|------|------|
| 200 | 成功 |
| 400 | 请求参数错误 |
| 401 | 未授权 |
| 403 | 权限不足 |
| 404 | 资源不存在 |
| 500 | 服务器内部错误 |

---

## 修改的文件清单

### Controllers
- `src/Controller/EmailsController.php` - 新增 6 个方法
- `src/Controller/AccountController.php` - 新增 7 个方法
- `src/Controller/ContactsController.php` - 新增 2 个方法
- `src/Controller/MarketingController.php` - 新增 5 个方法
- `src/Controller/DomainsController.php` - 新增 4 个方法

### Repository
- `src/Database/DomainsRepository.php` - 新增 `getDomainEmailById` 方法

### Routes
- `config/routes.php` - 新增 23 条 API 路由

---

## 统计汇总

| 分组 | API 数量 | 状态 |
|------|----------|------|
| Emails | 5 | ✅ 已完成 |
| Analytics & Dashboard | 2 | ✅ 已完成 |
| Contacts | 2 | ✅ 已完成 |
| Marketing | 3 | ✅ 已完成 |
| Templates | 2 | ✅ 已完成 |
| Domains | 4 | ✅ 已完成 |
| Settings | 5 | ✅ 已完成 |
| Applications | 5 | ⏳ 待开发 |
| **总计** | **28** | **23 已完成** |
