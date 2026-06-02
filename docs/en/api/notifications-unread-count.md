# Get Unread Count

> Get the count of unread notifications.

**Endpoint**: `GET https://api.litestartup.com/client/v2/notifications/unread-count`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/notifications/unread-count \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "unread_count": 5
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Count retrieved |
| 401 | Unauthorized |
| 500 | Server error |
