---
title: API Reference
description: LiteStartup Client API v2 — RESTful API for email, marketing, contacts, and more.
---

# Litestartup API Documentation

> Client API v2 - RESTful API for email and marketing operations

## Base URL

```
https://api.litestartup.com/client/v2
```

## Authentication

API requests can be authenticated using:

1. **API Key** (for server-to-server):
```
Authorization: Bearer sk_live_xxxxxxxxxxxxx
```

### Verify API Key

```bash
curl -X GET https://api.litestartup.com/client/v2/verify \
  -H "Authorization: Bearer sk_live_xxxxxxxxxxxxx"
```

### Success Response

```json
{
  "uuid": "xxxxxxxxxxxxx"
}
```

---

## API Endpoints


### Emails List (Folders)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/inbox](emails-inbox-list.md) | List inbox emails |
| GET | [/emails/sent](emails-sent-list.md) | List sent emails |
| GET | [/emails/draft](emails-draft-list.md) | List draft emails |
| GET | [/emails/trash](emails-trash-list.md) | List trash emails |
| GET | [/emails/spam](emails-spam-list.md) | List spam emails |

### Outbound Emails (Sending)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/emails](email-send.md) | Send email |
| GET | [/emails](email-list.md) | List sent emails |
| GET | [/emails/{id}](email-get.md) | Get email details |
| DELETE | [/emails/{id}](email-delete.md) | Delete email |

### Inbound Emails (Receiving)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/receiving](email-list-inbound.md) | List received emails |
| GET | [/emails/receiving/{id}](email-get-inbound.md) | Get received email details |
| DELETE | [/emails/receiving/{id}](email-delete-inbound.md) | Delete received email |
| POST | [/emails/receiving/{id}/reply](email-reply.md) | Reply to email |
| POST | [/emails/receiving/{id}/forward](email-forward.md) | Forward email |

### Attachments

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/emails/receiving/{id}/attachment](email-list-attachments.md) | List attachments |
| GET | [/emails/receiving/{id}/attachment/{attachmentId}](email-download-attachment.md) | Download attachment |
| DELETE | [/emails/receiving/{id}/attachment/{attachmentId}](email-delete-attachment.md) | Delete attachment |

### Contacts

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/contacts/list](contacts-list.md) | List contacts|
| POST | [/contacts/add](contacts-add.md) | Add contact|
| GET | [/contacts/search](contacts-search.md) | Search contacts |
| GET | [/contacts/get](contacts-get.md) | Get contact |
| PUT | [/contacts/update](contacts-update.md) | Update contact |
| DELETE | [/contacts/delete](contacts-delete.md) | Delete contact |
| POST | [/contacts/import](contacts-import.md) | Import contacts |
| GET | [/contacts/export](contacts-export.md) | Export contacts|

### Contacts Tags

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/tags/list](tags-list.md) | List tags |
| POST | [/tags/create](tags-create.md) | Create tag |
| PUT | [/tags/update](tags-update.md) | Update tag |
| DELETE | [/tags/delete](tags-delete.md) | Delete tag |

### Marketing Campaigns

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/marketing/list](marketing-list.md) | List campaigns|
| GET | [/marketing/{id}](marketing-get.md) | Get campaign detail |
| GET | [/marketing/{id}/report](marketing-report.md) | Get campaign report |
| POST | [/marketing/create](marketing-create.md) | Create campaign |
| PUT | [/marketing/update/{id}](marketing-update.md) | Update campaign |
| POST | [/marketing/copy/{id}](marketing-copy.md) | Copy campaign |
| DELETE | [/marketing/delete/{id}](marketing-delete.md) | Delete campaign |
| POST | [/marketing/test](marketing-test.md) | Send test email |

### Templates

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/templates/list](templates-list.md) | List templates|
| GET | [/templates/{id}](templates-get.md) | Get template detail |
| POST | [/templates/create](templates-create.md) | Create template |
| PUT | [/templates/update/{id}](templates-update.md) | Update template |
| POST | [/templates/copy/{id}](templates-copy.md) | Copy template |
| GET | [/templates/content/{id}](templates-get-content.md) | Get template content |
| DELETE | [/templates/delete/{id}](templates-delete.md) | Delete template|

### Domains

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/domains/list](domains-list.md) | List domains |
| GET | [/domains/{slug}](domains-get.md) | Get domain detail |
| POST | [/domains/add](domains-add.md) | Add domain |
| POST | [/domain/submit-domain-verify](domains-verify.md) | Submit domain verification |
| GET | [/domain/domain-verify-polling](domains-verify-polling.md) | Poll verification status |
| PUT | [/domain/config/{domainSlug}](domains-config.md) | Configure domain |
| PUT | [/domain/update/{domainSlug}](domains-update.md) | Update domain |
| DELETE | [/domain/{domainSlug}](domains-delete.md) | Delete domain |

### Domain Emails

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | [/domain-emails/list](domain-emails-list.md) | List domain emails |
| GET | [/domain-emails/{id}](domain-emails-get.md) | Get domain email detail |
| POST | [/domain-emails/add](domain-emails-add.md) | Add domain email |
| PUT | [/domain-emails/{emailId}](domain-emails-update.md) | Update domain email |
| DELETE | [/domain-emails/{emailId}](domain-emails-delete.md) | Delete domain email |

### Team

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | [/team/create](team-create.md) | Create team |
| POST | [/team/invite](team-invite.md) | Invite member |
| PUT | [/team/set-default](team-set-default.md) | Set default team |
| DELETE | [/team/member/{userId}](team-remove-member.md) | Remove member |
| PUT | [/team/member/{userId}/role](team-update-member-role.md) | Update member role |

---

## Response Format

All API responses follow this format:

```json
{
  "code": 200,
  "message": "Success",
  "data": { ... }
}
```

### Common HTTP Status Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Bad Request - Invalid parameters |
| 401 | Unauthorized - Invalid API key or token |
| 403 | Forbidden - Access denied |
| 404 | Not Found |
| 429 | Too Many Requests - Rate limit exceeded |
| 500 | Internal Server Error |

---

## Quick Start

### 1. Verify your API key

```bash
curl -X GET https://api.litestartup.com/client/v2/verify \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

### 2. Send your first email

```bash
curl -X POST https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx' \
     -H 'Content-Type: application/json' \
     -d '{
  "to": "recipient@example.com",
  "from": "Your Name <sender@yourdomain.com>",
  "subject": "Hello from Litestartup!",
  "html": "<h1>Welcome!</h1><p>This is your first email via API.</p>"
}'
```

### 3. Check sent emails

```bash
curl -X GET https://api.litestartup.com/client/v2/emails \
     -H 'Authorization: Bearer sk_live_xxxxxxxxxxxxx'
```

---

## Support

- Email: support@litestartup.com
- Documentation: https://www.litestartup.com/docs

---

*Last updated: January 30, 2026*