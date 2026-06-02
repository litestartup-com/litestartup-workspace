# Delete Campaign

> Delete a marketing campaign.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/marketing/delete/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | integer | Yes | Campaign ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/marketing/delete/12345 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Campaign deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Campaign deleted |
| 401 | Unauthorized |
| 404 | Campaign not found |
| 500 | Server error |
