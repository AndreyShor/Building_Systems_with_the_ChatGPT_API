# Building Systems with the OpenAI API

A production-oriented customer service pipeline built with the **OpenAI Python SDK v1.x**, inspired by the [DeepLearning.AI — Building Systems with the ChatGPT API](https://www.deeplearning.ai/courses/chatgpt-building-system/) course.

## What this covers

| Lesson | Concept | Modernised technique |
|--------|---------|---------------------|
| L1 | Chat format & tokens | `client.chat.completions.create()`, `tiktoken` |
| L2 | Input classification | Structured JSON via `response_format` |
| L3 | Moderation & safety | `client.moderations.create()` + `omni-moderation-latest` |
| L4 | Chain-of-Thought reasoning | Inner monologue with delimiter parsing |
| L5 | Chained prompts | Multi-step pipeline: extract → lookup → respond |

## Quick start

```bash
# 1. Clone
git clone <your-repo-url>
cd <repo-name>

# 2. Install dependencies
pip install -r requirements.txt

# 3. Set your API key
cp .env.example .env
# Edit .env and add your OpenAI API key

# 4. Open the notebook
jupyter notebook customer_service_pipeline.ipynb
```

## Key API changes (old → new)

| Old (course) | New (SDK v1.x) |
|---|---|
| `openai.ChatCompletion.create(...)` | `client.chat.completions.create(...)` |
| `response.choices[0].message["content"]` | `response.choices[0].message.content` |
| `openai.Moderation.create(...)` | `client.moderations.create(...)` |
| `text-moderation-stable` | `omni-moderation-latest` |
| `gpt-3.5-turbo` (course default) | `gpt-4o-mini` (current recommended) |

## Project structure

```
.
├── customer_service_pipeline.ipynb   # Main notebook
├── requirements.txt
├── .env.example
└── README.md
```

## Requirements

- Python >= 3.10
- OpenAI API key

---

*Built at Accenture · Inspired by DeepLearning.AI*
