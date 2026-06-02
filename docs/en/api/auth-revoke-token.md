# Revoke Token

> Revoke an access token to invalidate it.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/revoke`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| token | string | Yes | The access token to revoke |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/revoke \
     -H 'Content-Type: application/json' \
     -d '{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Token revoked successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Token revoked successfully |
| 400 | Missing token |
| 500 | Server error |
