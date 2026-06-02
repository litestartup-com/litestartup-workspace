# Download Attachment

> Download a specific attachment from an inbound email.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/receiving/{id}/attachment/{attachmentId}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID |
| attachmentId | integer | Yes | The attachment ID |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/emails/receiving/12345/attachment/1 \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success - S3 Storage)**

Returns a pre-signed URL for downloading the file:

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "download_url": "https://s3.amazonaws.com/bucket/path/to/file?signature=...",
    "file_name": "document.pdf",
    "file_size": 102400,
    "mime_type": "application/pdf"
  }
}
```

**Response (Success - Local Storage)**

Returns the file directly as a binary stream with appropriate headers:

```
Content-Type: application/pdf
Content-Disposition: attachment; filename="document.pdf"
Content-Length: 102400
```

**Response (Error)**

```json
{
  "code": 404,
  "message": "Attachment not found",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Attachment retrieved successfully |
| 403 | Access denied (attachment belongs to another team) |
| 404 | Attachment or file not found |
| 500 | Server error during download |

**Notes**

- Pre-signed URLs (for S3 storage) expire after 5 minutes.
- For large files, consider using the pre-signed URL approach to reduce server load.
