---
title: Help Desk
description: Manage customer support requests with a ticket system on LiteStartup.
---

# Help Desk

> Manage customer support requests with a ticket system.

Help Desk provides an organized way to handle customer inquiries. Tickets can be created from email, live chat, or manually. Your team can manage, prioritize, and resolve them.

## Getting Started

1. Go to **Applications > Help Desk** from the sidebar
2. View incoming support requests
3. Assign tickets to team members
4. Track and resolve issues

## How Tickets Work

1. Customer sends email to your support address (e.g., `support@yourdomain.com`)
2. Email is automatically converted to a ticket
3. Ticket appears in your Tickets dashboard
4. Team responds via the ticket interface
5. Customer receives response as email

## Viewing Tickets

### Ticket List

The Tickets page shows all tickets with:

- Ticket number (e.g., `TKT-00123`)
- Subject line
- Status
- Priority
- Created date
- Last updated

### Filter Tickets

Filter by status:

- **Open** - New or in-progress tickets
- **Pending** - Waiting for customer response
- **Closed** - Resolved tickets

## Managing Tickets

### View Ticket Details

Click on a ticket to see:

- Full conversation history
- Customer information
- Ticket metadata
- Actions available

### Reply to Ticket

1. Open the ticket
2. Type your response
3. Click **Send Reply**
4. Customer receives your response via email

### Update Ticket Status

| Status | When to Use |
|--------|-------------|
| Open | Ticket needs attention |
| Pending | Waiting for customer reply |
| Closed | Issue resolved |

### Set Priority

| Priority | Description |
|----------|-------------|
| Low | Non-urgent issues |
| Normal | Standard requests |
| High | Urgent issues |
| Critical | Business-critical problems |

### Close Ticket

1. Open the ticket
2. Click **Close Ticket**
3. Ticket moves to closed status

## Creating Tickets

### Ticket Sources

| Source | Description |
|--------|-------------|
| Form | Created manually via the dashboard |
| Email | Automatically created from incoming customer emails |
| Chat | Converted from a live chat session |

### From Email

Tickets are automatically created when customers email your support address.

### Manual Creation

Create tickets manually:

1. Click **Create Ticket**
2. Enter customer email and name
3. Enter title and description
4. Set priority
5. Assign to team member (optional)
6. Click **Create**

### From Live Chat

Convert a chat session to a ticket:

1. Open the chat session in **Applications > Live Chat**
2. Click **Convert to Ticket**
3. Chat history is included in the ticket

## Team Collaboration

### Assign Tickets

Assign tickets to specific team members:

1. Open the ticket
2. Click **Assign**
3. Select team member

### Internal Notes

Add notes visible only to your team:

1. Open the ticket
2. Click **Add Note**
3. Enter internal note
4. Note is not sent to customer

## API Access

Manage tickets programmatically:

- [List Tickets](api/tickets-list.md)
- [Create Ticket](api/tickets-create.md)
- [Get Ticket](api/tickets-get.md)
- [Update Ticket](api/tickets-update.md)
- [Add Reply](api/tickets-add-reply.md)
- [Close Ticket](api/tickets-close.md)

## Best Practices

- **Respond promptly** - Aim for first response within 24 hours
- **Use clear subjects** - Help customers understand the status
- **Set accurate priorities** - Triage tickets appropriately
- **Close resolved tickets** - Keep your queue clean
- **Use internal notes** - Document context for your team