# Update Profile

> Update user profile information.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/profile/update/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | User ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | No | User display name |
| avatar | string | No | Avatar URL |
| phone | string | No | Phone number |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/profile/update/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "John Smith",
  "phone": "+1234567890"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Profile updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Profile updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 403 | Cannot update other user's profile |
| 500 | Server error |
