---
title: "Introducing AI Gateway: One API Key for Every AI Modality"
date: 2026-07-21
slug: "ai-gateway-launch"
tags: ["ai", "feature", "product"]
status: "published"
excerpt: "AI Stack is now AI Gateway — a unified multimodal AI API. One key, one endpoint, all modalities. LLM chat, image generation, video creation, speech, OCR, and more."
---

Today we're launching **AI Gateway** — the evolution of AI Stack. Same powerful capabilities, clearer vision: one API key for every AI modality your startup needs.

## Why the rename?

AI Stack described what we built — a stack of AI tools. But "AI Gateway" better describes what you actually get: a single gateway to every AI capability, with one key, unified billing, and intelligent routing built in.

## What's new

### One API Key

No more managing separate provider accounts. Your LiteStartup API key now works across all modalities:

- **LLM Chat** — OpenAI-compatible `/ai/chat/completions` with 4 routing strategies
- **Image Generation** — Text to image with multiple styles and aspect ratios
- **Image Editing** — Transform images with text instructions
- **Video Generation** — Text to video and image to video (async)
- **Digital Human** — Talking-head videos from a photo and audio
- **Speech to Text** — Transcribe audio and video files
- **Text to Speech** — Natural speech synthesis with voice cloning
- **OCR** — Extract text from images and documents

### OpenAI-compatible

Switch from OpenAI to AI Gateway in one line. Same SDK, same request format:

```bash
curl https://api.litestartup.com/ai/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model": "auto", "messages": [{"role": "user", "content": "Hello!"}]}'
```

### Smart LLM Routing

Four routing strategies for LLM requests:

| Strategy | Description |
|----------|-------------|
| **Auto** | AI classifies your prompt and picks the best model |
| **Direct** | Choose the exact model yourself |
| **Tag** | Map tags like `fast`, `smart`, `creative` to models |
| **Failover** | Chain models with automatic fallback |

### Uncensored Models

For creative professionals and adult content platforms, AI Gateway now offers access to uncensored image and video generation models with no content filters. [Learn more →](/products/models/uncensored)

## Migration

If you were using AI Stack, **nothing changes on your end**. Same endpoints, same API key, same functionality. We've just added more capabilities and a clearer product identity.

## What's next

- More LLM providers via relay chains
- Model aliases for easier migration from other services
- Expanded async capabilities
- Usage analytics dashboard

---

AI Gateway is available now to all LiteStartup users on Free and Pro plans. [Get your API key →](https://app.litestartup.com/signup)
