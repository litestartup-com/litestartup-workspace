# Poll Chat Messages

> Poll for new chat messages across all sessions.

**Endpoint**: `GET https://api.litestartup.com/client/v2/chat/poll`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| since | string | No | ISO 8601 timestamp to get messages since |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/chat/poll?since=2026-01-23T10:00:00Z" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "messages": [
      {
        "session_id": 123,
        "message_id": 456,
        "content": "Hello!",
        "sender_type": "visitor",
        "created_at": "2026-01-23T10:05:00Z"
      }
    ],
    "new_sessions": 1,
    "unread_count": 3
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Poll successful |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- Use this endpoint for real-time updates (polling every 5-10 seconds recommended).
