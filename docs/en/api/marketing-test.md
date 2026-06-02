# Test Campaign

> Send a test email for a campaign.

**Endpoint**: `POST https://api.litestartup.com/client/v2/marketing/test`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| from_email | string | Yes | Sender email address |
| subject | string | Yes | Email subject line |
| content | string | Yes | HTML email content |
| test_email | string | Yes | Email address to send test to |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/marketing/test \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "from_email": "newsletter@yourdomain.com",
  "subject": "Test: Welcome Campaign",
  "content": "<h1>Welcome!</h1><p>This is a test email.</p>",
  "test_email": "test@example.com"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Test email sent successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Test email sent |
| 400 | Invalid email or missing fields |
| 401 | Unauthorized |
| 500 | Server error |
