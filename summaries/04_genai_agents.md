# Memory Palace #4: Generative AI & Agents

## í¾­ The Theater of Creation (Your Mental Palace)

Imagine a **magical theater** where actors create entirely new plays, never performed before.

---

## í¾¬ Act 1: What is Generative AI?

**Visual:** A stage where actors create NEW performances (not just recite memorized lines)

**Traditional AI (Analytical):**
**Visual:** Judge with a magnifying glass
**Job:** Analyze existing content
**Examples:**
- Classify email as spam
- Detect objects in photo
- Analyze sentiment of review

**Generative AI:**
**Visual:** Artist with blank canvas
**Job:** CREATE new content
**Examples:**
- Write email response
- Generate image from description
- Compose music

**Key difference:**
- Analytical = "What IS this?"
- Generative = "CREATE something like this"

---

## í·  The Brain: Large Language Models (LLMs)

**What they are:** AI models trained on huge amounts of text

**Famous LLMs:**
- **GPT-4** (OpenAI) - Best overall
- **GPT-3.5** (OpenAI) - Faster, cheaper
- **Llama** (Meta) - Open source
- **Phi-3** (Microsoft) - Small, efficient

**Exam tip:** Different models = different costs, speeds, capabilities

---

## í²¬ The Script: Prompts

### The Three Types of Prompts:

#### 1. System Prompt - sets the AI role/behavior for entire conversation
#### 2. User Prompt - your actual question/request
#### 3. Assistant Response - LLM's generated answer

### Prompt Engineering Techniques:

| Technique | Example | When to use |
|-----------|---------|-------------|
| **Zero-shot** | "Translate to French: Hello" | Simple, well-known tasks |
| **One-shot** | Give 1 example first | Novel format |
| **Few-shot** | Give 2-5 examples | Complex pattern |
| **Chain-of-thought** | "Think step-by-step" | Reasoning tasks |

### Prompt Parameters:

| Parameter | Range | What it controls |
|-----------|-------|------------------|
| **Temperature** | 0.0 - 2.0 | Randomness/creativity |
| **Top-p** | 0.0 - 1.0 | Diversity of word choices |
| **Max tokens** | 1 - 4096+ | Response length |
| **Stop sequences** | Custom text | When to stop generating |

**Mnemonic:** "Temperature = Thermometer of Creativity" (hot = creative, cold = predictable)

---

## í´– Act 2: What Are AI Agents?

**Chatbot vs Agent:**

| Chatbot í²¬ | Agent í´– |
|-----------|---------|
| Only talks | Talks AND acts |
| Stateless | Remembers context |
| Single-turn | Multi-turn with planning |

### Agent Capabilities:
1. **Tool/Function Calling** - executes external functions
2. **Memory/State** - retains context across interactions
3. **Planning** - decomposes complex tasks into subtasks

---

## í¿¢ Microsoft Foundry

### Key Components:

#### 1. Hub - top-level container for AI resources
#### 2. Project - workspace for ONE AI application (one hub â†’ many projects)
#### 3. Model Catalog - browse and deploy Azure OpenAI, open-source, and third-party models
#### 4. Deployment Types:
- **Serverless:** Pay per token (unpredictable traffic â†’ use this)
- **Managed:** Pay for dedicated capacity (predictable high traffic â†’ use this)

---

## âœ… Self-Test

1. Generate marketing copy. Generative or analytical AI?
   <details><summary>Answer</summary>Generative AI</details>

2. Agent needs to query a database. What capability?
   <details><summary>Answer</summary>Function calling</details>

3. Creative story generation. Temperature high or low?
   <details><summary>Answer</summary>High (e.g. 1.2)</details>

4. Unpredictable traffic, minimize cost. Which deployment?
   <details><summary>Answer</summary>Serverless</details>

5. Where do you find GPT-4 in Foundry?
   <details><summary>Answer</summary>Model Catalog</details>

---

## í¾¯ Exam Tips

- "Generate/create new content" â†’ Azure OpenAI (generative)
- "Analyze existing content" â†’ Language/Vision (analytical)
- "Agent needs to DO something" â†’ Function calling
- "Unpredictable traffic" â†’ Serverless deployment
- "System prompt" â†’ Persistent behavior instructions
