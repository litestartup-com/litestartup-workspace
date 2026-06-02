# Verify Domain

> Submit domain for DNS verification.

**Endpoint**: `POST https://api.litestartup.com/client/v2/domain/submit-domain-verify`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domain_slug | string | Yes | Domain slug identifier |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/domain/submit-domain-verify \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "domain_slug": "example-com"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Domain verification started",
  "data": {
    "status": "verifying"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Verification started |
| 400 | Invalid domain slug |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |
