# Get Dashboard Stats

> Get dashboard/home page statistics.

**Endpoint**: `GET https://api.litestartup.com/client/v2/home/stats`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/home/stats" \
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
      "status": "active"
    },
    "plan_usage": [
      {
        "feature": "team.emails_per_month",
        "quota_limit": 10000,
        "usage_count": 2500
      }
    ],
    "stats": {
      "emails_sent": 100,
      "emails_received": 50,
      "total_contacts": 200,
      "active_campaigns": 3
    }
  }
}
```

**Stats Description**

| Field | Description |
|-------|-------------|
| emails_sent | Emails sent in the last 30 days |
| emails_received | Emails received in the last 30 days |
| total_contacts | Total subscribed contacts |
| active_campaigns | Campaigns in ready/scheduled/sending status |

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 500 | Server error |
