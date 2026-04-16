# Domain 02 — Generative AI Solutions

> **Exam Weight:** 15-30% (Bobby says this is the LARGEST group)  
> **Bobby Russell Episode:** 2  
> **Study Days:** 27-32 (Phase 2, Weeks 6-7)

---

## ⚠️ Bobby Russell Says

> "This is your largest group with 25 to 30 percent of your exam
> content coming from it."

This is HIGHER than the official study guide says (15-20%).  
**This is the single most important domain. Prioritize it.**

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_azure_openai.md` | GPT models, Chat API, DALL-E, Embeddings | Day 28 |
| `02_prompt_engineering.md` | Zero/one/few-shot, CoT, system prompts, 7 techniques | Day 29 |
| `03_rag_pattern.md` | RAG architecture, CEEP pipeline, vector search | Day 30 |
| `04_fine_tuning.md` | When to fine-tune, evaluation metrics, cost | Day 31 |
| `05_responsible_genai.md` | Content filters, model reflection, monitoring | Day 32 |

---

## 🏗️ Azure AI Foundry Architecture (Bobby: "understand this workflow")

```
Azure OpenAI Resource (access to GPT, DALL-E, Embeddings)
    ↓
Azure AI Foundry (unified platform)
    ├── Project Section (model catalog, your projects)
    └── Management Section (configuration, resources)
         ↓
    Foundry Project Resource ←→ Foundry Hub
```

**Three ways to use Foundry:** Web portal, SDK, or CLI

| Fact | Detail |
|------|--------|
| Foundry is built on | Other Azure services underneath |
| Project connects to | Foundry Hub |
| Three access methods | Web portal, SDK, CLI |

---

## 📐 Deploying Hub + Project (Bobby: "identify the steps")

| Step | Action |
|------|--------|
| 1 | Create Azure AI Foundry Hub |
| 2 | Configure connections (Azure OpenAI, Storage, etc.) |
| 3 | Create a Project within the Hub |
| 4 | Deploy models to the Project |
| 5 | Get endpoint URL and API key |

> **Exam pattern:** "What is the correct order to set up a Foundry project?"  
> Answer: Hub FIRST → then Project → then Model deployment

---

## 🤖 Model Types (Bobby: "be able to summarize")

| Model | Best For | Key Feature | Exam Trap |
|-------|----------|-------------|-----------|
| **GPT-4** | Complex reasoning, best quality | Most capable, most expensive | Best for language and code |
| **GPT-3.5-turbo** | Fast, cheap, good enough | Best cost/performance ratio | Use when budget matters |
| **Embeddings** | Converting text to vectors | Used in RAG for semantic search | NOT for generating text |
| **DALL-E** | Generate images from text | Creates NEW images | ❌ NOT a search engine for images |

> **Bobby specifically warns:**  
> "DALL-E is NOT a search system for finding appropriate images.  
> It's an AI model that generates NEW images."

> **Bobby also says:**  
> "The newer GPT models are generally the best choice for all  
> language and code generation tasks."

---

## 🤖 Approach Selection (CRITICAL exam topic)

| Approach | Use When | Cost | Try In This Order |
|----------|----------|------|-------------------|
| **Prompt Engineering** | Simple customization, tone, format | Free | FIRST |
| **RAG** | Need factual answers from YOUR own data | Medium | SECOND |
| **Fine-tuning** | Need specific behavior, style, or output format | High | THIRD |
| **Train from scratch** | Almost never on this exam | Very high | LAST RESORT |

> **Bobby says:**  
> "Fine-tuning is an expensive and time-consuming process that  
> should be reserved for your most essential cases."

> **Exam trap:**  
> RAG ≠ Fine-tuning.  
> RAG = inject data at QUERY time (data stays separate from model).  
> Fine-tuning = change model WEIGHTS (data baked into model).

---

## 📡 Chat Completions API — Message Roles

| Role | Purpose | Example |
|------|---------|---------|
| `system` | Persistent instructions — defines behavior for whole conversation | "You are a medical assistant" |
| `user` | The human's message | "What causes headaches?" |
| `assistant` | The model's previous response — used for multi-turn context | "Headaches can be caused by..." |

### Python SDK Pattern (memorize this structure)

```python
from azure.ai.inference import ChatCompletionsClient
from azure.core.credentials import AzureKeyCredential

client = ChatCompletionsClient(
    endpoint="https://your-endpoint.openai.azure.com/",
    credential=AzureKeyCredential("your-key")
)

response = client.complete(
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "What is Azure?"}
    ],
    temperature=0.7,
    max_tokens=500
)

