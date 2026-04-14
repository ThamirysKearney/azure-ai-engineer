# AI-102 Study Plan 

## Exam Date: June 25, 2026
## Study Period: April 13 – June 24, 2026
## Total Study Days: 53 weekdays
## Total Hours: 205 hours
## Max Hours Per Day: 5h (never more)
## Weekend Study: NONE

---

## 📊 Phase Overview

| Phase | Dates | Days | Hours/Day | Total | Focus |
|-------|-------|------|-----------|-------|-------|
| **1: Foundation** | Apr 13 – May 8 | 20 days | 2h | 40h | AI-900 concepts |
| **2: Deep Dive** | May 9 – Jun 13 | 26 days | 5h | 130h | AI-102 domains |
| **3: Final Prep** | Jun 15 – Jun 24 | 7 days | 5h | 35h | Review + practice |
| **TOTAL** | | **53 days** | | **205h** | |

---

## 🎯 Study Structure Based on Exam Prep Guide

### Bobby Russell's 6 Episodes = Your 6 Study Blocks

| Episode | Exam Domain | Weight | Study Hours |
|---------|-------------|--------|-------------|
| Ep 1 | Plan & Manage Azure AI | 20-25% | 30h |
| Ep 2 | Generative AI Solutions | 15-20% | 35h |
| Ep 3 | Agent Solutions | 5-10% | 15h |
| Ep 4 | Computer Vision | 10-15% | 25h |
| Ep 5 | NLP Solutions | 15-20% | 25h |
| Ep 6 | Info Extraction & Knowledge Mining | 15-20% | 25h |
| — | Practice Exams & Final Review | — | 20h |
| — | AI-900 Foundation (built into above) | — | 30h |

---

## ==============================
## PHASE 1: FOUNDATION (Apr 13 – May 8)
## 20 weekdays × 2 hours = 40 hours
## ==============================

### WEEK 1: Apr 13-17 (Mon-Fri) — What is AI?

#### Day 1 (Mon Apr 13) — 2h
**Topic: AI, ML, and Generative AI Fundamentals**
- Read: "Introduction to AI concepts" module (40 min)
- Read: "Introduction to generative AI and agents" module (37 min)
- Review: Memory Palace #01 (AI Intro)
- Remaining time: Self-test + glossary terms

**What Bobby Russell says you need to know:**
> "Be able to provide a brief overview of Azure AI Foundry 
> and how it benefits developers"

**Key concepts (beginner definitions):**
- **AI** = Making machines smart
- **ML** = Machines learn from examples
- **Generative AI** = AI that creates new content
- **Agent** = AI that can take actions (not just talk)

---

#### Day 2 (Tue Apr 14) — 2h
**Topic: Machine Learning Types**
- Read: "Introduction to machine learning concepts" (1h 33min)
- Focus on: Classification, Regression, Clustering
- Review: Memory Palace #02 (ML Concepts)

**Key concepts:**
- **Classification** = Sort into categories (spam/not spam)
- **Regression** = Predict a number (house price)
- **Clustering** = Find natural groups (customer segments)
- **Supervised** = Learn from labeled examples
- **Unsupervised** = Find patterns without labels

---

#### Day 3 (Wed Apr 15) — 2h
**Topic: Azure AI Platform Overview**
- Read: "Get started with Microsoft Foundry" module (50 min)
- Watch: Bobby Russell Episode 1 (12 min) — **watch TWICE**
- Study: Azure resource hierarchy (Subscription → Resource Group → Resource)
- Review: Memory Palace #03 (Azure ML)

**What Bobby says:**
> "All paths lead to a project. Take time to become familiar 
> with navigating through the Foundry portal."

**Key concepts:**
- **Subscription** = Your billing account
- **Resource Group** = Folder for related resources
- **Resource** = Individual service (like Azure Vision)
- **Foundry Hub** = Top container for AI projects
- **Foundry Project** = Workspace for one AI app
- **Endpoint** = URL where you call your AI service
- **API Key** = Password to access the service

---

