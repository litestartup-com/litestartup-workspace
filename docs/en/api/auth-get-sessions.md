# Get Sessions

> Get all active sessions for the authenticated user.

**Endpoint**: `GET https://api.litestartup.com/client/v2/auth/sessions`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/auth/sessions \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "sessions": [
      {
        "id": 1,
        "device": "Chrome on Windows",
        "ip_address": "192.168.1.1",
        "last_active": "2026-01-23T10:00:00Z",
        "is_current": true
      },
      {
        "id": 2,
        "device": "Safari on macOS",
        "ip_address": "192.168.1.2",
        "last_active": "2026-01-22T15:30:00Z",
        "is_current": false
      }
    ]
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Sessions retrieved |
| 401 | Unauthorized |
| 500 | Server error |
