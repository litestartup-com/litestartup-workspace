# Update Campaign

> Update an existing marketing campaign.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/marketing/update/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Campaign ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | No | Campaign name |
| subject | string | No | Email subject line |
| from_email | string | No | Sender email address |
| from_name | string | No | Sender name |
| content | string | No | HTML email content |
| tags | string[] | No | Tag IDs to target contacts |
| status | string | No | `draft`, `scheduled`, `sending` |
| scheduled_at | string | No | ISO 8601 datetime for scheduled send |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/marketing/update/12345 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "subject": "Updated: Welcome to our newsletter!",
  "status": "scheduled",
  "scheduled_at": "2026-01-25T10:00:00Z"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Campaign updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Campaign updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Campaign not found |
| 500 | Server error |