#### Day 4 (Thu Apr 16) — 2h
**Topic: Azure AI Services Overview (Which Service for What)**
- Study the Service Selection table (from exam_tips.md)
- Watch: John Savill "Azure AI Services Overview" (~30 min)
- Create your own decision tree on paper

**What Bobby says:**
> "Know the use cases for computer vision, language services, 
> information extraction. Be able to list appropriate AI solutions 
> along with their use cases."

**CRITICAL TABLE — Memorize this:**

| Task | Service |
|------|---------|
| Analyze text sentiment | Azure Language |
| Extract entities from text | Azure Language |
| Detect PII in text | Azure Language |
| Translate text | Azure Translator |
| Speech to text | Azure Speech |
| Text to speech | Azure Speech |
| Analyze images | Azure Vision |
| Custom image classification | Custom Vision |
| Extract from invoices | Document Intelligence |
| Search documents | Azure AI Search |
| Generate text/images | Azure OpenAI |
| Build AI agents | Foundry Agent Service |

---

#### Day 5 (Fri Apr 17) — 2h
**Topic: Week 1 Review + Responsible AI**
- Read: Responsible AI principles
- Review all 5 days of notes
- Retake module knowledge checks
- Create flashcards for weak areas

**What Bobby says:**
> "You'll need to know the six principles and understand 
> what each specifically covers."

**The 6 Principles (memorize):**
1. **Fairness** — No discrimination
2. **Reliability & Safety** — Works consistently
3. **Privacy & Security** — Protects data
4. **Inclusiveness** — Works for everyone
5. **Transparency** — Explainable decisions
6. **Accountability** — Humans are responsible

**Mnemonic: "FRPITA"**

---

### WEEK 2: Apr 20-24 (Mon-Fri) — NLP & Speech Fundamentals

#### Day 6 (Mon Apr 20) — 2h
**Topic: NLP Fundamentals**
- Read: "Introduction to NLP concepts" (30 min)
- Read: "Get started with NLP in Foundry" (45 min)
- Review: Memory Palace #05 (NLP)

**Key concepts:**
- **Tokenization** = Breaking text into pieces
- **Embedding** = Converting words to numbers that capture meaning
- **NER** = Named Entity Recognition (find names, places, orgs)
- **Sentiment** = Is the text positive/negative/neutral?

---

#### Day 7 (Tue Apr 21) — 2h
**Topic: Azure Language Service Deep Dive**
- Read: "Analyze text with Azure Language" module (46 min)
- Study: API request/response examples
- Practice: Match task → API method

**What Bobby says:**
> "Detecting and redacting sensitive information such as PII 
> or PHI would use PII detection. If you're looking to extract 
> categories of information using a model specific to your data, 
> you'd use custom named entity recognition."

**Key distinction (exam trap!):**
- **Prebuilt NER** = Recognizes common entities (people, places)
- **Custom NER** = You train it for YOUR specific entity types
- **PII detection** = Specifically finds personal data

---

#### Day 8 (Wed Apr 22) — 2h
**Topic: Speech Services**
- Read: "Introduction to AI speech concepts" (28 min)
- Read: "Get started with speech in Foundry" (41 min)
- Study: SSML examples

**Key concepts:**
- **STT (Speech-to-Text)** = Converts spoken words to written text
- **TTS (Text-to-Speech)** = Converts written text to spoken audio
- **SSML** = XML code that controls HOW text is spoken
  - Speed, pitch, pauses, emphasis
- **Custom Speech** = Train for specific accents or terminology

---

#### Day 9 (Thu Apr 23) — 2h
**Topic: Translation Services**
- Read: "Translate text and speech" module (48 min)
- Study: Translation API examples
- Understand: Custom translation models

**Key concepts:**
- **Azure Translator** = Converts text between languages
- **Speech Translation** = Real-time spoken language translation
- **Custom Translator** = Train on YOUR domain vocabulary
- **Document Translation** = Translate entire files (PDFs, etc.)

---

#### Day 10 (Fri Apr 24) — 2h
**Topic: Week 2 Review**
- Review days 6-9
- Watch: Bobby Russell Episode 5 (NLP episode) when available
- Practice: "Which service for this NLP task?" scenarios
- Retake knowledge checks

---

