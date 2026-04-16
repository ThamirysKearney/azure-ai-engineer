# Domain 06 — Information Extraction & Knowledge Mining

> **Exam Weight:** 10-15% (Bobby says 10-15%, official guide says 15-20%)  
> **Bobby Russell Episode:** 6  
> **Study Days:** 42-45 (Phase 2, Week 9)

---

## ⚠️ Bobby Russell Says

> "This group accounts for 10 to 15% of the exam."  
> Note: Lower than the official guide. Still important — don't skip it.

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_document_intelligence.md` | Prebuilt (11 models), custom, composed, OCR | Day 42 |
| `02_ai_search.md` | Index, Indexer, Skillset, Query types, Projections | Day 43 |
| `03_vector_semantic_search.md` | Semantic ranking, vector index, hybrid search | Day 44 |
| `04_content_understanding.md` | Multimodal extraction, normalization, tokenization | Day 44 |

---

## 🧠 Service Selection — Information Extraction (CRITICAL)

| You Need To... | Use This |
|----------------|---------|
| Extract data from invoices, receipts, IDs | **Document Intelligence — Prebuilt Models** |
| Extract YOUR custom fields from documents | **Document Intelligence — Custom Extraction** |
| Classify document types automatically | **Document Intelligence — Custom Classification** |
| Combine multiple custom models | **Document Intelligence — Composed Model** |
| Analyze document structure (tables, layout) | **Document Intelligence — Layout Model** |
| Index and search large document collections | **Azure AI Search** |
| Add AI enrichment during indexing | **Azure AI Search — Skillsets** |
| Search by meaning not just keywords | **Azure AI Search — Semantic Ranking** |
| Search by vector similarity | **Azure AI Search — Vector Search** |
| Extract from text + images + video + audio | **Azure Content Understanding** |

---

## 📄 Document Intelligence

### Model Hierarchy

```
Document Intelligence
│
├── Prebuilt Models (no training — ready to use)
│   ├── 11 models available (Bobby: "be familiar with all 11")
│   ├── Invoice
│   ├── Receipt
│   ├── ID Document
│   ├── Business Card
│   ├── W-2 Tax Form
│   ├── Health Insurance Card
│   ├── Marriage Certificate
│   ├── Credit/Debit Card
│   ├── Bank Statement
│   ├── Pay Stub
│   └── Layout (tables, text, structure — ANY document)
│
├── Custom Models (you label and train)
│   ├── Custom Extraction    ← extract YOUR specific fields
│   ├── Custom Classification ← classify document type
│   ├── Custom Template     ← fixed layout documents
│   └── Custom Neural       ← varied layouts, deep learning
│
└── Composed Models
    └── Combines multiple custom models
        Routes each document to correct model automatically
