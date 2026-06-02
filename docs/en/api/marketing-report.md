# Get Campaign Report

> Get marketing campaign report and statistics.

**Endpoint**: `GET https://api.litestartup.com/client/v2/marketing/{id}/report`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Campaign ID |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/marketing/12345/report" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "campaign": {
      "id": 12345,
      "name": "Welcome Campaign",
      "subject": "Welcome to our newsletter!",
      "status": "sent",
      "total_recipients": 1000
    },
    "stats": {
      "total_recipients": 1000,
      "delivered": 980,
      "opens": 300,
      "clicks": 100,
      "unsubscribes": 5,
      "bounces": 20,
      "open_rate": 30.6,
      "click_rate": 10.2,
      "unsubscribe_rate": 0.5,
      "bounce_rate": 2.0
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Campaign ID required |
| 401 | Unauthorized |
| 403 | Permission denied |
| 404 | Campaign not found |
| 500 | Server error |
