# List Templates

> Get list of email templates with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/templates/list`

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
| category | string | No | Filter by category |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/templates/list?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "templates": [
      {
        "id": 12345,
        "name": "Welcome Template",
        "category": "onboarding",
        "thumbnail": "https://...",
        "created_at": "2026-01-30 10:00:00",
        "updated_at": "2026-01-30 12:00:00"
      }
    ],
    "total": 30,
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