```

> **Bobby says:** "Be familiar with the 11 prebuilt models.
> Understanding what each model is designed to extract will help
> you choose the right model and prepare for your exam."

---

### Prebuilt Models — What Each Extracts

| Model | Extracts | Use Case |
|-------|---------|---------|
| **Invoice** | Vendor, amount, date, line items | Accounts payable automation |
| **Receipt** | Merchant, items, total, date | Expense management |
| **ID Document** | Name, DOB, ID number, expiry | Identity verification |
| **Business Card** | Name, company, email, phone | Contact management |
| **W-2 Tax Form** | Employer, wages, tax withheld | Tax processing |
| **Health Insurance Card** | Member ID, plan, group number | Healthcare admin |
| **Marriage Certificate** | Names, date, location | Legal documentation |
| **Credit/Debit Card** | Card number, expiry, name | Payment processing |
| **Bank Statement** | Account, transactions, balance | Financial analysis |
| **Pay Stub** | Employer, earnings, deductions | Payroll verification |
| **Layout** | Tables, paragraphs, structure | Any document type |

> **Exam pattern:**
> "Extract vendor name and total from supplier invoices. Which model?"
> ✅ Invoice prebuilt model
> ❌ Layout model — that extracts structure, not invoice-specific fields

---

### Custom Model Types (Bobby: "know custom template, neural, and composed")

| Model Type | Best For | Uses Deep Learning |
|------------|---------|-------------------|
| **Custom Template** | Fixed layout documents — forms with same structure | No |
| **Custom Neural** | Varied layouts — documents with different formats | Yes |
| **Custom Extraction** | Extract specific fields you define | Depends |
| **Custom Classification** | Identify what type of document it is | Yes |
| **Composed** | Route mixed document types to correct model | Depends |

> **Exam pattern:**
> "Documents have varying layouts — sometimes portrait, sometimes landscape.
> Which custom model?"
> ✅ Custom Neural (handles varied layouts using deep learning)
> ❌ Custom Template (only works for fixed consistent layouts)

---

### Building a Custom Model (Bobby: "know the full process")

> "Make sure you understand the full process of building a custom
> document intelligence model, starting with creating a project
> in Document Intelligence Studio."

| Step | Action |
|------|--------|
| 1 | Create project in Document Intelligence Studio |
| 2 | Upload sample documents |
| 3 | Label documents accurately (fields you want to extract) |
| 4 | Choose model type — Template, Neural, Classification |
| 5 | Train the model |
| 6 | Evaluate accuracy |
| 7 | Publish the model |
| 8 | Test using prediction endpoint |

> **Bobby says:** "Know how to label documents accurately as this
> directly impacts the quality of your models."

---

### OCR in Document Intelligence (Bobby: "know the differences")

> "Know the differences between higher resolution OCR and standard
> OCR, especially how it improves text extraction from scanned
> images and PDFs."

| Property | Standard OCR | Higher Resolution OCR |
|----------|--------------|-----------------------|
| **Best for** | Clear, clean documents | Scanned images, low quality PDFs |
| **Accuracy** | Good for standard docs | Better for difficult content |
| **Processing** | Faster | Slower but more accurate |
| **Use case** | Digital documents | Scanned physical documents |

---

### Document Layout Model (Bobby: "remember this concept")

> "Document Intelligent Layout Model is an advanced machine
> learning-based document analysis API. Document structure layout
> analysis is the process of analyzing a document to extract
> regions of interest and their interrelationships."

| Property | Detail |
|----------|--------|
| **What it does** | Analyzes structure of ANY document |
| **Extracts** | Tables, paragraphs, headings, regions of interest |
| **API type** | Cloud-based — Document Intelligence Cloud |
| **Use case** | When you need structure, not specific field extraction |

> **Bobby says:** "Recall the two types of roles in a document layout."
> **(2) Speculative — Bobby did not explicitly name these in the transcript.**
> Study the Microsoft documentation for document layout roles.

---

### Document Classification — Deep Learning

> **Bobby says:** "Be familiar with how deep learning is used to
> combine layout and language features for accurate document
> classification. Understand how page-by-page classification works
> and why it helps improve precision."

| Concept | Detail |
|---------|--------|
| **Deep learning** | Combines layout + language features together |
| **Page-by-page** | Classifies each page individually — improves precision |
| **Why it helps** | A single document can contain multiple document types |

---

### Microsoft Customer Data Policies (Bobby: "keep that in mind")

> "Know the Microsoft policies on customer data while using
> these various custom models."

| Policy Area | What to Know |
|-------------|-------------|
| **Data storage** | Your training data is stored in your Azure storage |
| **Data privacy** | Microsoft does not use your data to train base models |
| **Data deletion** | You can delete your custom model and training data |
| **Compliance** | Subject to your Azure subscription terms |

---

## 🔍 Azure AI Search

> **Bobby says:** "Azure AI Search acts as the connection between
> your raw data sources and the client app that sends queries
> and receives results."

### The 5 Key Components

| Component | Role | Detail |
|-----------|------|--------|
| **Data Source** | Where documents live | Blob Storage, SQL, Cosmos DB, SharePoint |
| **Indexer** | Reads and enriches data | Runs skillset, populates index automatically |
| **Skillset** | AI enrichment pipeline | OCR, NER, language detection, translation |
| **Index** | Searchable structure | What users query against |
| **Knowledge Store** | Optional enriched data store | Saves enriched data as tables, files, objects |

---

### Search Pipeline Flow

```
Data Source → Indexer → Skillset → Index ← Queries from App
(Blob/SQL/     (reads +   (AI           (searchable
 Cosmos)        enriches)  enrichment:    structure)
                           OCR, NER,
                           language)
                               ↓
                        Knowledge Store
                        (projections saved
                         as tables/files/objects)
