# List Inbound Emails

> Retrieve a list of received (inbound) emails.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/receiving`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Number of results per page (default: 20, max: 100) |
| status | string | No | Filter by status: `unread`, `read` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/emails/receiving?page=1&limit=20" \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "emails": [
      {
        "id": 12345,
        "message_id": "abc123@sender-domain.com",
        "from_email": "sender@example.com",
        "from_name": "John Doe",
        "to_email": "you@yourdomain.com",
        "subject": "Hello!",
        "status": "unread",
        "received_at": "2026-01-23 10:30:00"
      }
    ],
    "pagination": {
      "page": 1,
      "limit": 20,
      "total": 50,
      "total_pages": 3
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Emails retrieved successfully |
| 401 | Invalid or missing API key |
| 500 | Server error |
