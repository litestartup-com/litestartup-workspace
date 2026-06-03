---
title: Litestartup Skill
description: Publish blog, docs, website, and changelog directly from your AI-powered editor. Write content, run one prompt, go live in seconds.
---

# Litestartup Skill

> Publish from your editor. No dashboard needed.

## Overview

Litestartup Skill is an open-source skill package that connects your AI-powered editor (Cursor, Claude Code, Codex, Windsurf) to the LiteStartup platform. Write markdown or HTML in your editor, run one prompt, and your content is live.

## Supported content types

| Type | Format | Directory |
|------|--------|-----------|
| Blog | Markdown with YAML frontmatter | `blog/*.md` |
| Documentation | Litestartup Docs markdown | `docs/{lang}/**/*.md` |
| Website | HTML with Tailwind CSS | `website/*.html` |
| Changelog | Markdown | `changelog/*.md` |

## How it works

1. **Bind your git repo** — Use litestartup-skill to connect your content repository. A `litestartup.yaml` config file is created automatically.
2. **Write content** — Your AI editor knows the format from spec files. Write blog posts in markdown, docs in Litestartup Docs format, website pages in HTML, and changelog in markdown.
3. **Sync and publish** — Tell your AI editor to sync. It commits, pushes, and triggers the API. Your content is live in seconds.

## Supported editors

- **Cursor** — Native adapter via `.cursor/rules/litestartup.mdc`
- **Claude Code** — Native adapter via `CLAUDE.md`
- **Codex** — Native adapter via `AGENTS.md`
- **Windsurf** — Native adapter via `.windsurfrules`

## Key features

- **One Command Publish** — Write content, run sync, go live. No browser, no dashboard, no context switching.
- **Secure by Design** — API keys stored locally, never echoed. Scripts read from file, nothing exposed in conversation.
- **Structured Specs** — Self-contained spec files tell AI exactly how to format content. No guessing, no errors.
- **Git as Source of Truth** — Your content lives in git. Version control, branches, PR reviews — all native.

## Getting started

1. Clone the [litestartup-skill](https://github.com/litestartup-com/litestartup-skill) repo.
2. Copy the adapter file for your editor into your content repo.
3. Create a content repo and bind it to your LiteStartup account.
4. Start writing and publishing with natural language prompts.

## Pricing

Litestartup Skill is open source and free to use. You need a LiteStartup account to sync content.
