# Add Contact

> Add a new contact to your contact list.

**Endpoint**: `POST https://api.litestartup.com/client/v2/contacts/add`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | Contact email address |
| name | string | No | Contact name |
| first_name | string | No | Contact first name |
| last_name | string | No | Contact last name |
| phone | string | No | Contact phone number |
| company | string | No | Contact company |
| tags | string[] | No | Array of tag IDs to assign |
| custom_fields | object | No | Custom field values |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/contacts/add \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "contact@example.com",
  "name": "John Doe",
  "company": "Acme Inc",
  "tags": ["tag1", "tag2"]
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Contact added successfully",
  "data": {
    "id": 12345,
    "email": "contact@example.com",
    "name": "John Doe"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Contact added |
| 400 | Invalid email or contact already exists |
| 401 | Unauthorized |
| 500 | Server error |
