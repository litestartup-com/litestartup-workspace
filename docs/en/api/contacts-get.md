# Get Contact

> Get a specific contact by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/contacts/get`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Contact ID |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/contacts/get?id=12345" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "email": "contact@example.com",
    "name": "John Doe",
    "first_name": "John",
    "last_name": "Doe",
    "phone": "+1234567890",
    "company": "Acme Inc",
    "tags": ["tag1", "tag2"],
    "created_at": "2026-01-01T00:00:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Contact retrieved |
| 401 | Unauthorized |
| 404 | Contact not found |
| 500 | Server error |