```

---

### Creating a Data Source and Index (Bobby: "know the steps")

> "You'll want to understand how to define and create data sources,
> set up indexes using C and configuring fields with attributes
> like searchable, filterable, and sortable."

#### Index Field Attributes

| Attribute | What It Enables |
|-----------|----------------|
| **Searchable** | Field can be queried using full-text search |
| **Filterable** | Field can be used in filter expressions |
| **Sortable** | Results can be sorted by this field |
| **Facetable** | Field can be used for faceted navigation |
| **Retrievable** | Field is returned in search results |
| **Key** | Unique identifier for each document |

> **Exam pattern:**
> "Users need to filter results by document category.
> Which attribute must the category field have?"
> ✅ Filterable
> ❌ Searchable (that enables text search, not filtering)

---

### Creating and Running an Indexer

> **Bobby says:** "Know the steps for creating an indexer,
> as well as the data source, index, and skillsets that are
> part of the indexer definition."

| Step | Action |
|------|--------|
| 1 | Define data source in Azure AI Search resource |
| 2 | Create index with field definitions and attributes |
| 3 | Create skillset with enrichment steps |
| 4 | Create indexer — links data source + index + skillset |
| 5 | Run indexer — starts data ingestion and enrichment |
| 6 | Monitor indexer status |
| 7 | View indexed documents in search explorer |
| 8 | Verify data source in Azure AI portal — Data Sources tab |

---

### Query Types — Simple vs Full (Bobby: "know the two types")

> "Know the two types of search solutions, which are simple and full."

| Type | Syntax | Best For |
|------|--------|---------|
| **Simple** | Basic keyword matching | Quick searches, most common |
| **Full (Lucene)** | Advanced — Boolean, wildcards, fuzzy | Complex, precise queries |

---

### Query Parameters (Bobby: "know the common parameters")

> "Know the common parameters submitted with a query:
> query search, query type, search fields, select, and search mode."

| Parameter | What It Does | Example |
|-----------|-------------|---------|
| **search** | The search term | `search=invoice` |
| **queryType** | Simple or full Lucene | `queryType=full` |
| **searchFields** | Which fields to search | `searchFields=title,content` |
| **select** | Which fields to return | `select=title,date,author` |
| **searchMode** | Any or all terms must match | `searchMode=all` |
| **$filter** | OData filter expression | `$filter=rating ge 4` |
| **$orderby** | Sort results | `$orderby=date desc` |
| **$top** | Number of results to return | `$top=10` |

---

### Query Syntax Examples

```bash
# Simple keyword
search=invoice

# Filter using OData syntax
$filter=rating ge 4

# Sort results
$orderby=date desc

# Wildcard
search=inv*

# Boolean — full Lucene
search=invoice AND (overdue OR pending)

# Fuzzy search — tolerates typos
search=invoce~1

# Search specific fields only
search=invoice&searchFields=title,content

