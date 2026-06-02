# Delete Template

> Delete an email template.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/templates/delete/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Template ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/templates/delete/123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Template deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Template deleted |
| 401 | Unauthorized |
| 404 | Template not found |
| 500 | Server error |
