# Getting Started

Welcome to Cognitia API!

This guide will help you make your **first successful API call** in just a few minutes.

---

## 📝 Step 1 — Sign up

To get access, create a free developer account at:

👉 [https://cognitia.ai/signup](https://cognitia.ai/signup)

You’ll receive an **API token** via your dashboard after signing up.

---

## 🔑 Step 2 — Get your API token

Your token is a long alphanumeric key used to authenticate your requests.  
You must include it in the `Authorization` header of every API call.

Example:

```makefile
Authorization: Bearer YOUR_API_TOKEN
```

Keep it secret. Don’t share it in public repos or frontend code.

---

## 🧪 Step 3 — Make your first API call

Try the Sentiment Analysis endpoint using `curl`:

```bash
curl -X POST https://api.cognitia.ai/v1/analyze-sentiment \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
  -d '{"text": "I absolutely love this product! Great experience."}'
```

✅ Expected response:

```json
{
  "sentiment": "positive",
  "score": 0.94
}
```

---

## 🧰 Optional — Use Postman

If you prefer GUI-based testing, you can import our [OpenAPI JSON spec](../openapi-coqnitia.json) into [Postman](https://www.postman.com).
It includes all endpoints and example requests.

---

## 🔄 What’s next?

Explore the available endpoints:

- [Analyze Sentiment](./endpoints/sentiment.md)

- [Summarize Text](./endpoints/summarize.md)

- [Detect Bias](./endpoints/bias.md)

---

Need help? Visit the [FAQ](../faq.md) or contact support at <support@cognitia.ai>.
