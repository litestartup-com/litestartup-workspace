# Delete Inbound Email

> Delete a specific inbound (received) email by ID.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/emails/receiving/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token with your API key: `Bearer sk_live_xxxxxxxxxxxxx` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | The inbound email ID to delete |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/emails/receiving/12345 \
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
