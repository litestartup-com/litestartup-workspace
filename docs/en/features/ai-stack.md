---
title: AI Stack
description: Unified AI tools — 9 capabilities covering text, audio, image, and video. OCR, transcription, TTS, voice clone, podcast, image generation, video generation, and intelligent LLM routing.
---

# AI Stack

> 9 AI tools, one unified platform. From OCR to podcast generation, from voice cloning to video creation.

## Overview

AI Stack provides a complete suite of AI capabilities through LiteStartup's dashboard and API. Instead of managing separate services for OCR, transcription, TTS, image generation, video creation, and LLM access — use AI Stack for all of them with unified auth, billing, and monitoring.

## Tools

### Image to Text (OCR)

Extract text from images, receipts, documents, and screenshots. Supports multimodal understanding — not just OCR, but contextual interpretation of visual content.

**Use cases**: Receipt scanning, document digitization, screenshot text extraction, handwriting recognition.

### Audio to Text (Transcription)

Transcribe audio and video files to text. Supports multiple languages and file formats including MP3, WAV, and MP4.

**Use cases**: Meeting transcription, interview notes, subtitle generation, voice memo processing.

### Text to Audio (TTS)

Convert text to natural-sounding speech with multiple voices and languages. Choose from a library of built-in voices or use your own cloned voice.

**Use cases**: Audio content creation, accessibility, podcast narration, notification audio.

### Voice Clone

Clone any voice from a short audio sample (10–30 seconds). The cloned voice can be used in Text to Audio and Podcast generation. Voice profiles are stored per team and reusable across all audio tools.

**Use cases**: Personalized TTS, branded audio content, podcast hosts with consistent voice identity.

### Text to Podcast

Generate multi-speaker podcast episodes from text content or URLs. AI generates a conversational script from your input, then synthesizes natural-sounding dialogue between two speakers.

**Features**:
- Input a long article, URL, or topic description
- AI generates a structured multi-turn conversation script
- Two-speaker synthesis with distinct voices (customizable)
- Asynchronous processing with progress tracking

**Use cases**: Convert blog posts to audio, create educational podcasts, repurpose long-form content.

### Text to Image

Generate images from text prompts using Seedream 3.0. Supports multiple aspect ratios, styles, and quality levels.

**Use cases**: Marketing visuals, social media graphics, product mockups, illustration generation.

### Text to Video

Generate videos from text descriptions. Asynchronous processing — submit a prompt, get a video when ready.

**Use cases**: Social media content, product demos, explainer clips, creative storytelling.

### Image to Video

Animate a static image into a short video clip. Upload an image and describe the desired motion or animation.

**Use cases**: Bring product photos to life, create animated social posts, generate motion from stills.

### LLM Router

Intelligent model routing across 10+ LLM providers (GPT, Claude, DeepSeek, Gemini, and more). Four routing modes:

| Mode | Description |
|------|-------------|
| **Auto** | AI classifies your prompt and selects the optimal model based on task type, cost, and complexity |
| **Direct** | Choose the exact model yourself, with real-time pricing (input/output per million tokens) |
| **Tag Routes** | Map tags like `fast`, `smart`, `creative` to pre-configured models |
| **Fallback** | Chain multiple models with automatic failover if primary is unavailable |

**Use cases**: Cost-optimized LLM access, multi-model experimentation, production AI pipelines with failover.

## How It Works

### Dashboard Access

All tools are accessible from the **AI Stack** section in your dashboard sidebar. Each tool has its own page with a simple interface:

1. Navigate to **AI Stack** in the sidebar
2. Select the tool you need
3. Provide input (text, image, audio, or URL)
4. Get results instantly (sync tools) or via status polling (async tools)

### Async Tasks

Heavy processing tasks (video generation, podcast creation, image generation) run asynchronously:

1. **Submit** — Send your request, receive a `usage_id`
2. **Poll** — Check task status with the usage ID
3. **Complete** — Download your result when processing finishes

Task status includes progress updates so your application can show meaningful feedback.

### API Access

1. Go to **Settings > API Keys** and create a new API key
2. Use the API key in your requests to any AI Stack endpoint
3. Monitor usage in **Settings > Usage**

## Key Features

- **Unified Platform** — One dashboard, one auth mechanism, 9 AI capabilities
- **Async Architecture** — Heavy tasks run in the background with status polling, no timeouts
- **Voice Library** — Built-in voices plus voice cloning for personalized audio
- **Smart LLM Routing** — Auto-classify tasks and route to the best model by cost/quality/speed
- **Markdown Rendering** — LLM Router responses render with full formatting (code blocks, tables, lists)
- **Usage Tracking** — Per-tool usage logs with billing integration

## Pricing

AI Stack usage is included in your plan's monthly AI Stack quota. Different tools consume different amounts based on processing complexity. See the [Pricing page](pricing.md) for details.
