# Verify Auth Code

> Verify the authentication code sent to user's email.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/verify-auth-code`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | User email address |
| code | string | Yes | The auth code received via email |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/verify-auth-code \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "user@example.com",
  "code": "123456"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Code verified successfully",
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
}
```

**Response (Error)**

```json
{
  "code": 401,
  "message": "Invalid or expired code",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Code verified successfully |
| 400 | Missing required fields |
| 401 | Invalid or expired code |
| 500 | Server error |
