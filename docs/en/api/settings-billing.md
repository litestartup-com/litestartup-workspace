# Get Billing Data

> Get billing information and order history.

**Endpoint**: `GET https://api.litestartup.com/client/v2/settings/billing`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/settings/billing" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "plan": {
      "id": 1,
      "name": "Pro",
      "type": "pro",
      "status": "active",
      "price": 29.00,
      "billing_cycle": "monthly",
      "expires_at": "2027-01-30 00:00:00"
    },
    "orders": [
      {
        "id": 12345,
        "order_no": "ORD-2026-001",
        "amount": 29.00,
        "currency": "USD",
        "status": "completed",
        "payment_method": "paypal",
        "created_at": "2026-01-01 10:00:00"
      }
    ]
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Success |
| 401 | Unauthorized |
| 403 | Permission denied (owner/admin only) |
| 500 | Server error |
