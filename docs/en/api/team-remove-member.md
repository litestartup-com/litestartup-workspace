# Remove Team Member

> Remove a member from the team.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/team/member/{userId}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| userId | integer | Yes | User ID of the member to remove |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/team/member/456 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Member removed successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Member removed |
| 401 | Unauthorized |
| 403 | Insufficient permissions |
| 404 | Member not found |
| 500 | Server error |
