# Update Team Settings

> Update team settings.

**Endpoint**: `PUT https://api.litestartup.com/client/v2/settings/update-team`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | No | Team name |
| logo | string | No | Team logo URL |
| timezone | string | No | Team timezone |

**Example**

```bash
curl -X PUT https://api.litestartup.com/client/v2/settings/update-team \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "My Company",
  "timezone": "America/New_York"
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Team settings updated",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Settings updated |
| 400 | Invalid data |
| 401 | Unauthorized |
| 500 | Server error |