print(response.choices[0].message.content)
```

---

## 🎛️ Key Parameters (Bobby: "summarize parameters to control generative behavior")

> "Be able to summarize the parameters: max response, top P, and past message history."

| Parameter | Effect | Low Value | High Value |
|-----------|--------|-----------|------------|
| `temperature` | Randomness and creativity | 0 = deterministic, factual | 1+ = creative, varied |
| `top_p` | Diversity of token sampling | Conservative choices | More varied choices |
| `max_tokens` | Maximum response length | Short answers | Long answers |
| `frequency_penalty` | Reduces repetition | Allows repetition | Penalizes repeated words |
| `presence_penalty` | Encourages new topics | Stays on topic | Explores new topics |
| `past_messages` | Context window for conversation | Less memory | More memory |

> **Exam pattern:**  
> "Customer support bot needs consistent, factual answers. Which setting?"  
> ✅ Low temperature (0.1-0.3)  
> ❌ High temperature

---

## ✍️ Prompt Engineering — 7 Techniques (Bobby: "make sure you understand EACH")

| # | Technique | What It Does | Example |
|---|-----------|-------------|---------|
| 1 | **Clear instructions** | Tell AI exactly what you want | "Write a 3-paragraph summary" |
| 2 | **Primary/supporting/grounding content** | Give AI data to work with | "Based on this document: [text]" |
| 3 | **Providing cues** | Start the answer for the AI | "The three benefits are: 1." |
| 4 | **Output composition** | Specify response format | "Reply in JSON format" |
| 5 | **System message** | Set AI role and behavior | "You are a medical assistant" |
| 6 | **Few-shot learning** | Give examples first | Show 3 input → output examples |
| 7 | **Chain of thought** | Ask AI to reason step by step | "Think through this step by step" |

**Mnemonic: "Can People Play On Stage For Cash"**

| Letter | Technique |
|--------|-----------|
| **C** | Clear instructions |
| **P** | Primary content |
| **P** | Providing cues |
| **O** | Output composition |
| **S** | System message |
| **F** | Few-shot learning |
| **C** | Chain of thought |

> **Bobby emphasizes code generation:**  
> "Understanding how you can use prompt engineering to generate  
> clear, concise code is important. Make sure you are comfortable  
> with using prompts to break down code."

---

## 🔄 RAG Flow (Bobby: "know the phases and recall the steps")

### High-Level Flow

| Step | What Happens |
|------|-------------|
| 1 | Upload documents to Azure Blob Storage |
| 2 | Azure AI Search indexes documents — chunks and embeddings |
| 3 | User asks a question |
| 4 | App converts question to embedding |
| 5 | Vector search finds relevant document chunks |
| 6 | Relevant chunks and question sent to LLM as context |
| 7 | LLM generates answer ONLY from provided context |
| 8 | App returns grounded answer with citations |

### Data Pipeline — CEEP (Bobby: "understand those processes")

> "Documents are either pushed or pulled into the data pipeline,  
> and the data pipeline processes each document individually."

| Step | Name | What Happens |
|------|------|-------------|
| 1 | **C**hunk | Split large documents into smaller pieces |
| 2 | **E**nrich | Add metadata, extract entities, add context |
| 3 | **E**mbed | Convert text chunks to vector numbers |
| 4 | **P**ersist | Store vectors in search index |

**Mnemonic: CEEP** (Chunk, Enrich, Embed, Persist)

---

## 📊 Evaluation (Bobby: "understand the foundation")

### Requirements

| Requirement | Detail |
|-------------|--------|
| **Test dataset format** | CSV or JSON-L — memorize BOTH |
| **Also required** | Azure OpenAI connection |

> **Exam pattern:**  
> "What format must test data be in for evaluation?"  
> ✅ CSV or JSON-L  
> ❌ XML or YAML

### Evaluation Targets

| Target | What It Evaluates |
|--------|------------------|
| Model + Prompt | How well the model responds to your prompt |
| Dataset | How well the model handles your test data |
| Prompt Flow | How well the full flow performs end-to-end |

### Built-in Evaluation Metrics

| Metric | Measures |
|--------|---------|
| **Groundedness** | Is the response based on source documents? |
| **Relevance** | Does the response answer the question? |
| **Coherence** | Is the response well-written and logical? |
| **Fluency** | Is the language natural and grammatically correct? |
| **Similarity** | How close is response to a reference answer? |

---

## 🔗 SDK Integration (Bobby: "crucial for building robust applications")

> "Make sure you're familiar with inserting the necessary connection strings."

### Where to Find Things

| What | Where to Find It |
|------|-----------------|
| Project connection string | Project → Overview section |
| Azure OpenAI credentials | Models and Endpoints section |
| Agent configuration | Agent section |

---

## 🔧 Prompt Flow (Bobby: "know the steps to implement")

> "Prompt flow is a development tool designed to streamline the  
> entire development lifecycle of AI applications powered by LLMs."

| Feature | Detail |
|---------|--------|
| **What it is** | Visual workflow designer for LLM apps |
| **What it does** | Chain steps: input → prompt → LLM → output → validation |
| **Testing** | Test and evaluate flows before deploying |
| **Deployment** | Deploy flows as endpoints |

---

## 📈 Monitoring and Diagnostics (Bobby: "know the features")

| Feature | What It Does | Where to Find It |
|---------|-------------|-----------------|
| **Tracing** | Track individual requests through the system | Azure AI Foundry portal |
| **Application Insights** | Collect feedback and performance data | Linked from Foundry |
| **Autoscale settings** | Scale based on demand | Azure Portal → Resource → Overview → Essentials |
| **GenAI dashboard** | Pre-built metrics dashboard | Foundry portal — requires tracing enabled |

> **Where is autoscale?**  
> Azure Portal → Resource → Overview tab → Essentials section → Autoscale link

---

## 🔄 Model Update Policies (Bobby: "understand the difference")

| Policy | What Happens | When to Use |
|--------|-------------|-------------|
| **Manual upgrade** | YOU choose which version to deploy | Production — you control versions |
| **Automatic update** | Azure updates to latest default version | Development — convenient |

> **Exam pattern:**  
> "Production environment needs version control. Which update policy?"  
> ✅ Manual upgrade  
> ❌ Automatic update — risky in production

---

## 🪞 Model Reflection (Bobby: "understand these concepts")

| Concept | What It Means |
|---------|--------------|
| **Model reflection** | AI checks its own response for accuracy |
| **Base model selection** | Choose the right foundation model first |
| **Pre-production evaluation** | Test thoroughly BEFORE deploying |
| **Post-production monitoring** | Monitor continuously AFTER deploying |

---

## 📦 Edge Deployment

> "Deploy containers for use on local and edge devices."

| Property | Detail |
|----------|--------|
| **What it does** | Run AI models locally without internet |
| **How** | Docker containers |
| **Requirements** | Docker installed, container image, license key |

---

## 🎭 Multi-Model Orchestration (Bobby: "understand why agents matter")

```
User query → Orchestrator Agent
    → GPT-4 for reasoning and text
    → DALL-E for image generation
    → Embeddings for semantic search
    → Combines all results
    → Returns unified response
