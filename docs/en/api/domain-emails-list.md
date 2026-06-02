# List Domain Emails

> Get list of domain emails with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/domain-emails/list`

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
curl -X GET "https://api.litestartup.com/client/v2/domain-emails/list?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "domain_emails": [
      {
        "id": 12345,
        "email_address": "info@yourdomain.com",
        "email_name": "Info",
        "email_type": "shared",
        "status": "active",
        "created_at": "2026-01-30 10:00:00"
      }
    ],
    "total": 10,
    "page": 1,
    "limit": 20
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
