# Close Ticket

> Close a support ticket.

**Endpoint**: `POST https://api.litestartup.com/client/v2/tickets/{id}/close`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Ticket ID |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/tickets/123/close \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Ticket closed successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Ticket closed |
| 401 | Unauthorized |
| 404 | Ticket not found |
| 500 | Server error |
