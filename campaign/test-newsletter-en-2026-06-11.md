---
subject: "Test Campaign - LiteStartup Skill Integration"
from: "all@mail.litestartup.com"
from_name: "LiteStartup"
tag: "newsletter_en"
status: "draft"
---

Hi there,

This is a **test campaign** sent via the LiteStartup Publish Skill's new campaign feature.

## What's Being Tested

- ✅ Campaign file sync from content repo
- ✅ Tag resolution by name (`newsletter_en`)
- ✅ Markdown to HTML conversion
- ✅ Campaign creation in the backend
- ✅ Contact count validation (status=subscribed, is_active=1)

## Campaign Workflow

The full skill-driven campaign workflow:

1. AI queries available tags via `GET /repo-sync/tags`
2. User picks a tag (or specifies one directly)
3. AI writes campaign Markdown with frontmatter
4. Sync triggers campaign creation
5. AI review → approval → send

---

Cheers,
The LiteStartup Team
