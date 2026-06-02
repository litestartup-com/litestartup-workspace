# Create Template

> Create a new email template.

**Endpoint**: `POST https://api.litestartup.com/client/v2/templates/create`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Template name |
| content | string | Yes | HTML template content |
| description | string | No | Template description |
| category | string | No | Template category |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/templates/create \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "Welcome Email",
  "content": "<h1>Welcome {{name}}!</h1><p>Thank you for joining us.</p>",
  "description": "Welcome email for new subscribers"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Template created successfully",
  "data": {
    "id": 123,
    "string_id": "welcome-email-abc123",
    "name": "Welcome Email"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Template created |
| 400 | Invalid data |
| 401 | Unauthorized |
| 500 | Server error |

**Template Variables**

Use `{{variable_name}}` syntax for dynamic content:
- `{{name}}` - Contact name
- `{{email}}` - Contact email
- `{{company}}` - Contact company
- `{{UNSUBSCRIBE}}` - Unsubscribe link (required for marketing emails)
