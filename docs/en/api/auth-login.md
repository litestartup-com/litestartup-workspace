# Login

> Authenticate user with email and password.

**Endpoint**: `POST https://api.litestartup.com/client/v2/auth/login`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | User email address |
| password | string | Yes | User password |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/auth/login \
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
    "user": {
      "id": 12345,
      "email": "user@example.com",
      "name": "John Doe"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
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
| 200 | Login successful |
| 400 | Missing required fields |
| 401 | Invalid email or password |
| 500 | Server error |
