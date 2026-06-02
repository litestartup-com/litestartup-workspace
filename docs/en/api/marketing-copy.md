# Copy Campaign

> Create a copy of an existing campaign.

**Endpoint**: `POST https://api.litestartup.com/client/v2/marketing/copy/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Campaign ID to copy |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/marketing/copy/12345 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Campaign copied successfully",
  "data": {
    "id": 12346,
    "name": "Welcome Campaign (Copy)"
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Campaign copied |
| 401 | Unauthorized |
| 404 | Campaign not found |
| 500 | Server error |
