# Create Campaign

> Create a new email marketing campaign.

**Endpoint**: `POST https://api.litestartup.com/client/v2/marketing/create`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Campaign name |
| subject | string | Yes | Email subject line |
| from_email | string | Yes | Sender email address |
| from_name | string | No | Sender name |
| content | string | Yes | HTML email content |
| template_id | integer | No | Template ID to use |
| tags | string[] | No | Tag IDs to target contacts |
| status | string | No | `draft`, `scheduled`, `sending` |
| scheduled_at | string | No | ISO 8601 datetime for scheduled send |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/marketing/create \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "Welcome Campaign",
  "subject": "Welcome to our newsletter!",
  "from_email": "newsletter@yourdomain.com",
  "from_name": "Your Company",
  "content": "<h1>Welcome!</h1><p>Thank you for subscribing.</p>",
  "tags": ["subscribers"],
  "status": "draft"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Campaign created successfully",
  "data": {
    "id": 12345,
    "name": "Welcome Campaign",
    "status": "draft"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Campaign created |
| 400 | Invalid data |
| 401 | Unauthorized |
| 500 | Server error |
