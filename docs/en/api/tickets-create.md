# Create Ticket

> Create a new support ticket.

**Endpoint**: `POST https://api.litestartup.com/client/v2/tickets`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| subject | string | Yes | Ticket subject |
| message | string | Yes | Initial message content |
| priority | string | No | Priority: `low`, `medium`, `high` (default: `medium`) |
| category | string | No | Ticket category |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/tickets \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "subject": "Cannot send emails",
  "message": "I am getting an error when trying to send emails...",
  "priority": "high"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Ticket created successfully",
  "data": {
    "id": 123,
    "ticket_number": "TKT-00123"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Ticket created |
| 400 | Missing required fields |
| 401 | Unauthorized |
| 500 | Server error |
