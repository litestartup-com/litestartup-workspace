# Delete Notification

> Delete a notification.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/notifications/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Notification ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/notifications/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Notification deleted",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Notification deleted |
| 401 | Unauthorized |
| 404 | Notification not found |
| 500 | Server error |
