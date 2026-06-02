# Get Current User

> Get the authenticated user's information.

**Endpoint**: `GET https://api.litestartup.com/client/v2/auth/oauth-config`

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/auth/oauth-config     
```

**Response (Success)**

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "googleClientId": "111",
        "githubClientId": "123",
        "googleCallback": "adsf",
        "githubCallback": "dddd"
    }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | OK |
| 401 | Unauthorized |
| 500 | Server error |
