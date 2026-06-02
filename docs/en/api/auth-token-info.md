# Get Token Info

> Get information about the current access token.

**Endpoint**: `GET https://api.litestartup.com/client/v2/auth/token-info`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/auth/token-info \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "user_id": 12345,
    "email": "user@example.com",
    "issued_at": "2026-01-23T10:00:00Z",
    "expires_at": "2026-01-23T11:00:00Z",
    "scopes": ["read", "write"]
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Token info retrieved |
| 401 | Invalid or expired token |
| 500 | Server error |
