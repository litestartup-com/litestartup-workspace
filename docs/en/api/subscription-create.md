# Create Subscription

> Create a new subscription (upgrade to Pro plan).

**Endpoint**: `POST https://api.litestartup.com/client/v2/subscription/create`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| plan_pay_type | string | Yes | Payment frequency: `monthly` or `yearly` |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/subscription/create \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "plan_pay_type": "monthly"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Subscription created successfully",
  "data": {
    "subscription_id": "I-XXXXXXXXXXXXX",
    "approve_link": "https://www.paypal.com/webapps/billing/subscriptions?ba_token=...",
    "status": "APPROVAL_PENDING"
  }
}
```

**Response (Error)**

```json
{
  "code": 400,
  "message": "Invalid plan type",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Subscription created, redirect user to approve_link |
| 400 | Invalid plan type |
| 401 | Unauthorized |
| 500 | Server error |

**Notes**

- After creating the subscription, redirect the user to `approve_link` to complete payment via PayPal.
- Monthly: $20/month, Yearly: $192/year (save $48).
