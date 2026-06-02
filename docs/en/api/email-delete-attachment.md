# Delete Attachment

> Delete a specific attachment from an inbound email.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/emails/receiving/{id}/attachment/{attachmentId}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID |
| attachmentId | integer | Yes | The attachment ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/emails/receiving/12345/attachment/1 \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": []
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
| 200 | Attachment deleted successfully |
| 403 | Access denied |
| 404 | Attachment not found |
| 500 | Server error during deletion |

**Notes**

- Deleting an attachment is permanent and cannot be undone.
- The attachment file will be removed from storage (S3 or local).
