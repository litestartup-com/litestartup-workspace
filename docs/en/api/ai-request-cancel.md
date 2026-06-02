# Cancel AI Request

> Cancel a pending AI generation request.

**Endpoint**: `POST https://api.litestartup.com/client/v2/ai/request/{id}/cancel`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | Request ID to cancel |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/request/req_abc123/cancel \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Request cancelled",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Request cancelled |
| 400 | Request already completed |
| 401 | Unauthorized |
| 404 | Request not found |
| 500 | Server error |
