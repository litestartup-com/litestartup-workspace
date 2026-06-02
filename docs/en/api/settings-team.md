# Get Team Data

> Get team information, members, and user's teams.

**Endpoint**: `GET https://api.litestartup.com/client/v2/settings/team`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/settings/team" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "team": {
      "id": 1,
      "name": "My Team",
      "slug": "team-abc123",
      "description": "Team description",
      "created_at": "2026-01-01 10:00:00"
    },
    "members": [
      {
        "id": 1,
        "email": "owner@example.com",
        "name": "John Doe",
        "role": "owner",
        "joined_at": "2026-01-01 10:00:00"
      },
      {
        "id": 2,
        "email": "admin@example.com",
        "name": "Jane Smith",
        "role": "admin",
        "joined_at": "2026-01-15 10:00:00"
      }
    ],
    "my_teams": [
      {
        "id": 1,
        "name": "My Team",
        "slug": "team-abc123",
        "role": "owner"
      }
    ],
    "current_team_id": 1,
    "current_user_id": 1,
    "plan_type": "pro"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 500 | Server error |
