# Update Domain

> Update domain settings.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/domain/update/{domainSlug}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domainSlug | string | Yes | Domain slug identifier |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | No | Display name for the domain |
| is_default | boolean | No | Set as default sending domain |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/domain/update/example-com \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "is_default": true
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Domain updated successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Domain updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |
