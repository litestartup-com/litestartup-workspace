# Search Contacts

> Search contacts by keyword.

**Endpoint**: `GET https://api.litestartup.com/client/v2/contacts/search`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| q | string | Yes | Search keyword (email, name, company) |
| limit | integer | No | Max results (default: 20) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/contacts/search?q=john&limit=10" \
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
        "company": "Acme Inc"
      }
    ],
    "total": 1
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Search completed |
| 401 | Unauthorized |
| 500 | Server error |
