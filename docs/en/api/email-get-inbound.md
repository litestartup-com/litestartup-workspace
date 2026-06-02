# Get Inbound Email

> Retrieve details of a specific inbound (received) email by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/receiving/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/emails/receiving/12345 \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "from_email": "sender@example.com",
    "from_name": "John Doe",
    "to_email": "you@yourdomain.com",
    "cc_email": "",
    "bcc_email": "",
    "subject": "Hello!",
    "content": "Plain text content...",
    "html_content": "<p>HTML content...</p>",
    "date": "Jan 23, 2026, 10:30 AM",
    "status": "read",
    "attachments": [
      {
        "id": 1,
        "file_name": "document.pdf",
        "file_size": 102400,
        "mime_type": "application/pdf"
      }
    ]
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

**Notes**

- Reading an email automatically marks it as "read" if it was previously "unread".

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email retrieved successfully |
| 500 | Email not found or server error |
