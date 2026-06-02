# Add Domain Email

> Add a new email address for a domain.

**Endpoint**: `POST https://api.litestartup.com/client/v2/domain-emails/add`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domain_id | integer | Yes | Domain ID |
| email_address | string | Yes | Email address (local part only, e.g., `info`) |
| display_name | string | No | Display name for the email |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/domain-emails/add \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "domain_id": 123,
  "email_address": "info",
  "display_name": "Info Team"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Email address added successfully",
  "data": {
    "id": 456,
    "email_address": "info@example.com",
    "display_name": "Info Team"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email added |
| 400 | Invalid email or already exists |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |
