# litestartup-workspace

Official content repository for [www.litestartup.com](https://www.litestartup.com). Managed via [litestartup-skill](https://github.com/litestartup-com/litestartup-skill).

## Structure

```
blog/           ← Blog posts (markdown → HTML)
website/        ← Website pages (HTML + Tailwind CSS)
docs/           ← Documentation (LiteDocs format)
changelog/      ← Release changelogs (markdown)
```

## Publishing

```bash
# Sync all content to production
./scripts/ls-sync.sh
```

Content goes live at [www.litestartup.com](https://www.litestartup.com).
