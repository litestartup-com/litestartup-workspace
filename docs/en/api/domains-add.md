# Add Domain

> Add a new domain for email sending.

**Endpoint**: `POST https://api.litestartup.com/client/v2/domains/add`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domain | string | Yes | Domain name (e.g., `example.com`) |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/domains/add \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "domain": "example.com"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Domain added successfully",
  "data": {
    "id": 123,
    "domain": "example.com",
    "slug": "example-com",
    "status": "pending",
    "dns_records": {
      "spf": {
        "type": "TXT",
        "name": "@",
        "value": "v=spf1 include:_spf.litestartup.com ~all"
      },
      "dkim": {
        "type": "CNAME",
        "name": "litestartup._domainkey",
        "value": "dkim.litestartup.com"
      },
      "dmarc": {
        "type": "TXT",
        "name": "_dmarc",
        "value": "v=DMARC1; p=none; rua=mailto:dmarc@litestartup.com"
      }
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Domain added |
| 400 | Invalid domain or already exists |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- After adding a domain, you need to configure DNS records and verify the domain.
