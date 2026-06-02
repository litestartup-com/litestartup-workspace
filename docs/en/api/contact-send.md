# Send Contact Message

> Send a contact form message.

**Endpoint**: `POST https://api.litestartup.com/client/v2/contact/send`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Sender's name |
| email | string | Yes | Sender's email address |
| subject | string | Yes | Message subject |
| message | string | Yes | Message content |

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/contact/send \
     -H 'Content-Type: application/json' \
     -d '{
  "name": "John Doe",
  "email": "john@example.com",
  "subject": "Question about pricing",
  "message": "I would like to know more about your pricing plans."
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Message sent successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Message sent |
| 400 | Missing required fields |
| 500 | Server error |
