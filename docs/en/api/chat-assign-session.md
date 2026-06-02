# Assign Chat Session

> Assign a chat session to a team member.

**Endpoint**: `POST https://api.litestartup.com/client/v2/chat/sessions/{id}/assign`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Session ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| user_id | integer | Yes | User ID to assign the session to |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/chat/sessions/123/assign \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "user_id": 456
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Session assigned",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Session assigned |
| 400 | Invalid user ID |
| 401 | Unauthorized |
| 404 | Session not found |
| 500 | Server error |
