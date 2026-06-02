# Configure Domain

> Update domain configuration settings.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/domain/config/{domainSlug}`

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
| tracking_enabled | boolean | No | Enable email tracking |
| custom_tracking_domain | string | No | Custom tracking domain |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/domain/config/example-com \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "tracking_enabled": true
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Domain configured successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Domain configured |
| 400 | Invalid configuration |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |
