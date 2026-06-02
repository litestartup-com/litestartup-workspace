# Get Domain Email Detail

> Get single domain email detail by ID.

**Endpoint**: `GET https://api.litestartup.com/client/v2/domain-emails/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Domain email ID |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/domain-emails/12345" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "domain_id": 100,
    "email_address": "info@yourdomain.com",
    "email_name": "Info",
    "email_type": "shared",
    "user_id": null,
    "status": "active",
    "created_at": "2026-01-30 10:00:00",
    "updated_at": "2026-01-30 12:00:00"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Email ID required |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 404 | Domain email not found |
| 500 | Server error |
