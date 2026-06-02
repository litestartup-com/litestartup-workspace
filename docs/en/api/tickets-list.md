# List Tickets

> Get a list of support tickets.

**Endpoint**: `GET https://api.litestartup.com/client/v2/tickets`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Results per page (default: 20) |
| status | string | No | Filter by status: `open`, `pending`, `closed` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/tickets?status=open" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "tickets": [
      {
        "id": 123,
        "ticket_number": "TKT-00123",
        "subject": "Cannot send emails",
        "status": "open",
        "priority": "high",
        "created_at": "2026-01-23T10:00:00Z",
        "updated_at": "2026-01-23T12:00:00Z"
      }
    ],
    "pagination": {
      "page": 1,
      "limit": 20,
      "total": 5
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Tickets retrieved |
| 401 | Unauthorized |
| 500 | Server error |
