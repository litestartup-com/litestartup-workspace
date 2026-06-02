# Domain Verify Polling

> Poll the status of domain verification.

**Endpoint**: `GET https://api.litestartup.com/client/v2/domain/domain-verify-polling`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domain_slug | string | Yes | Domain slug identifier |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/domain/domain-verify-polling?domain_slug=example-com" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "status": "verified",
    "spf_verified": true,
    "dkim_verified": true,
    "dmarc_verified": true
  }
}
```

**Response (Pending)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "status": "pending",
    "spf_verified": true,
    "dkim_verified": false,
    "dmarc_verified": false
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Status retrieved |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |
