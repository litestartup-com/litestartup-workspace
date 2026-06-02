---
title: Templates
description: Create and manage reusable email templates for your campaigns on LiteStartup.
---

# Templates

> Create and manage reusable email templates for your campaigns.

Templates allow you to create reusable email designs that can be used across multiple campaigns. Save time by creating templates once and reusing them for newsletters, promotions, and transactional emails.

## Getting Started

1. Go to **Emails > Templates** from the sidebar
2. Click **Create Template** to create a new template
3. Design your template using the visual editor
4. Save and use it in your marketing campaigns

## Creating a Template

### Using the Visual Editor

1. Click **Create Template**
2. Enter a template name and optional description
3. Choose a category (e.g., `onboarding`, `newsletter`, `promotion`)
4. Design your email using the drag-and-drop editor
5. Click **Save** to save your template

### Template Content

Templates support HTML content with dynamic variables for personalization:

```html
<h1>Welcome {{name}}!</h1>
<p>Thank you for joining us at {{company}}.</p>
<p>Your email: {{email}}</p>
```

### Available Variables

| Variable | Description |
|----------|-------------|
| `{{name}}` | Contact's full name |
| `{{first_name}}` | Contact's first name |
| `{{last_name}}` | Contact's last name |
| `{{email}}` | Contact's email address |
| `{{company}}` | Contact's company name |
| `{{UNSUBSCRIBE}}` | Unsubscribe link (required for marketing emails) |

## Managing Templates

### List Templates

View all your templates on the Templates page. You can:

- **Search** templates by name
- **Filter** by category
- **Sort** by creation date

### Edit Template

1. Click on a template to open it
2. Make your changes in the editor
3. Click **Save** to update

### Copy Template

Duplicate an existing template to create a variation:

1. Click the **Copy** button on a template
2. A new template is created with "(Copy)" suffix
3. Edit and rename as needed

### Delete Template

1. Click the **Delete** button on a template
2. Confirm deletion

> **Note**: Deleting a template does not affect campaigns that have already used it.

## Using Templates in Campaigns

When creating a marketing campaign:

1. Go to **Emails > Campaigns** → **Create Campaign**
2. In the content section, click **Use Template**
3. Select a template from your library
4. Customize the content as needed
5. Send your campaign

## Template Categories

Organize your templates with categories:

- **onboarding** - Welcome emails, getting started guides
- **newsletter** - Regular updates, news
- **promotion** - Sales, discounts, special offers
- **transactional** - Order confirmations, receipts
- **notification** - Alerts, reminders

## API Access

Manage templates programmatically via the [Templates API](api/templates-list.md):

- [List Templates](api/templates-list.md)
- [Create Template](api/templates-create.md)
- [Get Template](api/templates-get.md)
- [Update Template](api/templates-update.md)
- [Copy Template](api/templates-copy.md)
- [Delete Template](api/templates-delete.md)

## Best Practices

- **Use descriptive names** - Make templates easy to find
- **Include unsubscribe links** - Required for marketing emails
- **Test before sending** - Preview templates with test data
- **Keep templates modular** - Create reusable components
- **Use categories** - Organize templates for easy access