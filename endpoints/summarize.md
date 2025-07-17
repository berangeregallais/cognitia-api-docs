# Summarize Text

The `summarize` endpoint returns a short, meaningful summary of a longer text input.  
It uses AI to preserve the core message, tone, and structure in just a few lines.

---

## 📌 POST /summarize

Base URL: <https://api.cognitia.ai/v1/summarize>

---

### 🔐 Authentication

All requests must include your API token in the `Authorization` header:

```makefile
Authorization: Bearer YOUR_API_TOKEN
```

---

### 📥 Request

#### Headers

| Name           | Type    | Required | Description              |
|----------------|---------|----------|--------------------------|
| Authorization  | string  | ✅ yes    | Bearer token             |
| Content-Type   | string  | ✅ yes    | `application/json`       |

---

#### Body

```json
{
  "text": "In recent years, renewable energy sources have gained traction as the world faces growing concerns over climate change. Governments are investing heavily in wind, solar, and hydroelectric power to reduce carbon emissions..."
}
```

| Field | Type   | Required | Description                                           |
| ----- | ------ | -------- | ----------------------------------------------------- |
| text  | string | ✅ yes    | The long-form text to summarize (max 2000 characters) |

---

### 📤 Response

#### ✅ Success – 200 OK

```json
{
  "summary": "Renewable energy is growing globally as governments invest in sustainable alternatives to reduce carbon emissions."
}
```

| Field   | Type   | Description                                 |
| ------- | ------ | ------------------------------------------- |
| summary | string | A short, coherent summary of the input text |

---

#### ❌ Error Responses

| HTTP Code | Error Message                  | Cause                              | Solution                          |
| --------- | ------------------------------ | ---------------------------------- | --------------------------------- |
| 400       | `Missing required field: text` | The `text` field is missing        | Provide a non-empty `text` string |
| 401       | `Invalid or missing API token` | Missing or incorrect token         | Check the `Authorization` header  |
| 413       | `Payload too large`            | Input text exceeds 2000 characters | Reduce the input size             |
| 500       | `Internal server error`        | Unexpected error                   | Try again or contact support      |

---

### 🧪 Example (curl)

```bash
curl -X POST https://api.cognitia.ai/v1/summarize \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
  -d '{"text": "In recent years, renewable energy sources have gained traction as the world faces growing concerns over climate change..."}'
```

#### 📘 Response

```json
{
  "summary": "Renewable energy is growing globally as governments invest in sustainable alternatives."
}
```

---

### 💡 Use Cases

- Summarize long articles, blog posts, or research papers

- Auto-generate previews for content platforms

- Provide concise summaries in customer dashboards

---

### 🛑 Limitations

- Input must be **under 2000 characters**

- Summarization is extractive + generative (hybrid)

- Supports **English and French** only

---

Looking for sentiment or bias analysis?
Check out our other endpoints:

- [Sentiment Analysis](./sentiment.md)

- [Bias Detection](./bias.md)
