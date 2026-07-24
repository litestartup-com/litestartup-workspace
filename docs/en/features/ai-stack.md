---
title: AI Gateway
description: Unified multimodal AI API — one API key for LLM chat, image generation, video creation, speech synthesis, OCR, transcription, voice cloning, and more.
---

# AI Gateway

> One API key. Every AI modality. Unified under a single endpoint.

## Overview

AI Gateway is LiteStartup's unified multimodal AI API. Instead of managing separate provider accounts for LLM, image, video, and audio — use one API key for all of them with unified billing, rate limiting, and intelligent model routing.

## Capabilities

### Text & Language

| Capability | Description |
|------------|-------------|
| **LLM Chat** | OpenAI-compatible chat completions with intelligent routing (auto, direct, tag, failover) |
| **OCR** | Extract text from images, receipts, documents with contextual interpretation |

### Audio

| Capability | Description |
|------------|-------------|
| **Speech to Text** | Transcribe audio/video files with multi-language support |
| **Text to Speech** | Natural-sounding speech synthesis with multiple voices |
| **Voice Clone** | Clone any voice from a short audio sample for personalized TTS |

### Image

| Capability | Description |
|------------|-------------|
| **Image Generation** | Generate images from text prompts with multiple styles and aspect ratios |
| **Image Edit** | Transform images with text instructions — inpainting, style transfer, editing |

### Video

| Capability | Description |
|------------|-------------|
| **Text to Video** | Generate videos from text descriptions (async) |
| **Image to Video** | Animate static images into video clips (async) |
| **Digital Human** | Generate talking-head videos from a photo and audio (async) |

## Quick Start

### 1. Get your API key

Go to **Settings > API Keys** in your dashboard and create a new key. This key works for all AI Gateway endpoints.

### 2. Call the API

Use the OpenAI-compatible endpoint or any modality-specific alias:

```bash
curl https://api.litestartup.com/ai/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model": "auto", "messages": [{"role": "user", "content": "Hello!"}]}'
```

### 3. Get results

- **Sync** — LLM chat, TTS, OCR, and transcription return results immediately.
- **Async** — Video generation and digital human return a `task_id`. Poll `/ai/tasks/{id}` for status.

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/ai/chat/completions` | POST | LLM chat (OpenAI-compatible) |
| `/ai/images/ocr` | POST | Image to text |
| `/ai/audio/transcriptions` | POST | Speech to text |
| `/ai/audio/speech` | POST | Text to speech |
| `/ai/audio/speech/clone` | POST | Voice clone |
| `/ai/images/generate` | POST | Image generation |
| `/ai/images/edit` | POST | Image editing |
| `/ai/videos/generate` | POST | Text to video |
| `/ai/videos/animate` | POST | Image to video |
| `/ai/videos/digital-human` | POST | Digital human video |
| `/ai/models` | GET | List available models |
| `/ai/tasks/{id}` | GET | Check async task status |

> **Tip**: Full API documentation with request/response examples is available in the [Playground](https://app.litestartup.com/ai-stack) within your dashboard.

## LLM Routing

AI Gateway supports 4 routing strategies for LLM requests:

| Strategy | How to use |
|----------|-----------|
| **Auto** | Set `"model": "auto"` — AI picks the best model by cost, speed, and complexity |
| **Direct** | Set `"model": "model-name"` — choose a specific model |
| **Tag** | Set `"model": "fast"` or `"smart"` — route to a pre-configured model |
| **Failover** | Configured server-side — automatic fallback if primary model is unavailable |

## Sync vs Async

**Synchronous** endpoints return results in the HTTP response:
- LLM Chat, OCR, Speech to Text, Text to Speech

**Asynchronous** endpoints return a `task_id` immediately:
- Video Generation, Image to Video, Digital Human

For async tasks, poll `GET /ai/tasks/{task_id}` until status is `completed`, then retrieve the output URL from the response.

## Billing

AI Gateway usage consumes AI credits from your plan's monthly quota. Different capabilities consume different amounts based on processing complexity. See the [Pricing page](pricing.md) for details.
