# Request Auth Code

> Request an authentication code to be sent to user's email.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/request-auth-code`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | User email address to receive the auth code |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/request-auth-code \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "user@example.com"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Auth code sent successfully",
  "data": []
}
```

**Response (Error)**

```json
{
  "code": 400,
  "message": "Invalid email address",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Auth code sent successfully |
| 400 | Invalid email format |
| 429 | Too many requests (rate limited) |
| 500 | Server error |

**Notes**

- The auth code is valid for a limited time (typically 10 minutes).
- Rate limiting applies to prevent abuse.
