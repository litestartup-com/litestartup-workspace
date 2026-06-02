# Refresh Token

> Refresh an expired access token using a refresh token.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/refresh`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| refresh_token | string | Yes | The refresh token obtained during login |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/refresh \
     -H 'Content-Type: application/json' \
     -d '{
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "token_type": "Bearer",
    "expires_in": 3600
  }
}
```

**Response (Error)**

```json
{
  "code": 401,
  "message": "Invalid or expired refresh token",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Token refreshed successfully |
| 400 | Missing refresh token |
| 401 | Invalid or expired refresh token |
| 500 | Server error |
