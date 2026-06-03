---
title: AI Stack
description: Unified AI tools API — Image to Text, Speech to Text, Text to Speech, and LLM Router. One API, multiple AI capabilities.
---

# AI Stack

> One API for Image to Text, Speech to Text, Text to Speech, and LLM routing.

## Overview

AI Stack provides a unified API for multiple AI capabilities. Instead of managing separate accounts for OCR, transcription, TTS, and LLMs, use a single LiteStartup API endpoint for all of them.

## Tools

### Image to Text (OCR)

Extract text from images, receipts, documents, and screenshots. Multi-language support with high accuracy.

```bash
curl -X POST https://api.litestartup.com/v2/ai/image-to-text \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -F "image=@receipt.jpg" \
  -F "language=en"

# Response:
# { "text": "Invoice #1234\nTotal: $99.00\nDate: 2024-01-15" }
```

### Speech to Text

Transcribe audio and video files to text. Support for multiple languages and file formats (MP3, WAV, MP4).

```bash
curl -X POST https://api.litestartup.com/v2/ai/speech-to-text \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -F "audio=@meeting.mp3" \
  -F "language=en"
```

### Text to Speech

Convert text to natural-sounding speech. Multiple voices and languages. Perfect for audio content and accessibility.

```bash
curl -X POST https://api.litestartup.com/v2/ai/text-to-speech \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello world", "voice": "alloy", "language": "en"}'
```

### LLM Router

Route requests to the best LLM (GPT-4, Claude, etc.) based on cost, speed, or quality. One API, many models.

```bash
curl -X POST https://api.litestartup.com/v2/ai/chat \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"messages": [{"role": "user", "content": "Hello"}], "strategy": "balanced"}'
```

## How to use

1. Go to **Settings > API Keys** and create a new API key.
2. Use the API key in your requests to any AI Stack endpoint.
3. Monitor usage in **AI Stack > Dashboard**.

## Key features

- **Unified API** — One base URL, one auth mechanism, multiple AI capabilities.
- **API Key Management** — Create multiple API keys with permissions, IP whitelists, and usage limits.
- **Usage Dashboard** — Track API calls, costs, and usage per tool. Set alerts and budgets.
- **Pay-as-you-go** — Only pay for what you use. No minimum commitments.

## Pricing

AI Stack uses pay-as-you-go pricing based on API usage. See the [Pricing page](/pricing) for details.
