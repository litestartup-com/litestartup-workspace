# Copy Template

> Create a copy of an existing template.

**Endpoint**: `POST https://api.litestartup.com/client/v2/templates/copy/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Template ID to copy |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/templates/copy/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Template copied successfully",
  "data": {
    "id": 124,
    "name": "Welcome Email (Copy)"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Template copied |
| 401 | Unauthorized |
| 404 | Template not found |
| 500 | Server error |
