# Delete Email

> Delete a specific outbound email by ID.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/emails/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The email ID or message ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/emails/abc123def456 \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Success",
  "data": []
}
```

**Response (Error)**

```json
{
  "code": 500,
  "message": "error",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Email deleted successfully |
| 500 | Email not found or deletion failed |
