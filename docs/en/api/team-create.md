# Create Team

> Create a new team.

**Endpoint**: `POST https://api.litestartup.com/client/v2/team/create`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Team name |
| slug | string | No | Team slug (URL-friendly identifier) |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/team/create \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "My Team",
  "slug": "my-team"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Team created successfully",
  "data": {
    "id": 123,
    "name": "My Team",
    "slug": "my-team"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Team created |
| 400 | Invalid team name or slug already exists |
| 401 | Unauthorized |
| 500 | Server error |
