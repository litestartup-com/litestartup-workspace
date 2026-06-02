# Create Tag

> Create a new tag for contacts.

**Endpoint**: `POST https://api.litestartup.com/client/v2/tags/create`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Tag name |
| color | string | No | Tag color (hex code, e.g., `#FF5733`) |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/tags/create \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "VIP Customers",
  "color": "#FF5733"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Tag created successfully",
  "data": {
    "id": 123,
    "name": "VIP Customers",
    "color": "#FF5733"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Tag created |
| 400 | Invalid name or tag already exists |
| 401 | Unauthorized |
| 500 | Server error |
