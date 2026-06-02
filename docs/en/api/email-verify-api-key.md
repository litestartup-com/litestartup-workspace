# Verify API Key

> Verify that your API key is valid and retrieve account information.

**Endpoint**: `GET https://api.litestartup.com/client/v2/verify`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/verify \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "ok",
  "data": {
    "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  }
}
```

**Response (Error - Invalid API Key)**

```json
{
  "code": 401,
  "message": "",
  "data": {
    "error": "Invalid API key"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | API key is valid |
| 401 | Invalid or missing API key |
| 500 | Server error during verification |
