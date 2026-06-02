---
title: Emails Setup
description: Create and manage email addresses for your verified domains on LiteStartup.
---

# Domain Emails

> Create and manage email addresses for your verified domains.

Domain emails allow you to send and receive emails using your own domain, such as `support@yourdomain.com`, `hello@yourdomain.com`, or `noreply@yourdomain.com`.

## Prerequisites

Before creating domain emails, you need:

- A verified domain in LiteStartup (see [Domains](domains.md))
- DNS records configured for email receiving (MX records)

## Getting Started

1. Go to **Emails > Emails Setup** page from the dashboard
2. Click **Add Email** to create a new email address
3. Choose the domain and enter the local part (e.g., `support`)
4. Start sending and receiving emails

## Creating a Domain Email

### Add Email Address

1. Click **Add Email**
2. Select a verified domain
3. Enter the email address (local part only, e.g., `info`)
4. Enter a display name (e.g., "Info Team")
5. Choose email type
6. Click **Save**

### Email Types

| Type | Description | Use Case |
|------|-------------|----------|
| Team Email | Shared inbox for the team | `support@`, `info@`, `sales@` |
| Member Email | Personal email for a team member | `john@`, `jane@` |

## Managing Domain Emails

### View Email List

The Domain Emails page shows all your email addresses with:

- Email address
- Display name
- Associated domain
- Email type
- Creation date

### Edit Email

1. Click on an email address
2. Update display name or settings
3. Click **Save**

### Delete Email

1. Click **Delete** on an email
2. Confirm deletion

> **Warning**: Deleting an email address will remove all associated data.

## Using Domain Emails

### Send Emails

Use domain emails as the "From" address when sending:

1. Go to **Emails** → **Compose**
2. Select your domain email in the "From" field
3. Compose and send your email

### Receive Emails

Incoming emails to your domain email appear in:

1. Go to **Emails** → **Inbox**
2. View and manage received emails
3. Reply or forward as needed

### In Marketing Campaigns

Use domain emails for marketing:

1. Go to **Marketing** → **Create Campaign**
2. Select your domain email as the sender
3. Recipients see your professional email address

## Email Address Examples

| Email | Purpose |
|-------|---------|
| `support@yourdomain.com` | Customer support |
| `hello@yourdomain.com` | General inquiries |
| `info@yourdomain.com` | Information requests |
| `noreply@yourdomain.com` | Automated notifications |
| `sales@yourdomain.com` | Sales inquiries |
| `newsletter@yourdomain.com` | Newsletter sending |

## API Access

Manage domain emails programmatically via the [Domain Emails API](api/domain-emails-list.md):

- [List Domain Emails](api/domain-emails-list.md)
- [Add Domain Email](api/domain-emails-add.md)
- [Get Domain Email](api/domain-emails-get.md)
- [Update Domain Email](api/domain-emails-update.md)
- [Delete Domain Email](api/domain-emails-delete.md)

## Best Practices

- **Use descriptive names** - `support@` is clearer than `s@`
- **Set display names** - "Support Team" looks more professional
- **Create role-based emails** - Use `support@`, `sales@` instead of personal names
- **Use noreply sparingly** - Customers prefer emails they can reply to
- **Monitor all inboxes** - Don't let emails go unanswered