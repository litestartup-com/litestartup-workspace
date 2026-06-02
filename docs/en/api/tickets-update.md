# Update Ticket

> Update a ticket's details.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/tickets/{id}`

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
| subject | string | No | Ticket subject |
| priority | string | No | Priority: `low`, `medium`, `high` |
| status | string | No | Status: `open`, `pending`, `closed` |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/tickets/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "priority": "medium",
  "status": "pending"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Ticket updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Ticket updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Ticket not found |
| 500 | Server error |
