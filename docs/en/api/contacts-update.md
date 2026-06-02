# Update Contact

> Update an existing contact.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/contacts/update`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Contact ID |
| email | string | No | Contact email address |
| name | string | No | Contact name |
| first_name | string | No | Contact first name |
| last_name | string | No | Contact last name |
| phone | string | No | Contact phone number |
| company | string | No | Contact company |
| tags | string[] | No | Array of tag IDs |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/contacts/update \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "id": 12345,
  "name": "John Smith",
  "company": "New Company"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Contact updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Contact updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Contact not found |
| 500 | Server error |
