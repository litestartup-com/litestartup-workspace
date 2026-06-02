# Get Usage Data

> Get plan usage statistics.

**Endpoint**: `GET https://api.litestartup.com/client/v2/settings/usage`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/settings/usage" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "plan": {
      "id": 1,
      "name": "Pro",
      "type": "pro",
      "status": "active",
      "expires_at": "2027-01-30 00:00:00"
    },
    "plan_usage": [
      {
        "feature": "team.domains_limit",
        "quota_limit": 10,
        "usage_count": 3
      },
      {
        "feature": "team.emails_per_month",
        "quota_limit": 10000,
        "usage_count": 2500
      },
      {
        "feature": "team.contacts_limit",
        "quota_limit": 5000,
        "usage_count": 1200
      }
    ]
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