# Return only certain fields
search=*&select=title,date,status
```

---

### Query Processing — 4 Stages (Bobby: "know the four stages")

> "Know the four stages in which queries are processed."

| Stage | What Happens |
|-------|-------------|
| **1. Query Parsing** | Break query into terms and operators |
| **2. Lexical Analysis** | Normalize terms — lowercase, remove stop words, stemming |
| **3. Document Retrieval** | Find matching documents in index |
| **4. Scoring** | Rank documents by relevance score |

---

### Projections — Knowledge Store (Bobby: "understand projections")

> "Projections are views of enriched documents that can be saved
> as tables, files, and objects, making it easier for tools to
> access and use that data."

| Projection Type | Stored As | Best For |
|----------------|----------|---------|
| **Table projections** | Azure Table Storage | Tabular data analysis, Power BI |
| **Object projections** | Azure Blob Storage (JSON) | Full enriched document |
| **File projections** | Azure Blob Storage (binary) | Images extracted from documents |

> **Exam pattern:**
> "Save enriched document data for Power BI analysis.
> Which projection type?"
> ✅ Table projections
> ❌ File projections (those are for images/binary files)

> **Bobby says:** "Be familiar with how to read projected data
> from the containers or tables where they are being stored."

---

### Built-in Skillset Skills

| Skill | What It Does |
|-------|-------------|
| **OCR** | Extract text from images embedded in documents |
| **Language Detection** | Detect language of content |
| **Text Split** | Chunk large documents into smaller pieces |
| **Entity Recognition** | Find people, places, organizations |
| **Key Phrase Extraction** | Pull out main topics |
| **Sentiment** | Rate sentiment of content |
| **Translation** | Translate to target language |
| **Image Analysis** | Describe images found in documents |
| **Custom Web API** | Call your own enrichment endpoint |

---

## 🔎 Search Types Comparison

| Type | How It Works | Best For |
|------|-------------|---------|
| **Keyword** | Exact word matching | Known terms, structured queries |
| **Semantic** | Understands meaning and re-ranks | Natural language questions |
| **Vector** | Embedding similarity search | Conceptual similarity |
| **Hybrid** | Keyword AND vector combined | Best overall results |

---

### Semantic Ranking (Bobby: "remember the steps")

> "Remember the steps to implement semantic ranking."

| Step | Action |
|------|--------|
| 1 | Enable semantic search on Azure AI Search resource |
| 2 | Create a semantic configuration |
| 3 | Define priority fields — title, keyword, content fields |
| 4 | Add semantic configuration name to query |
| 5 | Set queryType to semantic |
| 6 | Results are re-ranked by semantic relevance |

---

### Vector Index (Bobby: "know the steps and requirements")

> "Understand the steps for creating a vector index and know that
> vector stores require more fields besides vector fields.
> For example, a key field ID is an index requirement."

| Required Field | Why |
|----------------|-----|
| **Key field (ID)** | Required — unique identifier for every document |
| **Vector field** | Stores the embedding vector |
| **Content field** | Original text (for hybrid search) |
| **Metadata fields** | Title, date, source, etc. |

| Step | Action |
|------|--------|
| 1 | Generate embeddings for your documents |
| 2 | Create index with vector field configuration |
| 3 | Define vector field — dimensions, algorithm |
| 4 | Include required key field |
| 5 | Upload documents with embeddings |
| 6 | Query using vector search |

---

### Document Q&A Integration (Bobby: "know how documents are used")

> "Know how different types of documents are used in question
> and answer projects."

| Document Type | How It Is Processed |
|---------------|-------------------|
| **Word / PDF with headings** | Headings and tables used to generate Q&A pairs |
| **Structured files (docs, PDFs)** | Processed based on layout and formatting |
| **Unstructured text (TXT)** | Processed as continuous content |
| **TSV files** | Tab-separated Q&A pairs imported directly |
| **XLS files** | Spreadsheet data imported as Q&A pairs |

---

## 🌐 Azure Content Understanding (Bobby: "know how different content types are processed")

> "Understand how different types of content like documents,
> images, videos, and audio are processed using Azure AI
> Content Understanding."

### Content Types Supported

| Content Type | Processing |
|--------------|-----------|
| **Documents** | OCR, layout analysis, entity extraction |
| **Images** | Visual analysis, object detection, caption generation |
| **Video** | Frame extraction, transcription, scene analysis |
| **Audio** | Speech-to-text, speaker identification |

---

### Content Extraction Pipeline (Bobby: "grasp the steps involved")

> "It's important to grasp the steps involved in content extraction,
> including pre-processing techniques like normalization, tokenization,
> as well as semantic analysis."

| Stage | What Happens |
|-------|-------------|
| **Pre-processing** | Normalization — clean and standardize input |
| **Tokenization** | Break content into processable units |
| **Semantic Analysis** | Extract meaning and relationships |
| **Structured Output** | Generate structured insights |

---

### How Structured Insights Are Used (Bobby: "know how consumers use them")

> "Know how the structured insights are used by consumers
> like search tools, databases, apps, and files."

| Consumer | How They Use Insights |
|----------|----------------------|
| **Search tools** | Index extracted entities and topics |
| **Databases** | Store structured field values |
| **Applications** | Display results and trigger workflows |
| **Files** | Export enriched data for reporting |

---

## 🧠 Memory Palace — The Information Extraction Factory

**Building 9 in your Robot Factory Town:**

```
🏭 BUILDING 9: INFORMATION EXTRACTION FACTORY

