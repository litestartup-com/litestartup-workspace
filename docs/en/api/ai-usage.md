# Get AI Usage

> Get AI usage statistics for the current billing period.

**Endpoint**: `GET https://api.litestartup.com/client/v2/ai/usage`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/ai/usage \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "used": 45,
    "limit": 100,
    "remaining": 55,
    "reset_at": "2026-02-01T00:00:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Usage retrieved |
| 401 | Unauthorized |
| 500 | Server error |
