# Update SMTP Settings

> Update SMTP configuration for email sending.

**Endpoint**: `POST https://api.litestartup.com/client/v2/settings/updateSmtp`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| smtp_host | string | Yes | SMTP server hostname |
| smtp_port | integer | Yes | SMTP server port |
| smtp_username | string | Yes | SMTP username |
| smtp_password | string | Yes | SMTP password |
| smtp_encryption | string | No | Encryption type: `tls`, `ssl`, `none` |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/settings/updateSmtp \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "smtp_host": "smtp.example.com",
  "smtp_port": 587,
  "smtp_username": "user@example.com",
  "smtp_password": "password",
  "smtp_encryption": "tls"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "SMTP settings updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Settings updated |
| 400 | Invalid configuration |
| 401 | Unauthorized |
| 500 | Server error |
