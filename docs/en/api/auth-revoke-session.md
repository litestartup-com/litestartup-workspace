# Revoke Session

> Revoke a specific session by ID.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/auth/sessions/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Session ID to revoke |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/auth/sessions/2 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Session revoked successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Session revoked |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
