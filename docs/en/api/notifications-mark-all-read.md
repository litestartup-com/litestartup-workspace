# Mark All Notifications as Read

> Mark all notifications as read.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/notifications/read-all`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/notifications/read-all \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "All notifications marked as read",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | All marked as read |
| 401 | Unauthorized |
| 500 | Server error |
