# Update Member Role

> Update a team member's role.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/team/member/{userId}/role`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| userId | integer | Yes | User ID of the member |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| role | string | Yes | New role: `admin` or `member` |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/team/member/456/role \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "role": "admin"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Role updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Role updated |
| 400 | Invalid role |
| 401 | Unauthorized |
| 403 | Insufficient permissions |
| 404 | Member not found |
| 500 | Server error |
