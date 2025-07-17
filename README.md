# Cognitia API ![Beta](https://img.shields.io/badge/status-beta-yellow)

> ⚠️ This documentation is part of a **fictional portfolio project** created by Berangere Gallais, freelance technical writer & documentation engineer.  
> It is not affiliated with a real product or company.

---

## 🧭 Table of Contents

- [What is Cognitia?](#-what-is-cognitia)
- [Features](#-features)
- [Quick Start](#-quick-start)
- [Available Endpoints](#-available-endpoints)
- [Tools & Format](#-tools--format)
- [Postman & Testing](#-postman--testing)
- [FAQ](#-faq)
- [Support](#-support)
- [About](#-about)

---

## 🤖 What is Cognitia?

Cognitia is a REST API that processes raw text and returns actionable insights in JSON format.  
It’s designed for developers and teams building tools that need **language understanding**.

You send us text. We send you back meaning.

---

## ✨ Features

- 🔍 **Sentiment Analysis** — Classify tone as positive, neutral, or negative
- 🧠 **Summarization** — Condense long text into clear, concise summaries
- 🚨 **Bias Detection** — Detect potential stereotypes or harmful language

Supports **English and French** (except Bias → English only).

---

## 🚀 Quick Start

👉 [Get started in 3 minutes](./getting-started.md)

```bash
curl -X POST https://api.cognitia.ai/v1/analyze-sentiment \
  -H "Authorization: Bearer YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"text": "I love using Cognitia — it saves me hours!"}'
```

---

## 📚 Available Endpoints

| Feature            | Endpoint                  | Docs                                        |
| ------------------ | ------------------------- | ------------------------------------------- |
| Sentiment Analysis | `POST /analyze-sentiment` | [Read the docs →](/endpoints/sentiment.md) |
| Summarization      | `POST /summarize`         | [Read the docs →](/endpoints/summarize.md) |
| Bias Detection     | `POST /detect-bias`       | [Read the docs →](/endpoints/bias.md)      |

---

## 🛠 Tools & Format

- REST over HTTPS

- JSON request/response

- OpenAPI spec available (for import in Postman)

---

## 🧰 Postman & Testing

You can import the OpenAPI JSON spec into [Postman](https://www.postman.com) or [Insomnia](https://insomnia.rest/)
for a GUI-based exploration of all endpoints.

---

## ❓ FAQ

Check out the [FAQ page](./faq.md) for answers to common questions.

---

## 💬 Support

- Contact: <support@cognitia.ai>

- FAQ: [See common issues](/faq.md)

- Status page: [status.cognitia.ai](https://status.cognitia.ai)

---

## 🧠 About

Cognitia is built for modern teams who care about ethical, usable, and smart language tools.
It’s your shortcut to deeper understanding — in content, comments, emails, reviews, and more.
(Cognitia is a fictional AI product designed to demonstrate technical documentation skills.
Made with ❤️ by Berangere Gallais — technical writer & documentation engineer).
