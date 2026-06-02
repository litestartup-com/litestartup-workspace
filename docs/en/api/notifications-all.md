# Get All Notifications

> Get all notifications with pagination.

**Endpoint**: `GET https://api.litestartup.com/client/v2/notifications/all`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Results per page (default: 20) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/notifications/all?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "notifications": [...],
    "pagination": {
      "page": 1,
      "limit": 20,
      "total": 50,
      "total_pages": 3
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Notifications retrieved |
| 401 | Unauthorized |
| 500 | Server error |
