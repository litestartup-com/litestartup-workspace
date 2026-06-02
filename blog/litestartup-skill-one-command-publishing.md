---
title: "LiteStartup Skill: One-Command Publishing from Your AI Editor"
date: 2026-06-02
slug: "litestartup-skill-one-command-publishing"
tags: ["skill", "tutorial", "publishing"]
status: "published"
---

Today we're shipping a major upgrade to how teams publish content: **multi-binding support** for LiteStartup Skill. One API key, multiple domains, zero confusion.

## The Problem We Solved

Previously, if you managed multiple websites under one LiteStartup account, you had to juggle API keys or manually specify which domain to sync. Not anymore.

Now each content repo carries its own `domain_slug` in `litestartup.yaml`. When you run `ls-sync.sh`, the skill automatically targets the correct domain. No prompts. No mistakes.

## How Multi-Binding Works

```yaml
# litestartup.yaml — one per content repo
version: 1
binding_id: 6
domain_slug: domain-bab4cade66abd03b75eda09337a941f1
endpoint: https://api.litestartup.com
repo_url: https://github.com/your-org/site-a.git
```

Your second site? Different repo, different `domain_slug`, same API key:

```yaml
# Different repo's litestartup.yaml
version: 1
binding_id: 7
domain_slug: do4cjlixsg31gzalnrihjwnshn
endpoint: https://api.litestartup.com
repo_url: https://github.com/your-org/site-b.git
```

Both repos can live on the same machine. Switch directories, run sync, done.

## What Changed

- **API**: `trigger`, `status`, and `unbind` endpoints now accept `domain_slug` parameter for precise targeting
- **Skill scripts**: `ls-bind.sh` extracts `domain_slug` from bind response; `ls-sync.sh` passes it automatically
- **YAML template**: `domain_slug` field added to `litestartup.yaml.example`

## Publishing Flow (30 seconds)

```bash
# 1. Write content — blog post, changelog, docs page, whatever
# 2. One command:
./scripts/ls-sync.sh

# Done. Your changes are live.
```

Behind the scenes:
1. Git commit + push
2. API trigger with `domain_slug` precision
3. Server clones, hashes, compares, writes
4. CDN cache purge

## Content Types Supported

| Type | Format | Server Handling |
|------|--------|-----------------|
| Blog | Markdown + YAML frontmatter | Converts to HTML, extracts tags |
| Website | Full HTML | Parsed into 5 template parts |
| Docs | Markdown + `config.json` | File-to-file sync to `var/docs/` |
| Changelog | Markdown with semver title | Timeline rendering |

## Get Started

Already have a LiteStartup account?

```bash
curl -fsSL https://litestartup.com/skill/install.sh | bash
./scripts/ls-bind.sh
# Paste your API key when prompted
```

Your AI editor now understands LiteStartup publishing. Ask it to "write a blog post and publish" — it will.

Ship faster. Edit locally. Go live in seconds.
