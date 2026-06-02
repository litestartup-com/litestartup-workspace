# Downgrade Subscription

> Downgrade to the Free plan.

**Endpoint**: `POST https://api.litestartup.com/client/v2/subscription/downgrade`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/subscription/downgrade \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Subscription downgraded successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Downgraded successfully |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- Downgrading will take effect at the end of the current billing period.
- You will lose access to Pro features after the downgrade.
