# Delete Contact

> Delete a contact.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/contacts/delete`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Contact ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/contacts/delete \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "id": 12345
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Contact deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Contact deleted |
| 401 | Unauthorized |
| 404 | Contact not found |
| 500 | Server error |