### WEEK 3: Apr 27 – May 1 (Mon-Fri) — Computer Vision & Video

#### Day 11 (Mon Apr 27) — 2h
**Topic: Computer Vision Fundamentals**
- Read: "Introduction to computer vision concepts" (34 min)
- Read: "Get started with CV in Foundry" (50 min)
- Study: Image Analysis API features

**What Bobby says:**
> "Azure AI Vision is used to tag visual features, detect color 
> schemes, detect domain-specific content, and detect brands. 
> The Face API is used to verify identities."

**Key concepts:**
- **Image Analysis** = Tags, captions, objects, color
- **Face API** = Detect, verify, identify faces
- **OCR** = Extract text from images
- **Custom Vision** = Train your own image classifier

---

#### Day 12 (Tue Apr 28) — 2h
**Topic: Image Analysis & OCR**
- Read: "Analyze images" module (44 min)
- Read: "Read text in images" module (45 min)
- Watch: Video walkthrough of Vision API demo

**Key concepts:**
- **Read API** = Best for documents, mixed text, handwriting
- **Image Analysis** = Best for photos, real-world images
- **JSON response** = Contains tags, objects, captions with confidence scores

---

#### Day 13 (Wed Apr 29) — 2h
**Topic: Custom Vision**
- Read: "Classify images" module (1h 3min)
- Watch: Custom Vision training video walkthrough

**Key concepts:**
- **Image Classification** = "What is this image?" (cat/dog/bird)
- **Object Detection** = "WHERE are objects in this image?" (bounding boxes)
- **Training** = Upload labeled images → train → evaluate → publish
- **Iteration** = Each training run is an iteration

---

#### Day 14 (Thu Apr 30) — 2h
**Topic: Object Detection & Video Analysis**
- Read: "Detect objects in images" module (1h 5min)
- Read: "Analyze video" module (48 min — partial)
- Study: Video Indexer capabilities

**Key concepts:**
- **Video Indexer** = Extracts insights from video
  - Face identification
  - OCR (text in video)
  - Scene segmentation
  - Topic detection
  - Spoken language transcription
- **Spatial Analysis** = Detect people movement in video

---

#### Day 15 (Fri May 1) — 2h
**Topic: Week 3 Review**
- Review days 11-14
- Watch: Bobby Russell Episode 4 (Computer Vision)
- Practice: "Which Vision API for this?" scenarios
- Create comparison table: Vision vs Custom Vision vs Face vs Video Indexer

---

### WEEK 4: May 4-8 (Mon-Fri) — Information Extraction & Phase 1 Wrap

#### Day 16 (Mon May 4) — 2h
**Topic: Document Intelligence**
- Read: "Use prebuilt Document Intelligence models" (21 min)
- Read: "Extract data from forms" (49 min)
- Study: Prebuilt model types

**What Bobby says:**
> "Understand the four types of models: pre-trained document 
> analysis, pre-trained scenario-specific, custom extraction, 
> and custom classification."

**Key concepts:**
- **Prebuilt models** = Ready to use (invoice, receipt, ID card, business card)
- **Layout model** = Extracts tables, text, structure from any document
- **Custom model** = Train on YOUR specific forms
- **Composed model** = Combines multiple custom models

---

#### Day 17 (Tue May 5) — 2h
**Topic: Azure AI Search & Knowledge Mining**
- Read: "Create knowledge mining solution" (1h 8min)
- Study: Index, Indexer, Skillset concepts

**What Bobby says:**
> "Know the key strengths of Azure AI Search. You can execute 
> queries over an index, use its crawler capabilities, and 
> customize the indexing pipeline."

**Key concepts:**
- **Index** = Searchable structure of your documents
- **Indexer** = Process that reads data and populates the index
- **Skillset** = AI enrichment steps during indexing (OCR, NER, language detection)
- **Knowledge Store** = Saves enriched data for later use
- **Data Source** = Where documents live (Blob Storage, SQL, etc.)

---

#### Day 18 (Wed May 6) — 2h
**Topic: Content Understanding + Multimodal Extraction**
- Read: "Create multimodal analysis solution" (1h)
- Study: Content Understanding API

