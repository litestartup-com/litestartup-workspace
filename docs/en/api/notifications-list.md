# List Notifications

> Get recent notifications (latest 10).

**Endpoint**: `GET https://api.litestartup.com/client/v2/notifications`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/notifications \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "notifications": [
      {
        "id": 1,
        "type": "campaign",
        "title": "Campaign Sent",
        "message": "Your campaign 'Welcome Email' has been sent to 150 contacts.",
        "icon_type": "success",
        "action_url": "/marketing/report?id=123",
        "action_label": "View Report",
        "is_read": false,
        "created_at": "2026-01-23T10:00:00Z",
        "time_ago": "5 minutes ago"
      }
    ],
    "unread_count": 3
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Notifications retrieved |
| 401 | Unauthorized |
| 500 | Server error |
