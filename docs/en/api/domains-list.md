# List Domains

> Get list of domains with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/domains/list`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Items per page (default: 20, max: 100) |
| search | string | No | Search keyword |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/domains/list?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "domains": [
      {
        "id": 12345,
        "domain": "mail.yourdomain.com",
        "domain_slug": "domain-abc123",
        "status": "verified",
        "created_at": "2026-01-30 10:00:00"
      }
    ],
    "total": 5,
    "page": 1,
    "limit": 20,
    "domain_status_config": {
      "pending": {"label": "Pending", "color": "yellow"},
      "verified": {"label": "Verified", "color": "green"},
      "failed": {"label": "Failed", "color": "red"}
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 500 | Server error |
