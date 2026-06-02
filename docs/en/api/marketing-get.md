# Get Campaign Detail

> Get single marketing campaign detail by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/marketing/{id}`

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
curl -X GET "https://api.litestartup.com/client/v2/marketing/12345" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "name": "Welcome Campaign",
    "subject": "Welcome to our newsletter!",
    "from_email": "newsletter@yourdomain.com",
    "from_name": "Your Company",
    "content": "<h1>Welcome!</h1><p>Thank you for subscribing.</p>",
    "status": "sent",
    "total_recipients": 1000,
    "tag_id": 1,
    "template_id": null,
    "scheduled_at": null,
    "sent_at": "2026-01-30 12:00:00",
    "created_at": "2026-01-30 10:00:00",
    "updated_at": "2026-01-30 12:00:00"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Campaign ID required |
| 401 | Unauthorized |
| 404 | Campaign not found |
| 500 | Server error |
