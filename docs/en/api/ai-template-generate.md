# Generate AI Template

> Submit a request to generate an email template using AI.

**Endpoint**: `POST https://api.litestartup.com/client/v2/ai/template/generate`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| prompt | string | Yes | Description of the template to generate |
| style | string | No | Template style: `modern`, `minimal`, `corporate`, `creative`, `elegant` |
| colors | string | No | Color scheme: `blue`, `purple`, `green`, `orange`, `dark`, `light` |
| industry | string | No | Industry: `tech`, `ecommerce`, `saas`, `finance`, `healthcare`, etc. |
| goal | string | No | Campaign goal: `open-rate`, `click-rate`, `conversion-rate`, etc. |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/template/generate \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "prompt": "Create a welcome email for new SaaS subscribers",
  "style": "modern",
  "colors": "blue",
  "industry": "saas",
  "goal": "engagement"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Request submitted",
  "data": {
    "request_id": "req_abc123"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Request submitted |
| 400 | Invalid parameters |
| 401 | Unauthorized |
| 429 | AI usage limit exceeded |
| 500 | Server error |

**Notes**

- Use the `request_id` to poll for the generation status.
- Generation typically takes 10-30 seconds.
