# List Tags

> Get list of tags with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/tags/list`

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
curl -X GET "https://api.litestartup.com/client/v2/tags/list?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "tags": [
      {
        "id": 1,
        "name": "VIP",
        "color": "#FF5733",
        "contact_count": 100,
        "created_at": "2026-01-30 10:00:00"
      },
      {
        "id": 2,
        "name": "Newsletter",
        "color": "#33FF57",
        "contact_count": 250,
        "created_at": "2026-01-29 10:00:00"
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
| 403 | Permission denied |
| 500 | Server error |
