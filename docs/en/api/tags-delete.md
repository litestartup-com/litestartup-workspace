# Delete Tag

> Delete a tag.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/tags/delete`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Tag ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/tags/delete \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "id": 123
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Tag deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Tag deleted |
| 401 | Unauthorized |
| 404 | Tag not found |
| 500 | Server error |

**Notes**

- Deleting a tag will remove it from all associated contacts.