```

---

## ⚠️ Important Notes from Bobby

| Topic | Bobby's Note |
|-------|-------------|
| **DALL-E** | NOT a search system — it GENERATES new images |
| **Corporate emails** | Personal emails (Outlook, Gmail) not accepted for Azure OpenAI access |
| **Code generation** | Understand the structure: task, prompt, completion elements |
| **Fine-tuning** | Expensive and time-consuming — last resort only |

---

## 🧠 Memory Palace — The GenAI Workshop

**Building 5 in your Robot Factory Town:**

```
🏭 BUILDING 5: THE GENAI WORKSHOP (7 Workstations)

┌─────────────────────────────────────────────┐
│  WORKSTATION 7 — Director's Office          │
│  Orchestrator assigns tasks:                │
│    GPT-4 worker → DALL-E worker             │
│    Embeddings worker                        │
├─────────────────────────────────────────────┤
│  WORKSTATION 6 — CCTV Room                 │
│  Tracing screens everywhere                 │
│  Application Insights dashboard             │
│  Autoscale settings in Essentials tab       │
├─────────────────────────────────────────────┤
│  WORKSTATION 5 — Gold Machine               │
│  Sign: "Try prompts → then RAG → then me"  │
│  Sign: "EXPENSIVE — last resort only"       │
├─────────────────────────────────────────────┤
│  WORKSTATION 4 — Exam Room                 │
│  Test papers: CSV and JSON-L format ONLY   │
│  Three judges: Groundedness Relevance       │
│               Coherence                     │
├─────────────────────────────────────────────┤
│  WORKSTATION 3 — Art Corner                │
│  DALL-E artist painting NEW images         │
│  Sign: "WE CREATE — WE DON'T SEARCH"       │
├─────────────────────────────────────────────┤
│  WORKSTATION 2 — Control Panel             │
│  Temperature DIAL: cold=factual hot=creative│
│  Length SLIDER: max tokens                 │
│  Variety KNOB: top_p                       │
├─────────────────────────────────────────────┤
│  WORKSTATION 1 — Assembly Line             │
│  CHUNK → ENRICH → EMBED → PERSIST          │
│  (CEEP — the RAG pipeline)                 │
└─────────────────────────────────────────────┘
```

---

## 🎯 Exam Priority Checklist

### Must Know

- [ ] RAG pipeline — CEEP (Chunk, Enrich, Embed, Persist)
- [ ] Foundry architecture — Hub → Project → Deployment → Endpoint
- [ ] 7 prompt engineering techniques — Can People Play On Stage For Cash
- [ ] Model types — GPT-4 vs GPT-3.5 vs DALL-E vs Embeddings
- [ ] Evaluation requires CSV or JSON-L test data
- [ ] Fine-tuning = last resort — expensive
- [ ] Parameters — temperature, top_p, max_tokens, past_messages
- [ ] DALL-E generates NEW images — does NOT search for existing ones

### Should Know

- [ ] SDK integration — connection strings from Project Overview
- [ ] Where to find credentials — Models and Endpoints section
- [ ] Update policies — manual vs automatic
- [ ] Prompt Flow — purpose and workflow
- [ ] Autoscale location — Azure Portal → Resource → Overview → Essentials
- [ ] Approach order — Prompt Engineering → RAG → Fine-tuning

### Good to Know

- [ ] Model reflection — four concepts
- [ ] Edge deployment with containers
- [ ] Multi-model orchestration with agents
- [ ] Tracing and Application Insights setup
- [ ] Three ways to deploy — serverless, managed, edge

---

## ❓ Quick Self-Test

**Q1. What are the 4 steps in the RAG data pipeline?**

<details>
<summary>▶ Click to reveal answer</summary>

| Step | Name | What Happens |
|------|------|-------------|
| 1 | **Chunk** | Split documents into smaller pieces |
| 2 | **Enrich** | Add metadata and context |
| 3 | **Embed** | Convert to vector numbers |
| 4 | **Persist** | Store in search index |

Mnemonic: **CEEP**

</details>

---

**Q2. DALL-E is used to search for existing images. True or false?**

<details>
<summary>▶ Click to reveal answer</summary>

**False.**

| Property | Detail |
|----------|--------|
| What DALL-E does | Generates NEW images from text descriptions |
| What it does NOT do | Search for or retrieve existing images |

> Bobby specifically warns about this trap.

</details>

---

**Q3. What format must evaluation test data be in?**

<details>
<summary>▶ Click to reveal answer</summary>

**CSV or JSON-L** — memorize both formats.

| Format | Example |
|--------|---------|
| CSV | Comma-separated values file |
| JSON-L | One JSON object per line |

❌ XML, YAML, or Excel are NOT accepted.

</details>

---

**Q4. Name the 7 prompt engineering techniques in order.**

<details>
<summary>▶ Click to reveal answer</summary>

**Can People Play On Stage For Cash**

| # | Technique |
|---|-----------|
| 1 | Clear instructions |
| 2 | Primary and supporting content |
| 3 | Providing cues |
| 4 | Output composition |
| 5 | System message |
| 6 | Few-shot learning |
| 7 | Chain of thought |

</details>

---

**Q5. Company needs GPT responses to match their legal writing style.
RAG or Fine-tuning?**

<details>
<summary>▶ Click to reveal answer</summary>

**Fine-tuning.**

| Approach | Use When |
|----------|---------|
| RAG | Need factual answers from your data |
| **Fine-tuning** | **Need specific behavior, style, or format** |

Writing style = model behavior change = Fine-tuning.

</details>

---

**Q6. Which temperature setting for a customer support bot
that must give consistent answers?**

<details>
<summary>▶ Click to reveal answer</summary>

**Low temperature — 0.1 to 0.3**

| Temperature | Effect |
|-------------|--------|
| 0.0 to 0.3 | Predictable, consistent, factual |
| 0.7 to 1.0 | Creative, varied, less predictable |
| Above 1.0 | Very random and creative |

Customer support needs consistency → low temperature.

</details>

---

**Q7. Where do you find the project connection string?**

<details>
<summary>▶ Click to reveal answer</summary>

**Project → Overview section**

| What | Location |
|------|----------|
| Project connection string | Project → Overview section |
| Azure OpenAI credentials | Models and Endpoints section |
| Autoscale settings | Azure Portal → Resource → Overview → Essentials |

</details>

---

**Q8. What is the correct approach order from cheapest to most expensive?**

<details>
<summary>▶ Click to reveal answer</summary>

| Order | Approach | Cost |
|-------|----------|------|
| 1st | Prompt Engineering | Free |
| 2nd | RAG | Medium |
| 3rd | Fine-tuning | High |
| 4th | Train from scratch | Very high |

Always try the cheapest option first.

</details>

---

*Domain 02 — Updated with Bobby Russell Episode 2 exam tips*  
*Part of the AI-102 study repository*