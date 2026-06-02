---
title: Docs
description: Create documentation and knowledge base for your product using LiteStartup's built-in docs feature.
---

# Docs

> Create documentation and knowledge base for your product.

The Docs feature allows you to create and publish documentation, help centers, and knowledge bases for your product or service.

## Getting Started

1. Go to **Docs** from the dashboard
2. Create a new documentation site
3. Add pages and organize with sidebar
4. Publish and share with users

## Creating Documentation

### Create a Doc Site

1. Click **Create Docs**
2. Enter site name and description
3. Choose a theme
4. Click **Create**

### Add Pages

1. Click **Add Page**
2. Enter page title
3. Write content in Markdown
4. Click **Save**

### Organize with Sidebar

Structure your docs with a sidebar navigation:

```markdown
- [Introduction](README.md)
- [Getting Started](quickstart.md)
- **Features**
  - [Feature 1](features/feature1.md)
  - [Feature 2](features/feature2.md)
- **API Reference**
  - [Overview](api/README.md)
  - [Endpoints](api/endpoints.md)
```

## Writing Content

### Markdown Support

Write documentation in Markdown:

- **Headings** - Structure your content
- **Code blocks** - Show code examples
- **Tables** - Display structured data
- **Links** - Connect pages
- **Images** - Add visuals

### Code Examples

Include syntax-highlighted code:

~~~markdown
```javascript
const api = new LiteStartup('YOUR_API_KEY');
api.sendEmail({
  to: 'user@example.com',
  subject: 'Hello'
});
```
~~~

## Customization

### Theme Settings

- **Primary color** - Match your brand
- **Logo** - Add your logo
- **Favicon** - Custom browser icon

### Custom Domain

Host docs on your domain:

1. Add CNAME record to your domain
2. Configure domain in settings
3. Docs available at `docs.yourdomain.com`

## Features

- **Search** - Full-text search across all pages
- **Versioning** - Maintain multiple doc versions
- **Multi-language** - Support multiple languages
- **Analytics** - Track page views and searches
- **Feedback** - Collect user feedback on pages

## Best Practices

- **Clear structure** - Organize logically
- **Concise writing** - Get to the point
- **Code examples** - Show, don't just tell
- **Keep updated** - Maintain accuracy
- **Use search data** - Improve based on what users search for