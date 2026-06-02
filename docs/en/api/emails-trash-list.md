# List Trash Emails

> Get list of trash emails with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/trash`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Items per page (default: 20, max: 100) |
| search | string | No | Search keyword |
| label | string | No | Filter by label |
| type | string | No | Filter by source type |
| domainEmail | string | No | Filter by domain email (default: all) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/emails/trash?page=1&limit=20" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "emails": [
      {
        "id": 12345,
        "from_email": "sender@example.com",
        "subject": "Deleted Email",
        "received_at": "2026-01-30 10:00:00",
        "status": "trash"
      }
    ],
    "total": 5,
    "page": 1,
    "limit": 20,
    "folder": "trash",
    "counts": {
      "inbox": 50,
      "draft": 5
    },
    "domain_emails": [...]
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 500 | Server error |
