# Get Chat Session

> Get details of a specific chat session.

**Endpoint**: `GET https://api.litestartup.com/client/v2/chat/sessions/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Session ID |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/chat/sessions/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 123,
    "visitor_name": "John",
    "visitor_email": "john@example.com",
    "status": "active",
    "assigned_to": null,
    "messages": [
      {
        "id": 1,
        "content": "Hello, I need help with...",
        "sender_type": "visitor",
        "created_at": "2026-01-23T10:00:00Z"
      },
      {
        "id": 2,
        "content": "Hi! How can I help you?",
        "sender_type": "agent",
        "created_at": "2026-01-23T10:01:00Z"
      }
    ],
    "created_at": "2026-01-23T10:00:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Session retrieved |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
