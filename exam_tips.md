# AI-102 Exam Tips & Question Strategies

> Source: Bobby Russell Exam Prep Guide + official Microsoft skill guide

---

## 🎯 Question Strategy

1. **Eliminate first** — cross out obviously wrong answers before picking
2. **Watch for "most appropriate"** — Microsoft wants the *best* answer, not just a correct one
3. **Service keywords** — each question usually has a clue word pointing to the right service
4. **Scenario questions** — read the business requirement carefully, then match to service
5. **"Which service would you use to..."** — these are the most common question type

---

## 🔑 Critical Service Selection Table

| Task | Service | Keyword to watch for |
|------|---------|----------------------|
| Analyze text sentiment | Azure Language | "positive/negative", "opinion" |
| Extract entities from text | Azure Language (NER) | "names, places, orgs" |
| Detect PII in text | Azure Language (PII) | "personal data", "redact" |
| Custom entity types | Azure Language (Custom NER) | "YOUR specific types" |
| Translate text | Azure Translator | "language to language" |
| Speech to text | Azure Speech (STT) | "spoken → written" |
| Text to speech | Azure Speech (TTS) | "written → spoken", SSML |
| Analyze images (tags, captions) | Azure Vision (Image Analysis) | "what's in the photo" |
| Extract text from images | Azure Vision (Read API / OCR) | "text in image", "handwriting" |
| Verify/identify faces | Azure Face API | "who is this person", "verify identity" |
| Custom image classification | Custom Vision | "YOUR own categories" |
| Detect objects with bounding boxes | Custom Vision (Object Detection) | "WHERE is the object" |
| Analyze video | Video Indexer | "video", "scene", "transcript from video" |
| Extract from invoices/receipts | Document Intelligence (Prebuilt) | "invoice", "receipt", "ID card" |
| Extract from custom forms | Document Intelligence (Custom) | "YOUR specific form" |
| Search documents | Azure AI Search | "search", "index", "knowledge mining" |
| Generate text/images | Azure OpenAI | "generate", "GPT", "DALL-E" |
| Build AI agents | Foundry Agent Service | "autonomous", "take actions", "tools" |
| Grounded answers from YOUR data | RAG pattern | "based on our documents", "citations" |

---

## ⚠️ Common Exam Traps

### Trap 1: Prebuilt NER vs Custom NER vs PII
- **Prebuilt NER** → recognizes common entities (people, places, orgs, dates) — no training needed
- **Custom NER** → YOU define entity types specific to your business (e.g., "ProductCode", "ClaimNumber")
- **PII Detection** → specifically finds personal data (SSN, email, phone, address) — for compliance/redaction

### Trap 2: Image Classification vs Object Detection
- **Classification** = "What IS this image?" → whole-image label → `cat` or `dog`
- **Object Detection** = "WHERE are things?" → bounding boxes → `[cat at top-left] [dog at bottom-right]`

### Trap 3: Fine-tuning vs RAG vs Prompt Engineering
- **Prompt engineering** → just write better prompts — no cost, no training
- **RAG** → inject YOUR documents as context at query time — factual accuracy from your data
- **Fine-tuning** → actually retrain model weights — use for style/format/behavior, NOT for factual data

### Trap 4: Serverless vs Managed deployment
- **Serverless** → pay per token, no infrastructure, scales automatically
- **Managed** → dedicated capacity, predictable cost, more control → use when you need guaranteed throughput

### Trap 5: Docker vs Kubernetes
- **Single container** → Docker / Azure Container Instances (ACI)
- **Multiple containers with dependencies** → Kubernetes (AKS)

### Trap 6: Azure AI Search — Indexer vs Index vs Skillset
- **Data Source** → where your documents live (Blob, SQL, Cosmos)
- **Indexer** → reads from data source, runs skillset, populates index
- **Skillset** → AI enrichment pipeline (OCR, NER, language detection, etc.)
- **Index** → the searchable structure users query against
- **Knowledge Store** → saves enriched data separately for later use

---

## 🔐 Authentication Methods (memorize all 3)

| Method | Header/Pattern | Use Case |
|--------|---------------|----------|
| API Key (Subscription Key) | `Ocp-Apim-Subscription-Key` | Simple apps, testing |
| Bearer Token | `Authorization: Bearer <token>` | Short-lived access |
| Entra ID (Azure AD) | `DefaultAzureCredential()` | Enterprise, managed identity |

> **Bobby says:** "Each Azure AI service provides you **two keys**." (for rotation without downtime)

---

## 📊 Azure Monitor — Know These 4 Components

| Component | Purpose | Example |
|-----------|---------|---------|
| Metrics | Real-time numerical data | Requests/sec, latency |
| Alerts | Notify when threshold exceeded | Alert when errors > 10/min |
| Diagnostic Settings | Route logs to storage/analysis | Log all API calls |
| Activity Log | Audit trail — who did what | "User deleted resource at 3pm" |

---

## 🛡️ Content Safety — Categories & Severity

Categories: **Hate | Violence | Sexual | Self-harm**

Severity levels: **0** (safe) → **2** → **4** → **6** (high/blocked)

Features:
- **Content Filters** → block by category + severity threshold
- **Blocklists** → custom banned words/phrases
- **Prompt Shields** → detect prompt injection attacks (user, document, third-party)
- **Groundedness Detection** → check if response is grounded in source data

---

## 🤖 Responsible AI — 6 Principles (FRPITA)

| # | Principle | What it means |
|---|-----------|---------------|
| 1 | **F**airness | No discrimination |
| 2 | **R**eliability & Safety | Works consistently |
| 3 | **P**rivacy & Security | Protects data |
| 4 | **I**nclusiveness | Works for everyone |
| 5 | **T**ransparency | Explainable decisions |
| 6 | **A**ccountability | Humans are responsible |

---

## 💡 RAG Flow (must know this perfectly)

```
1. Upload documents → Azure Blob Storage
2. Azure AI Search indexes docs (chunks + embeddings)
3. User asks question
4. App converts question → embedding
5. Vector search finds relevant chunks
6. Chunks + question → sent to LLM as context
7. LLM generates answer based ONLY on provided context
8. App returns grounded answer with citations
```

---

## 📝 Document Intelligence Model Hierarchy

```
Document Intelligence
├── Prebuilt Models (no training needed)
│   ├── Invoice
│   ├── Receipt
│   ├── ID Document
│   ├── Business Card
│   ├── W-2 Tax Form
│   └── Layout (tables, text structure — any document)
├── Custom Models (you train)
│   ├── Custom Extraction (extract YOUR specific fields)
│   └── Custom Classification (classify document type)
└── Composed Models (combine multiple custom models)
```

---

## 🔍 AI Search Query Syntax (exam will test this)

```bash
# Simple query
search=hotel

# Filter
$filter=rating ge 4

# Order by
$orderby=rating desc

# Wildcard
search=hot*

# Full Lucene (AND/OR)
search=hotel AND (pool OR spa)

# Fuzzy (misspelling tolerance)
search=hotl~1
```

Search types:
- **Keyword** → exact word match
- **Semantic** → understands meaning, better results
- **Vector** → mathematical similarity (embeddings)
- **Hybrid** → keyword + vector combined (best results)

---

*Last updated: April 2026*