# AI Stack - Image to Text (OCR)

> Extract text from an image using OCR (Optical Character Recognition). Supports both base64-encoded image uploads and image URLs.

**Endpoint**: `POST https://api.litestartup.com/client/v2/ai-stack/image-to-text`

**Headers**

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token: `Bearer <your_token>` |
| Content-Type | Yes | `application/json` |

**Body Parameters**

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| image_base64 | string | Conditional | Base64-encoded image data. Either `image_base64` or `image_url` is required |
| image_url | string | Conditional | URL of the image to process. Either `image_base64` or `image_url` is required |
| approximate_pixel | integer | No | Target pixel count for image resizing before OCR |
| mode | string | No | OCR processing mode |
| filter_thresh | float | No | Confidence threshold for filtering results |
| half_to_full | integer | No | Convert half-width characters to full-width (1 = enable, 0 = disable) |

**Image Limits**

- Maximum image size: **8 MB** (after base64 decode)
- Supported formats: JPEG, PNG, GIF, BMP, WebP
- Data URI prefix (e.g., `data:image/png;base64,`) is automatically stripped if present

**Example 1: Upload base64 image**

```bash
curl -X POST https://api.litestartup.com/client/v2/ai-stack/image-to-text \
     -H 'Authorization: Bearer <your_token>' \
     -H 'Content-Type: application/json' \
     -d '{
  "image_base64": "/9j/4AAQSkZJRgABAQ..."
}'
```

**Example 2: Process image from URL**

```bash
curl -X POST https://api.litestartup.com/client/v2/ai-stack/image-to-text \
     -H 'Authorization: Bearer <your_token>' \
     -H 'Content-Type: application/json' \
     -d '{
  "image_url": "https://example.com/document.png",
  "filter_thresh": 0.5
}'
```

**Response (Success)**

```json
{
  "code": 200,
  "message": "ok",
  "data": {
    "line_texts": [
      "Invoice #12345",
      "Date: 2025-01-15",
      "Amount: $299.00"
    ],
    "line_rects": [
      [10, 20, 200, 40],
      [10, 50, 180, 70],
      [10, 80, 160, 100]
    ],
    "line_probs": [0.98, 0.95, 0.97],
    "request_id": "req_abc123",
    "time_elapsed": "1.23s"
  }
}
```

**Response Fields**

| Field | Type | Description |
|-------|------|-------------|
| line_texts | string[] | Array of recognized text lines |
| line_rects | number[][] | Bounding box coordinates for each text line [x1, y1, x2, y2] |
| line_probs | number[] | Confidence probability for each text line (0.0 - 1.0) |
| request_id | string | Unique request identifier |
| time_elapsed | string | Processing time |

**Error Codes**

| Code | Description |
|------|-------------|
| 200 | OCR processing completed successfully |
| 400 | Invalid request: no image provided, invalid base64 data, invalid URL, or image exceeds 8MB |
| 403 | Forbidden (unauthorized team) |
| 500 | OCR processing failed |
