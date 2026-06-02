# Get API Keys Data

> Get API keys information.

**Endpoint**: `GET https://api.litestartup.com/client/v2/settings/keys`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/settings/keys" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "active_key": {
      "id": 1,
      "name": "Default API Key",
      "prefix": "sk-live-xxx",
      "status": "active",
      "last_used_at": "2026-01-29 12:00:00",
      "created_at": "2026-01-01 00:00:00"
    },
    "all_keys": [
      {
        "id": 1,
        "name": "Default API Key",
        "prefix": "sk-live-xxx",
        "status": "active",
        "last_used_at": "2026-01-29 12:00:00",
        "created_at": "2026-01-01 00:00:00"
      }
    ],
    "has_api_key": true
  }
}
```

**Note**: For security reasons, the full API key is only shown once when created or reset. Only the prefix is returned in subsequent requests.

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 500 | Server error |
