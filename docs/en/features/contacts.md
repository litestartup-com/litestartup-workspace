---
title: Contacts
description: Manage your contacts and subscriber lists for marketing campaigns on LiteStartup.
---

# Contacts

> Manage your contacts and subscriber lists for marketing campaigns.

Contacts are the foundation of your email marketing. LiteStartup provides powerful tools to import, organize, and manage your contact lists with tags and custom fields.

## Getting Started

1. Go to **Emails > Contacts** from the sidebar
2. Add contacts manually or import from CSV
3. Organize contacts with tags
4. Use contacts in your marketing campaigns

## Adding Contacts

### Add Single Contact

1. Click **Add Contact**
2. Enter contact details:
   - **Email** (required)
   - **Name**
   - **Company**
   - **Phone**
3. Assign tags (optional)
4. Click **Save**

### Import from CSV

Import multiple contacts at once:

1. Click **Import**
2. Upload your CSV file
3. Map CSV columns to contact fields
4. Choose tags to assign
5. Click **Import**

**CSV Format Example:**

```csv
email,name,first_name,last_name,phone,company
john@example.com,John Doe,John,Doe,+1234567890,Acme Inc
jane@example.com,Jane Smith,Jane,Smith,+0987654321,Tech Corp
```

### Import Options

| Option | Description |
|--------|-------------|
| Skip duplicates | Skip contacts that already exist (default: on) |
| Update existing | Update existing contacts with new data |
| Assign tags | Add tags to all imported contacts |

## Contact Fields

### Standard Fields

| Field | Description |
|-------|-------------|
| Email | Contact's email address (required) |
| Name | Full name |
| First Name | First name |
| Last Name | Last name |
| Phone | Phone number |
| Company | Company name |

### Contact Status

| Status | Description |
|--------|-------------|
| Subscribed | Active contact, can receive emails |
| Unsubscribed | Opted out, will not receive marketing emails |

## Organizing with Tags

Tags help you segment and organize your contacts for targeted campaigns.

### Create a Tag

1. Go to **Emails > Contacts** → **Tags**
2. Click **Create Tag**
3. Enter tag name and choose a color
4. Click **Save**

### Assign Tags to Contacts

- **Single contact**: Edit contact and select tags
- **Bulk assign**: Select multiple contacts and click **Add Tags**
- **During import**: Assign tags to all imported contacts

### Tag Examples

- `newsletter` - Newsletter subscribers
- `customer` - Paying customers
- `trial` - Trial users
- `vip` - High-value contacts
- `inactive` - Contacts who haven't engaged

## Managing Contacts

### Search and Filter

- **Search** by email or name
- **Filter** by status (subscribed/unsubscribed)
- **Filter** by tag

### Edit Contact

1. Click on a contact to open details
2. Update fields as needed
3. Click **Save**

### Delete Contact

1. Select contacts to delete
2. Click **Delete**
3. Confirm deletion

> **Note**: Deleted contacts cannot be recovered. Consider unsubscribing instead.

### Export Contacts

Export your contacts for backup or use in other systems:

1. Click **Export**
2. Choose format (CSV)
3. Select fields to include
4. Download file

## Using Contacts in Campaigns

When creating a marketing campaign:

1. Go to **Emails > Campaigns** → **Create Campaign**
2. In the audience section, choose:
   - **All contacts** - Send to everyone
   - **By tag** - Send to contacts with specific tags
   - **Custom segment** - Define custom criteria

## Contact Limits

| Plan | Contact Limit |
|------|---------------|
| Free | 3,000 contacts |
| Pro | Unlimited |
| Enterprise | Unlimited |

## API Access

Manage contacts programmatically via the [Contacts API](api/contacts-list.md):

- [List Contacts](api/contacts-list.md)
- [Add Contact](api/contacts-add.md)
- [Get Contact](api/contacts-get.md)
- [Search Contacts](api/contacts-search.md)
- [Update Contact](api/contacts-update.md)
- [Delete Contact](api/contacts-delete.md)
- [Import Contacts](api/contacts-import.md)
- [Export Contacts](api/contacts-export.md)

### Tags API

- [List Tags](api/tags-list.md)
- [Create Tag](api/tags-create.md)
- [Update Tag](api/tags-update.md)
- [Delete Tag](api/tags-delete.md)

## Best Practices

- **Keep lists clean** - Remove bounced and invalid emails regularly
- **Use double opt-in** - Confirm subscriptions to improve deliverability
- **Segment with tags** - Send targeted content to specific groups
- **Respect unsubscribes** - Never re-add unsubscribed contacts
- **Regular exports** - Backup your contact list periodically