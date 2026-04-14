# Domain 06 — Information Extraction & Knowledge Mining

> **Exam Weight:** 15-20%
> **Bobby Russell Episode:** 6
> **Study Days:** 42-45 (Phase 2, Week 9)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_document_intelligence.md` | Prebuilt, custom, composed models | Day 42 |
| `02_ai_search.md` | Index, Indexer, Skillset, Queries | Day 43 |
| `03_vector_semantic_search.md` | Semantic, vector, hybrid search | Day 44 |

---

## 🧠 Key Exam Points

Bobby says:
> "Understand the four types of models: pre-trained document analysis, pre-trained scenario-specific, custom extraction, and custom classification."
> "Know the key strengths of Azure AI Search. You can execute queries over an index, use its crawler capabilities, and customize the indexing pipeline."

---

## 📄 Document Intelligence Model Hierarchy

```
Document Intelligence
├── Prebuilt Models (no training needed)
│   ├── Invoice
│   ├── Receipt
│   ├── ID Document
│   ├── Business Card
│   ├── W-2 Tax Form
│   └── Layout (tables, text, structure — ANY document)
│
├── Custom Models (you label and train)
│   ├── Custom Extraction    ← extract YOUR specific fields
│   └── Custom Classification ← classify document type
│
└── Composed Models (combine multiple custom models)
    └── Routes to correct custom model per document type
```

> **Exam tip:** Layout model = analyze structure of ANY document. Prebuilt models = specific document types.

---

## 🔍 Azure AI Search Pipeline

```
Data Source → Indexer → Skillset → Index ← Queries
   (Blob/       (reads +   (AI          (searchable
    SQL/         enriches)  enrichment:   structure)
    Cosmos)                 OCR, NER,
                            language)
                               ↓
                        Knowledge Store
                        (enriched data saved
                         for analysis/export)
```

### The 5 Key Components

| Component | Role |
|-----------|------|
| **Data Source** | Where documents live (Blob, SQL, Cosmos, SharePoint) |
| **Indexer** | Reads from source, runs skillset, populates index |
| **Skillset** | AI enrichment pipeline (OCR, NER, language, translation) |
| **Index** | Searchable structure — what users query against |
| **Knowledge Store** | Optional: saves enriched data separately |

---

## 🔎 Query Syntax (exam will test this)

```bash
# Simple keyword
search=invoice

# Filter (OData syntax)
$filter=rating ge 4

# Sort results
$orderby=date desc

# Wildcard
search=inv*

# Boolean (full Lucene)
search=invoice AND (overdue OR pending)

# Fuzzy search (typo tolerance)
search=invoce~1
```

---

## 🧠 Search Types Comparison

| Type | How | Best for |
|------|-----|---------|
| **Keyword** | Exact word match | Known terms, structured queries |
| **Semantic** | Understand meaning + re-rank | Natural language questions |
| **Vector** | Embedding similarity | Conceptual/semantic similarity |
| **Hybrid** | Keyword + vector combined | Best overall — use this! |

---

## 🏗️ Built-in Skillset Skills (know these)

| Skill | What it does |
|-------|-------------|
| OCR | Extract text from images in documents |
| Language Detection | Detect language of content |
| Text Split | Chunk documents |
| Entity Recognition | Find people, places, orgs |
| Key Phrase Extraction | Pull out main topics |
| Sentiment | Rate sentiment of content |
| Translation | Translate to target language |
| Image Analysis | Describe images in documents |
| Custom Web API | Call your own enrichment endpoint |

---

*Domain 06 — Part of the AI-102 study repository*