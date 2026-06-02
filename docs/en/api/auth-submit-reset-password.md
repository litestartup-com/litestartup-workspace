# Submit Reset Password

> Submit a new password using the reset token.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/submit-reset-password`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| token | string | Yes | Password reset token from email link |
| password | string | Yes | New password |
| password_confirmation | string | Yes | Confirm new password |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/submit-reset-password \
     -H 'Content-Type: application/json' \
     -d '{
  "token": "reset_token_from_email",
  "password": "new_secure_password",
  "password_confirmation": "new_secure_password"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Password reset successfully",
  "data": []
}
```

**Response (Error)**

```json
{
  "code": 400,
  "message": "Invalid or expired token",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Password reset successfully |
| 400 | Invalid token or passwords don't match |
| 401 | Token expired |
| 500 | Server error |
