# Update Tag

> Update an existing tag.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/tags/update`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Tag ID |
| name | string | No | New tag name |
| color | string | No | New tag color (hex code) |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/tags/update \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "id": 123,
  "name": "Premium Customers",
  "color": "#00FF00"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Tag updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Tag updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Tag not found |
| 500 | Server error |
