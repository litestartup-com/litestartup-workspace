# Delete Domain Email

> Delete a domain email address.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/domain-emails/{emailId}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| emailId | integer | Yes | Email address ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/domain-emails/456 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Email address deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email deleted |
| 401 | Unauthorized |
| 404 | Email not found |
| 500 | Server error |
