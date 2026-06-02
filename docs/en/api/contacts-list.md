# List Contacts

> Get list of contacts with pagination and filtering.

**Endpoint**: `GET https://api.litestartup.com/client/v2/contacts/list`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Items per page (default: 20, max: 100) |
| search | string | No | Search keyword (email, name) |
| status | string | No | Filter by status (subscribed, unsubscribed) |
| tag | string | No | Filter by tag |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/contacts/list?page=1&limit=20&status=subscribed" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "contacts": [
      {
        "id": 12345,
        "email": "john@example.com",
        "name": "John Doe",
        "company": "Acme Inc",
        "status": "subscribed",
        "created_at": "2026-01-30 10:00:00"
      }
    ],
    "total": 500,
    "page": 1,
    "limit": 20,
    "tags": [
      {"id": 1, "name": "VIP"},
      {"id": 2, "name": "Newsletter"}
    ],
    "stats": {
      "total": 500,
      "subscribed": 450,
      "unsubscribed": 50
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied |
| 500 | Server error |
