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
| **LLM Chat** | Chat completions with 30+ models (DeepSeek, GPT, Claude, Qwen, etc.) |
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

All modalities use the same unified endpoint — just change the `model` field:

```bash
curl https://api.litestartup.com/client/v2/ai/generations \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "deepseek-v3",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

### 3. Get results

- **Sync** — LLM chat, TTS, OCR, and transcription return results immediately.
- **Async** — Video generation and digital human return a `task_id`. Poll `/client/v2/ai/tasks/{id}` for status.

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/client/v2/ai/generations` | POST | Unified generation — all modalities via `model` field |
| `/client/v2/ai/chat/completions` | POST | OpenAI-compatible chat completions (LLM only) |
| `/client/v2/ai/tasks/{id}` | GET | Check async task status |

### OpenAI-Compatible Mode (LLM)

For LLM chat, you can use the standard OpenAI SDK with our base URL:

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",
    base_url="https://api.litestartup.com/client/v2/ai"
)

response = client.chat.completions.create(
    model="deepseek-v3",
    messages=[{"role": "user", "content": "Hello!"}]
)
print(response.choices[0].message.content)
```

This endpoint is fully compatible with OpenAI's Chat Completions API — same request/response format, same SDKs.

> **Note**: `/client/v2/ai/chat/completions` only supports LLM models. For image, video, audio and other modalities, use the unified `/client/v2/ai/generations` endpoint.

The `model` field determines which capability is invoked. See the [API Reference](/docs/en/api/ai-gateway-generations) for full request/response documentation.  
For LLM-only usage with existing OpenAI SDKs, see the [OpenAI-Compatible Mode](#openai-compatible-mode-llm) section above.

> **Tip**: Try it interactively in the [Playground](https://app.litestartup.com/ai-stack) within your dashboard.

## Model Selection

Specify the model you want directly in the `model` field:

```json
{"model": "deepseek-v3", "messages": [...]}
{"model": "seedream-v5.0-lite-t2i", "input": {...}}
{"model": "wan-2.7-t2v", "input": {...}}
```

Available models are listed in the Playground. Intelligent routing features are planned for a future release.

## Sync vs Async

**Synchronous** endpoints return results in the HTTP response:
- LLM Chat, OCR, Speech to Text, Text to Speech

**Asynchronous** endpoints return a `task_id` immediately:
- Video Generation, Image to Video, Digital Human

For async tasks, poll `GET /client/v2/ai/tasks/{task_id}` until status is `completed`, then retrieve the output URL from the response.

## Billing

AI Gateway usage consumes AI credits from your plan's monthly quota. Different capabilities consume different amounts based on processing complexity. See the [Pricing page](pricing.md) for details.
