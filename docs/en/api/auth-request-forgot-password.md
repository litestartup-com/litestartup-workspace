# Request Forgot Password

> Request a password reset link to be sent to user's email.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/request-forgot-password`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | User email address |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/request-forgot-password \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "user@example.com"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Password reset link sent",
  "data": []
}
```

**Response (Error)**

```json
{
  "code": 404,
  "message": "Email not found",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Reset link sent successfully |
| 400 | Invalid email format |
| 404 | Email not registered |
| 429 | Too many requests |
| 500 | Server error |
