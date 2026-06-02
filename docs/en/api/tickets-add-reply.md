# Add Ticket Reply

> Add a reply to a ticket.

**Endpoint**: `POST https://api.litestartup.com/client/v2/tickets/{id}/replies`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Ticket ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| message | string | Yes | Reply message content |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/tickets/123/replies \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "message": "Thank you for your response. I have tried the suggested solution..."
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Reply added successfully",
  "data": {
    "id": 456
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Reply added |
| 400 | Missing message |
| 401 | Unauthorized |
| 404 | Ticket not found |
| 500 | Server error |
