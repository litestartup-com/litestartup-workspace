# List Attachments

> Retrieve a list of attachments for a specific inbound email.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/receiving/{id}/attachment`

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
curl -X GET https://api.litestartup.com/client/v2/emails/receiving/12345/attachment \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "attachments": [
      {
        "id": 1,
        "file_name": "document.pdf",
        "file_size": 102400,
        "mime_type": "application/pdf",
        "is_inline": false
      },
      {
        "id": 2,
        "file_name": "image.png",
        "file_size": 51200,
        "mime_type": "image/png",
        "is_inline": true
      }
    ]
  }
}
```

**Response Fields**

| Field | Type | Description |
|-------|------|-------------|
| id | integer | Attachment ID |
| file_name | string | Original file name |
| file_size | integer | File size in bytes |
| mime_type | string | MIME type of the file |
| is_inline | boolean | Whether the attachment is inline (embedded in email body) |

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Attachments retrieved successfully |
| 500 | Email not found or server error |
