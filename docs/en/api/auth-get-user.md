# Get Current User

> Get the authenticated user's information.

**Endpoint**: `GET https://api.litestartup.com/client/v2/auth/user`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/auth/user \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "email": "user@example.com",
    "name": "John Doe",
    "avatar": "https://example.com/avatar.jpg",
    "team_id": 1,
    "role": "admin",
    "created_at": "2026-01-01T00:00:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | User info retrieved |
| 401 | Unauthorized |
| 500 | Server error |
