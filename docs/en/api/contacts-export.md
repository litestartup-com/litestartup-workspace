# Export Contacts

> Export contacts to a CSV file.

**Endpoint**: `GET https://api.litestartup.com/client/v2/contacts/export`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Query Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| tags | string | No | Filter by tag IDs (comma-separated) |
| format | string | No | Export format: `csv` (default) |

**Example**

```bash
curl -X GET "https://api.litestartup.com/client/v2/contacts/export?tags=tag1,tag2" \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' \
     -o contacts.csv
```

**Response (Success)**

Returns a CSV file download with headers:

```
Content-Type: text/csv
Content-Disposition: attachment; filename="contacts.csv"
```

**CSV Content**

```csv
email,name,first_name,last_name,phone,company,tags,created_at
john@example.com,John Doe,John,Doe,+1234567890,Acme Inc,"tag1,tag2",2026-01-01
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Export successful |
| 401 | Unauthorized |
| 500 | Server error |
