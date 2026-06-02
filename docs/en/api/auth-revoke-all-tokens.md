# Revoke All Tokens

> Revoke all tokens for the authenticated user (logout from all devices).

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/revoke-all`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/revoke-all \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "All tokens revoked successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | All tokens revoked |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- This will log out the user from all devices and sessions.
- The current token will also be invalidated.
