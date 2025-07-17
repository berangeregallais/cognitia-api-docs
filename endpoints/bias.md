# Detect Bias

The `detect-bias` endpoint identifies potential **biases, stereotypes, or harmful language** in a given text.  
It flags content that may be discriminatory, unbalanced, or ethically problematic.

---

## 📌 POST /detect-bias

Base URL: <https://api.cognitia.ai/v1/detect-bias>

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
  "text": "Women are naturally less suited for technical jobs."
}
```

| Field | Type   | Required | Description                               |
| ----- | ------ | -------- | ----------------------------------------- |
| text  | string | ✅ yes    | The text to analyze (max 1500 characters) |

---

### 📤 Response

#### ✅ Success – 200 OK

```json
{
  "biased": true,
  "categories": ["gender bias", "stereotyping"],
  "explanation": "This sentence contains gender-based stereotypes suggesting women are less capable in technical fields."
}
```

| Field       | Type      | Description                                       |
| ----------- | --------- | ------------------------------------------------- |
| biased      | boolean   | Whether bias was detected                         |
| categories  | string\[] | Types of bias (e.g. `gender bias`, `racial bias`) |
| explanation | string    | Short explanation of the bias                     |

---

#### ❌ Error Responses

| HTTP Code | Error Message                  | Cause                         | Solution                          |
| --------- | ------------------------------ | ----------------------------- | --------------------------------- |
| 400       | `Missing required field: text` | The `text` field is missing   | Provide a non-empty `text` string |
| 401       | `Invalid or missing API token` | Missing or incorrect token    | Check the `Authorization` header  |
| 413       | `Payload too large`            | Input exceeds 1500 characters | Reduce the input length           |
| 500       | `Internal server error`        | Server-side failure           | Try again or contact support      |

---

### 🧪 Example (curl)

```bash
curl -X POST https://api.cognitia.ai/v1/detect-bias \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
  -d '{"text": "Immigrants are taking all the jobs."}'
```

#### 📘 Response

```json
{
  "biased": true,
  "categories": ["xenophobia", "economic bias"],
  "explanation": "This statement generalizes and blames a group of people, which is a form of bias."
}
```

---

### 💡 Use Cases

- Editorial and content moderation

- AI alignment and safety layers

- Auditing user-generated content

- Ethical compliance in media platforms

---

### 🛑 Limitations

- Detection is probabilistic, not deterministic

- Cultural/linguistic nuances may affect accuracy

- Only available for **English** (French coming soon)

---

Explore other endpoints:

- [Sentiment Analysis](/endpoints/sentiment.md)

- [Summarize Text](/endpoints/summarize.md)
