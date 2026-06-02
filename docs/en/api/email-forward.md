# Forward Email

> Forward a received (inbound) email to another recipient.

**Endpoint**: `POST https://api.litestartup.com/client/v2/emails/receiving/{id}/forward`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID to forward |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| to | string \| string[] | Yes | Recipient email address(es) to forward to |
| from | string | Yes | Sender email address |
| subject | string | Yes | Email subject line (typically prefixed with "Fwd:") |
| html | string | Yes | HTML email body (including forwarded content) |
| cc | string \| string[] | No | CC recipients |
| bcc | string \| string[] | No | BCC recipients |
| replyTo | string | No | Reply-to email address |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails/receiving/12345/forward \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "colleague@example.com",
  "from": "you@yourdomain.com",
  "subject": "Fwd: Important Message",
  "html": "<p>FYI - see below.</p><hr><p>Original message content...</p>"
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
| 200 | Email forwarded successfully |
| 429 | Rate limit exceeded |
| 500 | Server error or missing required fields |
