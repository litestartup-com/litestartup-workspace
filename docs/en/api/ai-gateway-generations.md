# AI Gateway API Reference

> Unified multimodal AI API with OpenAI-compatible LLM access.

## Endpoints Overview

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/client/v2/ai/generations` | POST | Unified generation — all modalities via `model` field |
| `/client/v2/ai/chat/completions` | POST | OpenAI-compatible chat completions (LLM only) |
| `/client/v2/ai/tasks/{id}` | GET | Check async task status |

---

## OpenAI-Compatible: Chat Completions

**Endpoint**: `POST https://api.litestartup.com/client/v2/ai/chat/completions`

Fully compatible with OpenAI's Chat Completions API. Use any OpenAI SDK by changing the `base_url`:

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",
    base_url="https://api.litestartup.com/client/v2/ai"
)

response = client.chat.completions.create(
    model="deepseek-v3",
    messages=[{"role": "user", "content": "Hello!"}],
    temperature=0.7,
    max_tokens=4096
)
```

```javascript
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: 'YOUR_API_KEY',
  baseURL: 'https://api.litestartup.com/client/v2/ai',
});

const response = await client.chat.completions.create({
  model: 'deepseek-v3',
  messages: [{ role: 'user', content: 'Hello!' }],
});
```

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/chat/completions \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "deepseek-v3",
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "What is LiteStartup?"}
  ],
  "temperature": 0.7,
  "max_tokens": 4096
}'
```

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| model | string | Yes | LLM model identifier (e.g. `deepseek-v3`, `gpt-4o`, `claude-sonnet-4-20250514`) |
| messages | array | Yes | Chat messages array |
| temperature | number | No | Sampling temperature (0-2, default varies by model) |
| max_tokens | integer | No | Maximum tokens in the response |
| stream | boolean | No | Enable streaming (default: false) |

### Response

```json
{
  "id": "chatcmpl-a1b2c3d4e5f6",
  "object": "chat.completion",
  "created": 1721836800,
  "model": "deepseek-v3",
  "choices": [
    {
      "index": 0,
      "message": {"role": "assistant", "content": "LiteStartup is..."},
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 24,
    "completion_tokens": 128,
    "total_tokens": 152,
    "cost": "0.0012"
  }
}
```

> **Note**: This endpoint only accepts LLM models. Non-LLM models (image, video, audio) will return a `400` error. Use `/client/v2/ai/generations` for those.

---

## Unified: Generations

**Endpoint**: `POST https://api.litestartup.com/client/v2/ai/generations`

All modalities (LLM, image, video, audio, OCR) through a single endpoint. The `model` field determines which capability is invoked.

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer <your_api_key>` |
| Content-Type | Yes | `application/json` |

## Request Body

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| model | string | Yes | Model identifier (e.g. `deepseek-v3`, `seedream-v5.0-lite-t2i`, `wan-2.7-t2v`) |
| messages | array | Conditional | Chat messages array (required for LLM models) |
| input | object | Conditional | Model-specific input parameters (required for non-LLM models) |
| stream | boolean | No | Enable streaming for LLM models (default: false) |

> Either `messages` (for LLM) or `input` (for other modalities) is required depending on the model type.

---

## Examples by Modality

### LLM Chat

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "deepseek-v3",
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "What is LiteStartup?"}
  ],
  "temperature": 0.7
}'
```

**Response** (OpenAI-compatible):

```json
{
  "id": "chatcmpl-a1b2c3d4e5f6",
  "object": "chat.completion",
  "created": 1721836800,
  "model": "deepseek-v3",
  "choices": [
    {
      "index": 0,
      "message": {"role": "assistant", "content": "LiteStartup is..."},
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 24,
    "completion_tokens": 128,
    "total_tokens": 152,
    "cost": "0.0012"
  }
}
```

---

### Image Generation (Sync)

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "seedream-v5.0-lite-t2i",
  "input": {
    "prompt": "A futuristic city at sunset, cyberpunk style",
    "width": 1024,
    "height": 1024
  }
}'
```

---

### Image OCR (Sync)

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "ls-ocr",
  "input": {
    "image_url": "https://example.com/receipt.png"
  }
}'
```

---

### Text to Video (Async)

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "wan-2.7-t2v",
  "input": {
    "prompt": "A cat playing piano in a jazz bar",
    "duration": 5
  }
}'
```

**Response** (Async task submitted):

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "task_id": 12345,
    "status": "processing",
    "model": "wan-2.7-t2v"
  },
  "meta": {
    "tool": "text-to-video",
    "provider": "atlascloud"
  }
}
```

---

### Text to Speech (Sync)

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "cosyvoice-2.0",
  "input": {
    "text": "Hello, welcome to LiteStartup!",
    "voice": "default"
  }
}'
```

---

### Speech to Text / Transcription (Sync)

```bash
curl -X POST https://api.litestartup.com/client/v2/ai/generations \
     -H 'Authorization: Bearer <your_api_key>' \
     -H 'Content-Type: application/json' \
     -d '{
  "model": "sensevoice-v1",
  "input": {
    "audio_url": "https://example.com/meeting.mp3"
  }
}'
```

---

## Response Formats

### Sync Tool Response (Image/Audio/OCR)

```json
{
  "code": 200,
  "message": "Success",
  "data": { ... },
  "meta": {
    "model": "model-id",
    "tool": "tool-type",
    "provider": "provider-name",
    "latency_ms": 1234
  }
}
```

### Async Task Response (Video/Digital Human)

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "task_id": 12345,
    "status": "processing",
    "model": "model-id"
  },
  "meta": {
    "tool": "tool-type",
    "provider": "provider-name"
  }
}
```

For async tasks, poll `GET /client/v2/ai/tasks/{task_id}` until status is `completed`:

```bash
curl https://api.litestartup.com/client/v2/ai/tasks/12345 \
     -H 'Authorization: Bearer <your_api_key>'
```

```json
{
  "code": 200,
  "data": {
    "task_id": 12345,
    "status": "completed",
    "output": {
      "video_url": "https://cdn.litestartup.com/ai/output/..."
    }
  }
}
```

Task status values: `processing`, `completed`, `failed`.

---

## Error Response

```json
{
  "error": {
    "code": "model_not_found",
    "message": "The requested model 'xyz' is not available.",
    "type": "invalid_request_error"
  }
}
```

**Error Codes**

| HTTP Status | Error Code | Description |
|-------------|-----------|-------------|
| 400 | invalid_request | Missing `model` field or invalid parameters |
| 401 | unauthorized | Invalid or missing API key |
| 403 | forbidden | Team not authorized for this feature |
| 404 | model_not_found | Requested model does not exist |
| 429 | rate_limited | Too many requests, retry after cooldown |
| 500 | provider_error | Upstream provider failure |
