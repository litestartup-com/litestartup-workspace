# Reply to Email

> Reply to a received (inbound) email.

**Endpoint**: `POST https://api.litestartup.com/client/v2/emails/receiving/{id}/reply`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID to reply to |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| to | string \| string[] | Yes | Recipient email address(es) |
| from | string | Yes | Sender email address |
| subject | string | Yes | Email subject line |
| html | string | Yes | HTML email body |
| cc | string \| string[] | No | CC recipients |
| bcc | string \| string[] | No | BCC recipients |
| replyTo | string | No | Reply-to email address |
| inReplyToHeader | string | No | Message-ID of the email being replied to |
| referencesHeader | string | No | References header for email threading |
| conversationId | integer | No | Conversation ID for threading |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails/receiving/12345/reply \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "sender@example.com",
  "from": "you@yourdomain.com",
  "subject": "Re: Hello!",
  "html": "<p>Thank you for your message!</p>"
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
| 200 | Reply sent successfully |
| 429 | Rate limit exceeded |
| 500 | Server error or missing required fields |
