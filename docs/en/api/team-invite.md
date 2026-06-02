# Invite Team Member

> Invite a new member to the team.

**Endpoint**: `POST https://api.litestartup.com/client/v2/team/invite`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | Email address of the person to invite |
| role | string | No | Role to assign: `admin`, `member` (default: `member`) |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/team/invite \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "newmember@example.com",
  "role": "member"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Invitation sent successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Invitation sent |
| 400 | Invalid email or user already in team |
| 401 | Unauthorized |
| 403 | Insufficient permissions |
| 500 | Server error |
