# Get Template Detail

> Get single email template detail by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/templates/{id}`

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
curl -X GET "https://api.litestartup.com/client/v2/templates/12345" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "name": "Welcome Template",
    "category": "onboarding",
    "content": "<html>...</html>",
    "thumbnail": "https://...",
    "created_at": "2026-01-30 10:00:00",
    "updated_at": "2026-01-30 12:00:00"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Template ID required |
| 401 | Unauthorized |
| 404 | Template not found |
| 500 | Server error |
