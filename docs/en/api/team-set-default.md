# Set Default Team

> Set a team as the default team for the user.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/team/set-default`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| team_id | integer | Yes | Team ID to set as default |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/team/set-default \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "team_id": 123
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Default team updated",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Default team set |
| 400 | Invalid team ID |
| 401 | Unauthorized |
| 403 | Not a member of this team |
| 500 | Server error |
