---
title: "Introducing App Setup: Flexible Subdomain Routing for Your Applications"
date: 2026-06-05
slug: "app-setup-subdomain-routing"
tags: ["feature-release"]
status: "published"
excerpt: "Control how each application is accessed — serve your blog on a dedicated subdomain, disable unused services, or keep everything under one domain. All from a single dashboard."
---

We're excited to announce **App Setup** — a new feature that gives you full control over how each of your applications (Website, Blog, Docs, Changelog) is accessed by visitors.

## The Problem

Until now, all applications lived under your main domain as path-based routes:

```
www.example.com/blog
www.example.com/docs
www.example.com/changelog
```

This works great for most cases, but some users wanted more flexibility:

- "I want my blog on `blog.example.com`"
- "I only use LiteStartup for Docs — can I hide the Website?"
- "I need to disable Changelog since we don't use it yet"

## The Solution

The new **Setup** page (under Applications → Setup) lets you configure each application independently with three access modes:

### Path Mode (Default)

Content is served at your main domain path. Nothing changes from before.

### Subdomain Mode (Pro)

Serve any application on its own subdomain. When enabled:

- `blog.example.com` serves your blog
- `docs.example.com` serves your documentation
- Old path URLs (`/blog`, `/docs`) automatically 301 redirect to the subdomain

This is great for branding, SEO isolation, or when you want each application to feel like its own product.

### Disabled Mode

Returns 404 for that application. Use this to hide services you haven't set up yet, or to keep things clean when you only need specific applications.

## Mix and Match

The real power is in combining modes. For example:

| Application | Mode | URL |
|-------------|------|-----|
| Website | Path | `www.example.com` |
| Blog | Subdomain | `blog.example.com` |
| Docs | Path | `www.example.com/docs` |
| Changelog | Disabled | — |

## SEO-Safe Switching

Worried about SEO when changing modes? We've got you covered:

- **Automatic 301 redirects** — When you switch from path to subdomain, all old URLs permanently redirect to the new location
- **Link authority transfer** — Search engines pass PageRank through 301 redirects
- **Gradual migration** — Search engines typically complete re-indexing within 1–4 weeks

We also show a confirmation dialog with SEO implications before any mode change takes effect.

## Website-Specific Rules

Website is special — it's the root of your domain. You can:

- ✅ Keep it in Path mode (default)
- ✅ Disable it (if you only need Blog/Docs/Changelog)
- ❌ Subdomain mode is not available (your domain root *is* the website)

If you need your website on a different domain entirely, use Domain Settings instead.

## Getting Started

1. Go to **Applications → Setup** in your dashboard
2. Choose the access mode for each application
3. For subdomain mode: bind a subdomain and configure DNS (CNAME record)
4. Done — changes take effect immediately

## What's Next

The system is built to be extensible. As we add new applications (Roadmap, Feedback, etc.), they'll automatically appear on the Setup page with the same flexible routing options.

---

App Setup is available now for all users. Subdomain mode requires a Pro plan. [Upgrade today](/billing) to unlock dedicated subdomains for your applications.
