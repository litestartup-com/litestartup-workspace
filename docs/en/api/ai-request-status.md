# Get AI Request Status

> Get the status of an AI generation request.

**Endpoint**: `GET https://api.litestartup.com/client/v2/ai/request/{id}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | Request ID from the generation request |

**Example**

```bash
curl -X GET https://api.litestartup.com/client/v2/ai/request/req_abc123 \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Pending)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": "req_abc123",
    "status": "processing",
    "progress": 50
  }
}
```

**Response (Completed)**

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "id": "req_abc123",
    "status": "completed",
    "result": {
      "html": "<html>...</html>",
      "subject": "Welcome to Our Platform!"
    }
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Status retrieved |
| 401 | Unauthorized |
| 404 | Request not found |
| 500 | Server error |
