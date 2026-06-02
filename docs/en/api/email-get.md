# Get Email

> Retrieve details of a specific outbound email by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The email ID or message ID |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/emails/abc123def456 \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "from_email": "sender@yourdomain.com",
    "to_email": "recipient@example.com",
    "cc_email": "",
    "bcc_email": "",
    "subject": "Welcome!",
    "date": "Jan 23, 2026, 10:30 AM",
    "message_id": "abc123def456@yourdomain.com",
    "html_content": "<h1>Hello</h1><p>Welcome to litestartup.</p>",
    "attachments": []
  }
}
```

**Response (Error)**

```json
{
  "code": 500,
  "message": "error",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email retrieved successfully |
| 500 | Email not found or server error |
