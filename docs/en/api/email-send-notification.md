# Send Notification Email

> Send a notification email using your API key. Requires the `notification` scope.

**Endpoint**: `POST https://api.litestartup.com/client/v2/emails/notification`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| to | string | No | Recipient email address. Defaults to the API key's configured notification email, or the user's registration email |
| from | string | No | Sender email address. Defaults to the API key's configured notification email, or the system-assigned email (e.g. `xxx@litestartup.net`) |
| from_name | string | No | Sender display name. Defaults to the local part of the from email address |
| to_name | string | No | Recipient display name. Defaults to the local part of the to email address |
| subject | string | Yes | Notification subject line |
| content | string | Yes | HTML email body |

**Scope Requirement**

This endpoint requires the API key to have the `notification` scope (or `all` scope). You can configure the scope and allowed from/to emails in [Settings > Keys](https://app.litestartup.com/settings/keys).

When the `notification` scope is configured with specific from/to email whitelists:
- The `from` parameter must match one of the allowed sender emails (only checked when explicitly provided)
- The `to` parameter must match one of the allowed recipient emails (only checked when explicitly provided)
- If omitted, the system uses the default email which is always allowed

**Example 1: Send with defaults (minimal)**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails/notification \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "subject": "Server Alert",
  "content": "<p>CPU usage exceeded 90% on production server.</p>"
}'
```

**Example 2: Send with custom from/to**

```bash
curl -X POST https://api.litestartup.com/client/v2/emails/notification \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "from": "alerts@yourdomain.com",
  "from_name": "System Alerts",
  "to": "admin@yourdomain.com",
  "to_name": "Admin",
  "subject": "Deployment Complete",
  "content": "<h1>Deployment Successful</h1><p>Version 2.1.0 has been deployed to production.</p>"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "messageId": "xxxxxxxxxxxxxxxx"
  }
}
```

**Response (Error)**

```json
{
  "code": 500,
  "message": "Subject is required",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Notification sent successfully |
| 400 | Invalid request parameters (missing subject/content, invalid email format, no sender/recipient available) |
| 401 | Unauthorized - Invalid or missing API key |
| 403 | Forbidden - API key lacks `notification` scope, or from/to email not in whitelist, or from email domain not allowed |
| 429 | Rate limit exceeded (monthly or daily email usage limit) |
| 500 | Internal server error |

**Rate Limits**

- Consumes regular email quota (monthly and daily) based on your subscription plan
- When limits are exceeded, the API returns HTTP 429 with message `"Monthly email usage exceeded the limit"` or `"Daily email usage exceeded the limit"`

**Notes**

- This endpoint is designed for server-to-server notification use cases (e.g. alerts, deployment notifications, monitoring)
- CORS is not supported — do not call this endpoint from browser-side code
- Both `from` and `to` are optional; the system resolves defaults from the API key configuration and user account
- The `content` field accepts HTML; a plain text version is automatically generated
