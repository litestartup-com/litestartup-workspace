# Update Domain Email

> Update a domain email address.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/domain-emails/{emailId}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| emailId | integer | Yes | Email address ID |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| display_name | string | No | Display name for the email |
| is_default | boolean | No | Set as default email for the domain |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/domain-emails/456 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "display_name": "Support Team",
  "is_default": true
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Email address updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Email not found |
| 500 | Server error |
