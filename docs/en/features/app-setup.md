---
title: App Setup
description: Configure how each application is accessed — via path, subdomain, or disabled.
---

# App Setup

The **Setup** page lets you control the access mode for each application (Website, Blog, Docs, Changelog) on a per-domain basis.

## Access Modes

| Mode | Behavior | Example |
|------|----------|---------|
| **Path** | Content served under main domain path | `www.example.com/blog` |
| **Subdomain** | Content served on a dedicated subdomain | `blog.example.com` |
| **Disabled** | Returns 404 — content is not accessible | — |

You can mix modes freely. For example: Website on path, Blog on subdomain, Docs on path, Changelog disabled.

## How to Access

Navigate to **Applications → Setup** in the sidebar.

## Changing Access Mode

1. Open the **Setup** page
2. Use the dropdown next to each service to select the desired mode
3. Confirm the change when prompted (SEO warning)

> [!WARNING]
> Switching modes triggers a **301 permanent redirect** from old URLs to new URLs. Search engines need 1–4 weeks to update their index. Rankings may fluctuate briefly during migration.

## Subdomain Mode

When you select **Subdomain** for a service:

1. Click the **Bind** button that appears
2. Enter the subdomain and domain (e.g. `blog` + `example.com`)
3. Configure your DNS: add a CNAME record pointing to your LiteStartup domain
4. The service will be accessible at the subdomain once DNS propagates

> [!NOTE]
> Subdomain mode requires a **Pro plan**. Free plans can only use Path and Disabled modes.

### DNS Configuration

Add a CNAME record at your DNS provider:

| Type | Name | Value |
|------|------|-------|
| CNAME | `blog` | `your-slug.litestartup.net` |

Replace `blog` with your chosen subdomain and `your-slug` with your team slug.

## Website Limitations

The **Website** application has special rules:

- **Path mode** — Default. Your website pages are served at the domain root (`/`, `/about`, `/pricing`, etc.)
- **Disabled mode** — All website pages return 404. Blog, Docs, and Changelog continue to work normally under their respective paths
- **Subdomain mode** — Not supported. Website is the root of your domain. To use a different domain, go to Domain Settings

> [!TIP]
> Use Website disabled mode if you only need LiteStartup for Blog, Docs, or Changelog — for example, when your main site is hosted elsewhere.

## SEO Behavior

### Path → Subdomain

| Old URL | New URL | What Happens |
|---------|---------|--------------|
| `www.example.com/blog` | `blog.example.com` | Automatic 301 redirect |
| `www.example.com/blog/my-post` | `blog.example.com/my-post` | Automatic 301 redirect |

The 301 redirect transfers link authority (PageRank) to the new URL. Search engines typically complete the migration within 1–4 weeks.

### Subdomain → Path

When switching back, we recommend keeping the old subdomain DNS active for 30 days to allow search engines to follow the 301 redirect back to the path URL.

## Adding Future Applications

The system is designed to be extensible. When new applications are added (e.g. Roadmap, Feedback), they automatically appear on the Setup page with the same Path / Subdomain / Disabled options.
