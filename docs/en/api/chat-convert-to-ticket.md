# Convert Chat to Ticket

> Convert a chat session to a support ticket.

**Endpoint**: `POST https://api.litestartup.com/client/v2/chat/sessions/{id}/to-ticket`

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
curl -X POST https://api.litestartup.com/client/v2/chat/sessions/123/to-ticket \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Ticket created from chat",
  "data": {
    "ticket_id": 456,
    "ticket_number": "TKT-00456"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Ticket created |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
