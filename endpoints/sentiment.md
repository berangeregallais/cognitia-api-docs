# Sentiment Analysis

The `analyze-sentiment` endpoint returns the **emotional polarity** of a given text input.  
It classifies the text as `positive`, `neutral`, or `negative` and provides a confidence score.

---

## 📌 POST /analyze-sentiment

Base URL: <https://api.cognitia.ai/v1/analyze-sentiment>

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

#### Body

```json
{
  "text": "This is a wonderful product!"
}
```

| Field | Type   | Required | Description                               |
| ----- | ------ | -------- | ----------------------------------------- |
| text  | string | ✅ yes    | The text to analyze (max 1000 characters) |

---

### 📤 Response

#### Success – 200 OK

```json
{
  "sentiment": "positive",
  "score": 0.92
}
```

| Field     | Type   | Description                          |
| --------- | ------ | ------------------------------------ |
| sentiment | string | `positive`, `neutral`, or `negative` |
| score     | float  | Confidence score between 0 and 1     |

---

#### ❌ Error Responses

| HTTP Code | Error Message                  | Cause                                   | Solution                                              |
| --------- | ------------------------------ | --------------------------------------- | ----------------------------------------------------- |
| 400       | `Missing required field: text` | The `text` field is missing             | Provide a non-empty `text` string in the request body |
| 401       | `Invalid or missing API token` | Missing or wrong `Authorization` header | Check your token and header format                    |
| 413       | `Payload too large`            | Text exceeds 1000 characters            | Shorten your input                                    |
| 500       | `Internal server error`        | Something went wrong server-side        | Try again later or contact support                    |

---

### 🧪 Example (curl)

```bash
curl -X POST https://api.cognitia.ai/v1/analyze-sentiment \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
  -d '{"text": "The design is elegant, but the app is too slow."}'
```

#### 📘 Response

```json
{
  "sentiment": "neutral",
  "score": 0.61
}
```

---

### 🧠 Use Cases

- Content moderation (filter negative reviews)

- Social media monitoring

- Product feedback analysis

- Customer support triage

---

### 🛑 Limitations

- Input is limited to **1000 characters**

- Only supports **English and French** (beta)

---

Looking for bias detection or summarization?
Check out our other endpoints:

- [Summarize](/endpoints/summarize.md)

- [Detect Bias](/endpoints/bias.md)
