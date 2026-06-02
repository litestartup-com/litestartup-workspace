# Mark Notification as Read

> Mark a specific notification as read.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/notifications/{id}/read`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Notification ID |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/notifications/123/read \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Notification marked as read",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Marked as read |
| 401 | Unauthorized |
| 404 | Notification not found |
| 500 | Server error |
