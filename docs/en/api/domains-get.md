# Get Domain Detail

> Get single domain detail by slug.

**Endpoint**: `GET https://api.litestartup.com/client/v2/domains/{slug}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| slug | string | Yes | Domain slug |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/domains/domain-abc123" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": 12345,
    "domain": "mail.yourdomain.com",
    "domain_slug": "domain-abc123",
    "subdomain": "mail",
    "root_domain": "yourdomain.com",
    "status": "verified",
    "selector": "litestartup",
    "dns_record": {
      "mx": {...},
      "spf": {...},
      "dkim": {...},
      "dmarc": {...}
    },
    "created_at": "2026-01-30 10:00:00",
    "verified_at": "2026-01-30 12:00:00"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Domain slug required |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 404 | Domain not found |
| 500 | Server error |
