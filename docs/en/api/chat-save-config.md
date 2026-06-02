# Save Chat Config

> Save chat widget configuration.

**Endpoint**: `POST https://api.litestartup.com/client/v2/chat/config`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| enabled | boolean | No | Enable/disable chat widget |
| welcome_message | string | No | Welcome message for visitors |
| offline_message | string | No | Message when offline |
| theme_color | string | No | Widget theme color (hex) |
| position | string | No | Widget position: `bottom-right`, `bottom-left` |
| auto_reply_enabled | boolean | No | Enable auto-reply |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/chat/config \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "enabled": true,
  "welcome_message": "Hi there! How can we help?",
  "theme_color": "#10B981"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Config saved successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Config saved |
| 400 | Invalid data |
| 401 | Unauthorized |
| 500 | Server error |
