# Get Analytics Data

> Get analytics and statistics data for the team.

**Endpoint**: `GET https://api.litestartup.com/client/v2/analytics`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| days | integer | No | Time range in days (default: 30, max: 365) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/analytics?days=30" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "stats": {
      "total_campaigns": 10,
      "completed_campaigns": 8,
      "emails_sent": 1000,
      "total_contacts": 500,
      "active_contacts": 450,
      "total_opens": 300,
      "total_clicks": 100,
      "total_unsubscribes": 5,
      "open_rate": 30.0,
      "click_rate": 10.0,
      "unsubscribe_rate": 0.5,
      "engagement_trend": [
        {
          "date": "2026-01-01",
          "sends": 100,
          "opens": 30,
          "clicks": 10,
          "unsubscribes": 1
        }
      ]
    },
    "days": 30,
    "start_date": "2025-12-31 00:00:00"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied |
| 500 | Server error |
