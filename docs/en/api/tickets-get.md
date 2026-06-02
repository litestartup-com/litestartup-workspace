# Get Ticket

> Get details of a specific ticket.

**Endpoint**: `GET https://api.litestartup.com/client/v2/tickets/{id}`

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
curl -X GET https://api.litestartup.com/client/v2/tickets/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 123,
    "ticket_number": "TKT-00123",
    "subject": "Cannot send emails",
    "status": "open",
    "priority": "high",
    "assigned_to": null,
    "replies": [
      {
        "id": 1,
        "message": "I am getting an error...",
        "user_id": 456,
        "created_at": "2026-01-23T10:00:00Z"
      }
    ],
    "created_at": "2026-01-23T10:00:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Ticket retrieved |
| 401 | Unauthorized |
| 404 | Ticket not found |
| 500 | Server error |
