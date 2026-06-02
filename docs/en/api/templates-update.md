# Update Template

> Update an existing email template.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/templates/update/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Template ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | No | Template name |
| content | string | No | HTML template content |
| description | string | No | Template description |
| category | string | No | Template category |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/templates/update/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "Updated Welcome Email",
  "content": "<h1>Welcome {{name}}!</h1><p>We are excited to have you.</p>"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Template updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Template updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Template not found |
| 500 | Server error |
