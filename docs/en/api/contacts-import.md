# Import Contacts

> Import contacts from a CSV file.

**Endpoint**: `POST https://api.litestartup.com/client/v2/contacts/import`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |
| Content-Type | Yes | `multipart/form-data` |

**Form Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| file | file | Yes | CSV file containing contacts |
| tags | string | No | Comma-separated tag IDs to assign |
| skip_duplicates | boolean | No | Skip duplicate emails (default: true) |

**CSV Format**

```csv
email,name,first_name,last_name,phone,company
john@example.com,John Doe,John,Doe,+1234567890,Acme Inc
jane@example.com,Jane Smith,Jane,Smith,+0987654321,Tech Corp
```

**Example**

```bash
curl -X POST https://api.litestartup.com/client/v2/contacts/import \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -F 'file=@contacts.csv' \
     -F 'tags=tag1,tag2'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Import completed",
  "data": {
    "imported": 150,
    "skipped": 5,
    "failed": 2
  }
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Import completed |
| 400 | Invalid file format |
| 401 | Unauthorized |
| 500 | Server error |
