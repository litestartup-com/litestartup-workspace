# Get Token (JWT)

> Obtain a JWT access token for API authentication.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/token`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | User email address |
| password | string | Yes | User password |
| grant_type | string | No | Token grant type (default: `password`) |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/token \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "user@example.com",
  "password": "your_password"
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
    "expires_in": 1800
  }
}
```

**Response (Error)**

```json
{
  "code": 401,
  "message": "Invalid credentials",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Token generated successfully |
| 400 | Missing required fields |
| 401 | Invalid credentials |
| 500 | Server error |

**Notes**

- Access tokens expire after the time specified in `expires_in` (seconds).
- Use the refresh token to obtain a new access token without re-authenticating.
