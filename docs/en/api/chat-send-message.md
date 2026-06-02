# Send Chat Message

> Send a message in a chat session.

**Endpoint**: `POST https://api.litestartup.com/client/v2/chat/sessions/{id}/message`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Session ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| message | string | Yes | Message content |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/chat/sessions/123/message \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "message": "Thank you for contacting us. Let me help you with that."
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Message sent",
  "data": {
    "id": 456
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Message sent |
| 400 | Missing message |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
