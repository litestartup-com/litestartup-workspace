# List Chat Sessions

> Get a list of chat sessions.

**Endpoint**: `GET https://api.litestartup.com/client/v2/chat/sessions`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| status | string | No | Filter by status: `active`, `closed` |
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Results per page (default: 20) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/chat/sessions?status=active" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "sessions": [
      {
        "id": 123,
        "visitor_name": "John",
        "visitor_email": "john@example.com",
        "status": "active",
        "unread_count": 2,
        "last_message": "Hello, I need help...",
        "created_at": "2026-01-23T10:00:00Z"
      }
    ],
    "pagination": {
      "page": 1,
      "limit": 20,
      "total": 5
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Sessions retrieved |
| 401 | Unauthorized |
| 500 | Server error |
