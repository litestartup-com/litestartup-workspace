# Get Chat Config

> Get chat widget configuration.

**Endpoint**: `GET https://api.litestartup.com/client/v2/chat/config`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/chat/config \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "enabled": true,
    "welcome_message": "Hello! How can we help you today?",
    "offline_message": "We are currently offline. Leave a message!",
    "theme_color": "#3B82F6",
    "position": "bottom-right",
    "auto_reply_enabled": true
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Config retrieved |
| 401 | Unauthorized |
| 500 | Server error |
