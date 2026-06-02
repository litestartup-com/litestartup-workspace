# Send Email

> Send a single email or batch of emails.

**Endpoint**: `POST https://api.litestartup.com/client/v2/emails`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| to | string \| string[] | Yes | Recipient email address(es) |
| from | string | Yes | Sender email address. Supports format: `sender@domain.com` or `Your Name <sender@domain.com>` |
| subject | string | Yes | Email subject line |
| html | string | Yes | HTML email body |
| text | string | No | Plain text email body (auto-generated from HTML if not provided) |
| replyTo | string | No | Reply-to email address |
| cc | string \| string[] | No | CC recipients |
| bcc | string \| string[] | No | BCC recipients |
| template | object | No | Email template |
| template.id | string | No | Template ID (string_id from your templates) |
| template.variables | object | No | Template variables for placeholder replacement |

**Example 1: Send a single email**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "recipient@example.com",
  "from": "Your Name <sender@yourdomain.com>",
  "subject": "Welcome!",
  "html": "<h1>Hello</h1><p>Welcome to litestartup.</p>"
}'
```

**Example 2: Send to multiple recipients with CC/BCC**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": ["user1@example.com", "user2@example.com"],
  "from": "sender@yourdomain.com",
  "subject": "Team Update",
  "html": "<p>Hello team!</p>",
  "cc": "manager@example.com",
  "bcc": ["admin@example.com"]
}'
```

**Example 3: Send using a template**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "recipient@example.com",
  "from": "sender@yourdomain.com",
  "subject": "Welcome {{name}}!",
  "html": "",
  "template": {
    "id": "welcome-template-001",
    "variables": {
      "name": "John",
      "company": "Acme Inc"
    }
  }
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "messageId": "xxxxxxxxxxxxxxxx"
  }
}
```

**Response (Error)**

```json
{
  "code": 500,
  "message": "From email or to email is required",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email sent successfully |
| 400 | Invalid request parameters |
| 404 | Template not found (when using template) |
| 429 | Rate limit exceeded (monthly or daily usage limit) |
| 500 | Server error or missing required fields |

**Rate Limits**

- Monthly email limit based on your subscription plan
- Daily email limit based on your subscription plan

When limits are exceeded, the API returns HTTP 429 with message `"monthly usage exceeded the limit"` or `"daily usage exceeded the limit"`.