**Key concepts:**
- **Multimodal** = Analyzes text + images + tables together
- **Content Understanding** = Newer service for complex documents
- **OCR Pipeline** = Extract text from scanned documents
- **Entity extraction** = Find specific data in documents

---

#### Day 19 (Thu May 7) — 2h
**Topic: Phase 1 Comprehensive Review**
- Re-read ALL memory palace summaries (01-05)
- Create master service comparison chart
- Study: Bobby Russell Episode 1 again (focus on gaps)
- Review: All module knowledge checks

---

#### Day 20 (Fri May 8) — 2h
**Topic: First Practice Assessment**
- Take FREE Microsoft practice assessment
- Link: https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/?practice-assessment-type=certification
- Record your score
- List every wrong answer topic
- These gaps become priority topics for Phase 2

---

## ==============================
## PHASE 2: AI-102 DEEP DIVE (May 9 – Jun 13)
## 26 weekdays × 5 hours = 130 hours
## ==============================

### WEEK 5: May 9-15 — Domain 1: Plan & Manage (Bobby Ep. 1)

#### Day 21 (Mon May 9) — 5h
**Topic: Azure AI Foundry Platform Deep Dive**
- **Hour 1:** Re-watch Bobby Russell Episode 1 with notes
- **Hour 2:** Read "Plan and prepare to develop AI solutions" (1h)
- **Hour 3:** Study Foundry portal navigation (watch video walkthrough)
- **Hour 4:** Study: Hub → Project → Resource → Endpoint hierarchy
- **Hour 5:** Practice: Draw architecture diagrams from memory

**What Bobby says to focus on:**
> "When you come to the Foundry portal, all paths lead to a project."
> "Practice creating resources in the Azure AI Foundry portal."

---

#### Day 22 (Tue May 10) — 5h
**Topic: Model Selection & Deployment**
- **Hour 1:** Read "Choose and deploy models from catalog" (40 min)
- **Hour 2:** Study Model Catalog: Azure OpenAI vs open-source vs third-party
- **Hour 3:** Study deployment types: Serverless vs Managed
- **Hour 4:** Study: SDK and API patterns (Python code examples)
- **Hour 5:** Watch: John Savill "Model Deployment" video

**What Bobby says:**
> "There are over 1,700 models. Know that selecting the right one 
> is key to enabling the right capabilities, at the right price point, 
> and with the right protections."

**Key concepts:**
- **Model Catalog** = Library of available models
- **Model Benchmarks** = Compare model performance
- **Serverless** = Pay per use (no infrastructure to manage)
- **Managed** = Dedicated capacity (more control)
- **Quota** = Limits on tokens per minute

---

#### Day 23 (Wed May 11) — 5h
**Topic: SDKs, APIs, and Authentication**
- **Hour 1:** Study REST API structure (headers, body, response)
- **Hour 2:** Study Python SDK patterns (AzureKeyCredential, clients)
- **Hour 3:** Study 3 authentication methods
- **Hour 4:** Study: Endpoints and keys (how to find and use them)
- **Hour 5:** Practice: Read code and identify correct patterns

**What Bobby says:**
> "Make sure you spend extra time reviewing API structures."
> "Understand the three main ways to authenticate: subscription key, 
> token, or Entra ID."

**The 3 Authentication Methods (memorize):**

| Method | When to Use | Exam Keyword |
|--------|-------------|--------------|
| **API Key** (subscription key) | Simple apps, testing | `Ocp-Apim-Subscription-Key` header |
| **Token** | Short-lived access | `Authorization: Bearer <token>` |
| **Entra ID** (formerly Azure AD) | Enterprise, granular permissions | `DefaultAzureCredential()` |

**Python SDK pattern (memorize this structure):**
```python
from azure.core.credentials import AzureKeyCredential

# Pattern 1: API Key authentication
client = SomeAzureClient(
    endpoint="https://your-resource.azure.com/",
    credential=AzureKeyCredential("your-key")
)

# Pattern 2: Entra ID (managed identity)
from azure.identity import DefaultAzureCredential
client = SomeAzureClient(
    endpoint="https://your-resource.azure.com/",
    credential=DefaultAzureCredential()
)