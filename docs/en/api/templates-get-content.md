# Get Template Content

> Get the content of a specific template.

**Endpoint**: `GET https://api.litestartup.com/client/v2/templates/content/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Template ID |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/templates/content/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 123,
    "string_id": "welcome-email-abc123",
    "name": "Welcome Email",
    "content": "<h1>Welcome {{name}}!</h1><p>Thank you for joining us.</p>",
    "description": "Welcome email for new subscribers",
    "category": "onboarding",
    "created_at": "2026-01-01T00:00:00Z",
    "updated_at": "2026-01-15T10:30:00Z"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Template retrieved |
| 401 | Unauthorized |
| 404 | Template not found |
| 500 | Server error |
