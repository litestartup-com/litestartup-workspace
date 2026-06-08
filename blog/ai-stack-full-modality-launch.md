---
title: "AI Stack: 8 AI Tools, One Unified API"
date: 2026-06-08
slug: "ai-stack-full-modality-launch"
tags: ["ai", "feature", "product"]
status: "published"
excerpt: "From OCR to video creation, from voice cloning to image generation — AI Stack now covers every modality through a single API."
---

We just shipped the biggest update to LiteStartup's AI capabilities: **AI Stack Full Modality**. Eight AI tools, one API, zero infrastructure headaches.

## What's AI Stack?

AI Stack is LiteStartup's unified AI toolkit. Instead of stitching together separate APIs for transcription, image generation, video creation, and LLM routing — you get everything under one roof with consistent auth, billing, and monitoring.

## The Full Tool Suite

### Text & Language

| Tool | What It Does |
|------|-------------|
| **LLM Router** | Routes prompts to the best model (GPT, Claude, DeepSeek, etc.) based on task type, cost, or quality |
| **AI Content Assistant** | Generate marketing copy, email drafts, blog outlines directly in the dashboard |

### Audio

| Tool | What It Does |
|------|-------------|
| **Audio to Text** | Transcribe meetings, interviews, and audio files to text |
| **Text to Audio** | Convert text to natural-sounding speech with multiple voices |
| **Voice Clone** | Clone any voice from a short audio sample for personalized TTS |

### Visual

| Tool | What It Does |
|------|-------------|
| **Image to Text** | Extract text from images, receipts, screenshots (OCR + multimodal) |
| **Text to Image** | Generate images from text prompts (Seedream 3.0) |
| **Text to Video** | Create videos from text descriptions |
| **Image to Video** | Animate static images into video clips |

## LLM Router: Smart Model Selection

The LLM Router deserves a special mention. It supports four routing modes:

- **Auto** — AI classifies your prompt and picks the best model by analyzing cost, speed, and task complexity
- **Direct** — You choose the exact model (Claude Opus, GPT-5, etc.) with full pricing transparency
- **Tag Routes** — Map tags like `fast`, `smart`, `creative` to specific models
- **Fallback** — Chain models with automatic failover if primary is down

The router displays real-time pricing (input/output per million tokens) so you always know what you're paying.

## Async by Design

Heavy tasks like video generation run asynchronously. You submit a task, get a `usage_id`, and poll for status. No timeouts, no broken connections on long-running jobs.

```
Submit → Processing → Completed → Download
```

Each task status includes progress updates, so your UI can show meaningful feedback.

## Voice Clone: Your Voice, AI Powered

Upload a short audio sample (10–30 seconds), and AI Stack creates a voice profile. Use that cloned voice in:

- **Text to Audio** — Read any text in the cloned voice

Voice profiles are stored per team, reusable across all audio tools.

## What's Next

We're working on:

- **Weighted billing** — Different AI tools have vastly different costs. Video generation will cost more credits than OCR. Fair pricing, coming soon
- **Usage analytics** — Per-tool usage trends, daily/weekly charts
- **Task notifications** — Get notified when async tasks complete instead of polling
- **API documentation** — Full OpenAPI spec for all AI Stack endpoints

## Try It Now

AI Stack is available to all LiteStartup users. Head to **AI Stack** in your dashboard sidebar to start using any tool immediately.

For API access, create an API key in **Settings > API Keys** and check the [AI Stack documentation](/docs/en/features/ai-stack) for endpoint details.
