# Close Chat Session

> Close a chat session.

**Endpoint**: `POST https://api.litestartup.com/client/v2/chat/sessions/{id}/close`

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
curl -X POST https://api.litestartup.com/client/v2/chat/sessions/123/close \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Session closed",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Session closed |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
