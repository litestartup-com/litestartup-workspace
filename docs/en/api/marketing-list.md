# List Campaigns

> Get list of marketing campaigns with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/marketing/list`

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
| status | string | No | Filter by status (draft, scheduled, sending, sent, completed) |
| tag | string | No | Filter by tag |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/marketing/list?page=1&limit=20&status=sent" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "campaigns": [
      {
        "id": 12345,
        "name": "Welcome Campaign",
        "subject": "Welcome to our newsletter!",
        "from_email": "newsletter@yourdomain.com",
        "status": "sent",
        "total_recipients": 1000,
        "created_at": "2026-01-30 10:00:00",
        "sent_at": "2026-01-30 12:00:00"
      }
    ],
    "total": 20,
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
| 403 | Permission denied |
| 500 | Server error |
