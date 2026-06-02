# Get SMTP Config

> Get SMTP configuration for email sending.

**Endpoint**: `GET https://api.litestartup.com/client/v2/settings/smtp`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/settings/smtp" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "host": "smtp.litestartup.com",
    "port": 587,
    "encryption": "tls",
    "username": "user@example.com",
    "has_api_key": true,
    "api_key_prefix": "sk-live-xxx"
  }
}
```

**SMTP Configuration**

Use the following settings in your email client or application:

| Setting | Value |
|---------|-------|
| Host | smtp.litestartup.com |
| Port | 587 |
| Encryption | TLS |
| Username | Your email address |
| Password | Your API key |

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 500 | Server error |