┌─────────────────────────────────────────────────┐
│  FLOOR 3 — CONTENT UNDERSTANDING LAB            │
│  4 conveyor belts:                              │
│    📄 Documents belt → OCR + layout             │
│    🖼️ Images belt → visual analysis             │
│    🎥 Video belt → frames + transcription       │
│    🎵 Audio belt → speech-to-text               │
│  3 processing stations:                         │
│    [NORMALIZE] → [TOKENIZE] → [ANALYZE]         │
│  Output goes to: Search, DB, Apps, Files        │
├─────────────────────────────────────────────────┤
│  FLOOR 2 — AZURE AI SEARCH CONTROL ROOM         │
│  Pipeline on wall:                              │
│    SOURCE→INDEXER→SKILLSET→INDEX→QUERY          │
│  Knowledge Store vault in corner:               │
│    3 drawers: TABLES | OBJECTS | FILES          │
│  Query desk with syntax cards:                  │
│    [SIMPLE] [FULL LUCENE]                       │
│    [SEMANTIC] [VECTOR] [HYBRID]                 │
│  4-stage processor: PARSE→ANALYZE→RETRIEVE→SCORE│
├─────────────────────────────────────────────────┤
│  FLOOR 1 — DOCUMENT INTELLIGENCE STUDIO         │
│  Shelf with 11 prebuilt model boxes:            │
│    Invoice Receipt ID-Doc Business-Card W-2     │
│    Health-Insurance Marriage Credit-Card        │
│    Bank-Statement Pay-Stub Layout               │
│  Custom workshop with 4 stations:               │
│    [TEMPLATE] [NEURAL] [EXTRACTION] [CLASSIFY]  │
│  Composed model router: sends doc to right model│
│  OCR machines: STANDARD and HIGH-RESOLUTION     │
└─────────────────────────────────────────────────┘
```

---

## 🎯 Exam Priority Checklist

### Must Know

- [ ] 11 prebuilt Document Intelligence models — know what each extracts
- [ ] Layout model = structure of ANY document
- [ ] Custom Template vs Custom Neural — fixed vs varied layouts
- [ ] Full custom model building process — 8 steps in order
- [ ] Azure AI Search 5 components — Data Source, Indexer, Skillset, Index, Knowledge Store
- [ ] Index field attributes — Searchable, Filterable, Sortable, Facetable, Key
- [ ] 4 query processing stages — Parse, Lexical Analysis, Retrieve, Score
- [ ] 2 query types — Simple and Full Lucene
- [ ] Query parameters — search, queryType, searchFields, select, searchMode
- [ ] 3 projection types — Table, Object, File

### Should Know

- [ ] Standard OCR vs Higher Resolution OCR
- [ ] Custom Neural model uses deep learning for varied layouts
- [ ] Page-by-page classification improves precision
- [ ] Semantic ranking — 6 steps to implement
- [ ] Vector index requirements — key field is mandatory
- [ ] Hybrid search = keyword + vector combined
- [ ] Content Understanding — 4 content types
- [ ] Content extraction stages — Normalize, Tokenize, Analyze

### Good to Know

- [ ] Microsoft customer data policies for custom models
- [ ] Document layout roles — two types exist
- [ ] How TSV and XLS are processed in Q&A projects
- [ ] How structured insights are consumed — search, DB, apps, files
- [ ] Indexer creation steps — 8 steps in order

---

## ❓ Quick Self-Test

**Q1. Extract vendor name, date, and total from supplier invoices.
Which Document Intelligence model?**

<details>
<summary>▶ Click to reveal answer</summary>

**Invoice prebuilt model**

| Property | Detail |
|----------|--------|
| No training needed | Ready to use immediately |
| Extracts | Vendor, amount, date, line items, tax |
| Alternative | Layout model only gets structure, not invoice-specific fields |

</details>

---

**Q2. Documents arrive in many different formats and layouts.
Custom Template or Custom Neural?**

<details>
<summary>▶ Click to reveal answer</summary>

**Custom Neural**

| Model | Best For |
|-------|---------|
| **Custom Template** | Fixed, consistent layouts |
| **Custom Neural** | Varied, changing layouts — uses deep learning |

</details>

---

**Q3. Name the 4 stages of query processing in Azure AI Search.**

<details>
<summary>▶ Click to reveal answer</summary>

| Stage | What Happens |
|-------|-------------|
| **1. Query Parsing** | Break query into terms |
| **2. Lexical Analysis** | Normalize — lowercase, stemming |
| **3. Document Retrieval** | Find matching documents |
| **4. Scoring** | Rank by relevance |

</details>

---

**Q4. What are the 3 projection types in a Knowledge Store?**

<details>
<summary>▶ Click to reveal answer</summary>

| Type | Stored As | Best For |
|------|----------|---------|
| **Table** | Azure Table Storage | Power BI, tabular analysis |
| **Object** | Blob Storage JSON | Full enriched document |
| **File** | Blob Storage binary | Extracted images |

</details>

---

**Q5. Users search in natural language — "documents about
contract renewals". Which search type gives best results?**

<details>
<summary>▶ Click to reveal answer</summary>

**Semantic Search** or **Hybrid Search**

| Type | Why |
|------|-----|
| Semantic | Understands meaning, not just keywords |
| Hybrid | Combines keyword + vector — best overall |

Keyword search would only match exact words "contract" and "renewals".
Semantic/hybrid finds conceptually related documents too.

</details>

---

**Q6. A vector index is required to have a key field.
True or false?**

<details>
<summary>▶ Click to reveal answer</summary>

**True**

> Bobby says: "Vector stores require more fields besides vector fields.
> A key field ID is an index requirement."

Every Azure AI Search index requires a key field regardless of type.

</details>

---

**Q7. A field needs to appear in filter expressions like
`$filter=category eq 'legal'`. Which attribute must it have?**

<details>
<summary>▶ Click to reveal answer</summary>

**Filterable**

| Attribute | Enables |
|-----------|---------|
| Searchable | Full-text search |
| **Filterable** | **Use in $filter expressions** |
| Sortable | Use in $orderby |
| Facetable | Faceted navigation |

</details>

---

**Q8. How many prebuilt Document Intelligence models exist?
Name at least 5.**

<details>
<summary>▶ Click to reveal answer</summary>

**11 prebuilt models**

| Model | Extracts |
|-------|---------|
| Invoice | Vendor, amount, date |
| Receipt | Merchant, items, total |
| ID Document | Name, DOB, ID number |
| Business Card | Name, company, contact |
| W-2 Tax Form | Employer, wages, tax |
| Health Insurance Card | Member ID, plan |
| Marriage Certificate | Names, date, location |
| Credit/Debit Card | Card number, expiry |
| Bank Statement | Transactions, balance |
| Pay Stub | Earnings, deductions |
| Layout | Structure of any document |

</details>

---

*Domain 06 — Merged: Bobby Russell Episode 6 and technical reference*  
*Part of the AI-102 study repository*