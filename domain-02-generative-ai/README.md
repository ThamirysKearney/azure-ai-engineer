# Domain 02 — Generative AI Solutions

> **Exam Weight:** 15-20%
> **Bobby Russell Episode:** 2
> **Study Days:** 27-32 (Phase 2, Weeks 6-7)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_azure_openai.md` | GPT models, Chat API, DALL-E, Embeddings | Day 28 |
| `02_prompt_engineering.md` | Zero/one/few-shot, CoT, system prompts | Day 29 |
| `03_rag_pattern.md` | RAG architecture, vector search, chunking | Day 30 |
| `04_fine_tuning.md` | When to fine-tune, evaluation metrics | Day 31 |
| `05_responsible_genai.md` | Content filters, model reflection | Day 32 |

---

## 🧠 Key Exam Points

### What Bobby Russell says:
> "There are over 1,700 models. Selecting the right one is key to enabling the right capabilities, at the right price point, and with the right protections."

---

## 🤖 Approach Selection (CRITICAL exam topic)

| Approach | Use When | Cost |
|----------|----------|------|
| **Prompt Engineering** | Simple customization, tone, format | Free |
| **RAG** | Need factual answers from YOUR own data | Medium |
| **Fine-tuning** | Need specific behavior, style, or output format | High |
| **Train from scratch** | Almost never on this exam | Very high |

> **Exam trap:** RAG ≠ Fine-tuning. RAG = inject data at query time. Fine-tuning = change model weights.

---

## 📡 Chat Completions API — Message Roles

| Role | Purpose |
|------|---------|
| `system` | Persistent instructions — defines the assistant's behavior |
| `user` | The human's message |
| `assistant` | The model's previous response (for multi-turn context) |

---

## 🎛️ Key Parameters

| Parameter | Effect |
|-----------|--------|
| `temperature` | 0 = deterministic, 1 = creative/random |
| `top_p` | Controls diversity of token sampling |
| `max_tokens` | Limits response length |
| `frequency_penalty` | Reduces repetition |
| `presence_penalty` | Encourages new topics |

---

## 🔄 RAG Flow (memorize perfectly)

```
1. Upload docs → Azure Blob Storage
2. AI Search indexes docs (chunks + embeddings)
3. User asks question
4. App converts question → embedding
5. Vector search finds relevant chunks
6. Chunks + question → sent to LLM as context
7. LLM generates answer ONLY from provided context
8. App returns grounded answer with citations
```

---

## 📊 Evaluation Metrics (Domain 2)

| Metric | Measures |
|--------|---------|
| Groundedness | Is the response based on source documents? |
| Relevance | Does the response answer the question? |
| Coherence | Is the response well-written and logical? |
| Fluency | Is the language natural and grammatically correct? |
| Similarity | How close is the response to a reference answer? |

---

*Domain 02 — Part of the AI-102 study repository*
