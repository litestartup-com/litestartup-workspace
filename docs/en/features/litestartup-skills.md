---
title: Litestartup Skills
description: Publish blog, docs, website, changelog, and campaign emails directly from your AI coding agent. Complete setup guide with step-by-step instructions.
---

# Litestartup Skills

> Publish from your editor. No dashboard needed.

## Overview

Litestartup Skills is an open-source skill package that connects your AI coding agent (Cursor, Claude Code, Codex, Windsurf) to the LiteStartup platform. Write markdown or HTML in your editor, run one prompt, and your content is live.

With Litestartup Skills, you can update your website, docs, blog, changelog, and send campaign emails in the same coding session — keeping content in sync with your project at all times.

---

## Prerequisites

- A [LiteStartup](https://litestartup.com) account (free signup)
- Git installed on your machine
- An AI coding editor: Cursor, Claude Code, Codex, or Windsurf
- A public (not private) git repository on GitHub, GitLab, or Gitee

---

## Step 1: Create a git repository

Create a new public git repository for your content. This repo will hold all your website pages, blog posts, documentation, and changelogs.

```bash
mkdir my-content
cd my-content
git init
git remote add origin https://github.com/yourname/my-content.git
```

> **Important**: The repo must be public so LiteStartup can pull content from it.

---

## Step 2: Install Litestartup Skills

Clone the skill repo and copy the adapter file for your editor into your content repo:

```bash
git clone https://github.com/litestartup-com/litestartup-skills.git
```

Copy the adapter for your editor:

| Editor | Adapter file | Copy to |
|--------|-------------|---------|
| Cursor | `adapters/cursor/litestartup.mdc` | `.cursor/rules/litestartup.mdc` |
| Claude Code | `adapters/claude/CLAUDE.md` | `CLAUDE.md` (repo root) |
| Codex | `adapters/codex/AGENTS.md` | `AGENTS.md` (repo root) |
| Windsurf | `adapters/windsurf/.windsurfrules` | `.windsurfrules` (repo root) |

The adapter file tells your AI editor how to use Litestartup Skills — it loads the capabilities and specs automatically.

---

## Step 3: Get your API Key

1. Log in to [LiteStartup Dashboard](https://app.litestartup.com).
2. Go to **Settings > API Keys**.
3. Click **Create API Key**.
4. Select the required scopes:

| Scope | Purpose |
|-------|---------|
| `system.publish` | Required. Sync content (bind repo, publish pages, blog, docs, changelog) |
| `notification` | Optional. Send notification emails from the system address |
| `email` | Optional. Send emails from your custom domain address |

5. Copy the API key and save it securely. You will provide it during the bind step.

> **Tip**: If you plan to send emails (e.g., newsletters, release announcements) via your AI editor, include the `notification` or `email` scope.

---

## Step 4: Bind your repo

Open your content repo in your AI editor and use a natural language prompt to bind:

**Prompt example:**

```
Bind this repo to my LiteStartup account.
```

The AI will:
1. Ask you to provide your API key (stored locally at `~/.litestartup/credentials`, never displayed)
2. Detect the git remote URL
3. Call the LiteStartup bind API
4. Create a `litestartup.yaml` config file in your repo root

**After success, you'll see:**
```
✅ Repo bound to LiteStartup. You can now sync content.
```

---

## Step 5: Initialize your content repo

Ask your AI editor to set up the initial content structure based on your project:

**Prompt example:**

```
Initialize this content repo for my project "MyApp". Create:
- A homepage introducing MyApp
- An about page
- A blog post announcing our launch
- A quickstart doc in English
- A v1.0.0 changelog entry
```

The AI will create files following the Litestartup Skills specs:

```
my-content/
├── litestartup.yaml
├── blog/
│   └── announcing-myapp-launch.md
├── website/
│   ├── index.html
│   └── about.html
├── docs/
│   ├── config.json
│   └── en/
│       ├── _nav.md
│       ├── _sidebar.md
│       └── index.md
├── changelog/
│   └── v1.0.0.md
└── campaign/
    └── .gitkeep
```

---

## Step 6: First sync (test)

Run your first sync to verify everything works:

**Prompt example:**

```
Sync all my content to production.
```

The AI will:
1. Validate file structure and frontmatter
2. `git add`, `git commit`, `git push`
3. Call the sync API
4. Report results:

```
✅ Sync completed
inserted: blog/announcing-myapp-launch.md
inserted: website/index.html
inserted: website/about.html
inserted: docs/en/index.md
inserted: changelog/v1.0.0.md
```

Your content is now live at `https://yourdomain.com`.

---

## Step 7: Ongoing workflow

Once set up, you use Litestartup Skills just like you use your AI editor for coding — continuous, natural language driven updates:

**Update content when your project changes:**

```
Our pricing changed from $9 to $12/mo. Update the pricing page and the docs pricing section, then write a changelog entry for this change.
```

**Write and publish a blog post:**

```
Write a blog post about our new API v2 release. Include the key improvements and migration guide. Then sync it.
```

**Update docs after shipping a feature:**

```
We just shipped a dark mode feature. Add a "Dark Mode" section to the features docs and update the changelog.
```

**Send a campaign email to subscribers:**

```
Send a campaign email to newsletter_en subscribers announcing our new dark mode feature.
```

The AI writes a Markdown email in `campaign/`, commits, pushes, and triggers sync. LiteStartup converts it to HTML, runs an AI safety review, and sends to all active contacts in the tag.

**Send a notification email:**

```
Send a notification email about our new dark mode feature. Subject: "Dark mode is here!" Body: brief announcement with a link to the docs.
```

**Partial sync (only changed files):**

```
I only updated the pricing page. Sync just that file.
```

> **Key insight**: You can develop your project and keep all content (website, docs, blog, changelog) up to date — and send campaign emails to your subscribers — in the same AI coding session. No context switching, no separate CMS, no manual copy-pasting.

---

## Supported content types

| Type | Format | Directory | Published URL |
|------|--------|-----------|---------------|
| Blog | Markdown + YAML frontmatter | `blog/*.md` | `/blog/slug` |
| Documentation | Litestartup Docs markdown | `docs/{lang}/**/*.md` | `/docs/{lang}/path` |
| Website | HTML with Tailwind CSS | `website/**/*.html` | `/path` |
| Changelog | Markdown | `changelog/*.md` | `/changelog/slug` |
| Campaign | Markdown + YAML frontmatter | `campaign/*.md` | Sent via email to tagged contacts |

---

## Supported editors

| Editor | Adapter | How to install |
|--------|---------|----------------|
| Cursor | `.cursor/rules/litestartup.mdc` | Copy adapter file to content repo |
| Claude Code | `CLAUDE.md` | Place in repo root |
| Codex | `AGENTS.md` | Place in repo root |
| Windsurf | `.windsurfrules` | Place in repo root |

---

## Pricing

Litestartup Skills is **free and open source** (MIT license).

| Item | Cost |
|------|------|
| Skill package | Free |
| Content sync (blog, docs, website, changelog, campaign) | Free |
| Custom domain hosting | Free |
| Email sending | Pay-as-you-go (negligible cost) |
| Storage & bandwidth | Pay-as-you-go (negligible cost) |

You need a LiteStartup account to sync content. [Sign up free](https://app.litestartup.com/signup).
