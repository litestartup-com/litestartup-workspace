# Waitlist

> Add an email to the waitlist.

**Endpoint**: `POST https://api.litestartup.com/client/v2/waitlist`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | Email address to add to waitlist |
| name | string | No | User's name |
| source | string | No | Referral source |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/waitlist \
     -H 'Content-Type: application/json' \
     -d '{
  "email": "user@example.com",
  "name": "John Doe"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Successfully added to waitlist",
  "data": []
}
```

**Response (Error)**

```json
{
  "code": 400,
  "message": "Email already on waitlist",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Added to waitlist |
| 400 | Invalid email or already on waitlist |
| 500 | Server error |

**Notes**

- A verification email will be sent to the provided email address.
- CORS enabled for cross-origin requests.
