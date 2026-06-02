# List AI Requests

> Get a list of AI generation requests.

**Endpoint**: `GET https://api.litestartup.com/client/v2/ai/requests`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Results per page (default: 20) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/ai/requests?page=1&limit=10" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "requests": [
      {
        "id": "req_abc123",
        "type": "template",
        "status": "completed",
        "created_at": "2026-01-23T10:00:00Z"
      }
    ],
    "pagination": {
      "page": 1,
      "limit": 10,
      "total": 25
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Requests retrieved |
| 401 | Unauthorized |
| 500 | Server error |
