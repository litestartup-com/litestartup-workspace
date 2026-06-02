# List Draft Emails

> Get list of draft emails with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/emails/draft`

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
curl -X GET "https://api.litestartup.com/client/v2/emails/draft?page=1&limit=20" \
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
        "to_email": "recipient@example.com",
        "subject": "Draft Email",
        "created_at": "2026-01-30 10:00:00",
        "status": "draft"
      }
    ],
    "total": 10,
    "page": 1,
    "limit": 20,
    "folder": "draft",
    "counts": {
      "inbox": 50,
      "draft": 10
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
