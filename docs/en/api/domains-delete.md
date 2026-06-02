# Delete Domain

> Delete a domain.

**Endpoint**: `DELETE https://api.litestartup.com/client/v2/domain/{domainSlug}`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer {access_token}` |

**Path Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| domainSlug | string | Yes | Domain slug identifier |

**Example**

```bash
curl -X DELETE https://api.litestartup.com/client/v2/domain/example-com \
     -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "Domain deleted successfully",
  "data": []
}
```

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | Domain deleted |
| 401 | Unauthorized |
| 404 | Domain not found |
| 500 | Server error |

**Notes**

- Deleting a domain will also remove all associated email addresses.
- This action cannot be undone.
