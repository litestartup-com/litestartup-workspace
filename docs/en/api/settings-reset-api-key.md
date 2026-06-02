# Reset API Key

> Generate a new API key (invalidates the old one).

**Endpoint**: `POST https://api.litestartup.com/client/v2/settings/reset-api-key`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/settings/reset-api-key \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "API key reset successfully",
  "data": {
    "api_key": "sk_live_xxxxxxxxxxxxxxxxxxxxx"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | API key reset |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- The old API key will be immediately invalidated.
- Make sure to update your applications with the new key.
