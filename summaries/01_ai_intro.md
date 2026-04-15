# Memory Palace #1: Introduction to AI, ML, and Generative AI

## 🏘️ The Robot Factory Town (Your Mental Image)

Imagine walking down a street with **4 houses**. Each house has a different
robot inside doing a different job. This is your AI town.

---

## 🏠 House 1: The POST OFFICE — Artificial Intelligence (AI)

**Visual:** A robot postman sorting letters into the right mailboxes

**What AI is (simple):**
- Making machines do tasks that normally need human intelligence
- ANY system that can perceive, decide, or act

**What the robot postman does:**
- Reads the address (PERCEIVE)
- Decides which mailbox (DECIDE)
- Puts letter in correct box (ACT)

**Real examples:**
- Spam filter deciding which emails are junk
- GPS calculating fastest route
- Thermostat adjusting temperature automatically

**The key insight:**
AI is the BROADEST term. Everything else (ML, GenAI, Agents) lives INSIDE AI.

AI (everything)
└── Machine Learning
└── Deep Learning
└── Generative AI
└── Agents



**Exam trap:**
> ❌ "AI always uses machine learning" — FALSE
> ✅ Some AI uses simple rules (if temperature > 25, turn on AC)

---

## 🏠 House 2: The SCHOOL — Machine Learning (ML)

**Visual:** A robot student sitting at a desk with flashcards,
learning by looking at thousands of examples

**What ML is (simple):**
- A SUBSET of AI
- Machines that LEARN from DATA (not programmed with rules)
- You show it examples → it finds patterns → it makes predictions

**How the robot student learns:**

### Lesson 1: Supervised Learning (Teacher shows answers)
Teacher shows: 🐱 photo → "This is CAT"
Teacher shows: 🐶 photo → "This is DOG"
Teacher shows: 🐱 photo → "This is CAT"
... (thousands of times)

Test: 🐱 new photo → Student says "CAT!" ✅

**Key word:** LABELED data (every example has the correct answer)

**Two types:**
- **Classification** = Sort into categories (cat/dog, spam/not-spam)
- **Regression** = Predict a NUMBER (house price = $350,000)

**Mnemonic:**
- **C**lassification = **C**ategories
- **R**egression = **R**eal numbers

### Lesson 2: Unsupervised Learning (No teacher, find patterns alone)
Robot sees: 🔴🔴🔵🔵🟢🔴🔵🟢🟢🔵
Robot thinks: "I see 3 groups! Red, Blue, Green!"
**Key word:** UNLABELED data (no correct answers given)
**Main type:** Clustering (find natural groups)

### Lesson 3: Deep Learning (Many-layered brain)
Input → [Layer 1] → [Layer 2] → [Layer 3] → Output
simple medium complex
features features features


**What it is:** Neural networks with MANY layers
**When to use:** Complex tasks (images, speech, text)
**Key fact:** ALL modern AI services use deep learning

**Exam question you'll see:**
> "Predict house sale price from historical data. Which type?"
> ✅ Regression (supervised learning — predicting a number)
> ❌ Classification (that's for categories, not numbers)

---

## 🏠 House 3: The ART STUDIO — Generative AI (GenAI)

**Visual:** A robot artist with a blank canvas, creating paintings
that never existed before

**What GenAI is (simple):**
- A SUBSET of Machine Learning
- AI that CREATES new content (doesn't just analyze existing content)
- Powered by LLMs (Large Language Models)

**What the robot artist creates:**
- 📝 Text (articles, emails, code)
- 🖼️ Images (from text descriptions)
- 🎵 Music (compositions)
- 💻 Code (programs)

**Key difference from regular AI:**

| Regular AI (Analytical) | Generative AI |
|------------------------|---------------|
| "What IS this?" | "CREATE something like this" |
| Classifies existing content | Produces NEW content |
| Input: photo → Output: "cat" | Input: "draw a cat" → Output: 🐱 |

**The brain behind GenAI: LLMs**

**LLM = Large Language Model**
- **Large** = trained on BILLIONS of text documents
- **Language** = understands and generates human language
- **Model** = the trained AI "brain"

**How LLMs work (simplified):**
Step 1: Read billions of web pages, books, code
Step 2: Learn patterns (what word usually comes next?)
Step 3: Generate text by predicting one word at a time

Example:
Input: "The capital of France is ___"
LLM predicts: "Paris" (saw this pattern millions of times)


**Famous LLMs:**
- **GPT-4** (OpenAI) — Best overall, available in Azure OpenAI
- **GPT-3.5** (OpenAI) — Faster, cheaper, less capable
- **Llama** (Meta) — Open source
- **Phi-3** (Microsoft) — Small but efficient

**Prompts (how you talk to an LLM):**

| Prompt Type | What It Is | Example |
|-------------|-----------|---------|
| **System prompt** | Sets AI personality (stays for whole conversation) | "You are a helpful Python tutor" |
| **User prompt** | Your actual question | "Explain what a loop does" |
| **Assistant** | AI's response | "A loop repeats code..." |

**Exam question you'll see:**
> "Generate marketing copy from product specs. Which type of AI?"
> ✅ Generative AI
> ❌ Classification (that analyzes, doesn't create)

---

## 🏠 House 4: The ACTION AGENCY — AI Agents

**Visual:** A robot butler who can actually DO things — not just talk.
He has a toolbelt with a phone, a calculator, and a calendar.

**What an Agent is (simple):**
- AI that can TAKE ACTIONS in the real world
- Goes beyond just chatting — actually DOES things
- Has access to TOOLS (functions, databases, APIs)

**Chatbot vs Agent:**

| Chatbot 💬 | Agent 🤖 |
|-----------|---------|
| Only talks | Talks AND acts |
| "The weather is sunny" | Actually checks weather API |
| Forgets after conversation | Remembers context |
| Single task | Plans multi-step tasks |

**Agent capabilities:**

1. **Tool/Function calling** — Agent can run external functions

User: "What's the weather in Paris?"
Agent thinks: "I need get_weather() tool"
Agent calls: get_weather(city="Paris")
Tool returns: {"temp": 22, "condition": "sunny"}
Agent says: "It's 22°C and sunny in Paris!"


2. **Memory** — Agent remembers previous interactions

Turn 1: "Find hotels in Tokyo"
Turn 2: "Make it pet-friendly" ← Agent remembers "Tokyo"
Turn 3: "Book it" ← Agent remembers "Tokyo + pet-friendly"


3. **Planning** — Agent breaks complex tasks into steps

User: "Plan my trip to Japan"
Agent's plan:

Ask for dates and budget
Search flights
Find hotels
Create itinerary
Book everything


**Exam question you'll see:**
> "AI needs to query a database to answer user questions. What capability?"
> ✅ Function calling (agent uses tools)
> ❌ Prompt engineering (that's just text input)

---

## 🏛️ The Town Hall: Azure AI Platform

**Visual:** The central building in Robot Factory Town where all robots
get their assignments and resources

### The Hierarchy (memorize this):
Azure Subscription (your billing account)
└── Resource Group (folder for related stuff)
└── Resource (the actual AI service)
└── Endpoint (URL to call the service)
└── API Key (password to use it)


**Real-world analogy:**
Country (Subscription)
└── City (Resource Group)
└── Building (Resource)
└── Front Door (Endpoint)
└── Door Key (API Key)


### Microsoft Foundry (the platform):

Foundry Hub (the entire building)
└── Foundry Project (one app/solution)
└── Model Deployment (AI model running and ready)
└── Endpoint (URL to call it)


**Key facts:**
- One Hub → many Projects
- One Project → many Deployments
- Each Deployment has its own Endpoint + Key
- Formerly called "Azure AI Studio" (exam may use old name)

---

## 🛡️ The Town Laws: Responsible AI (6 Principles)

**Visual:** 6 signs posted on the Town Hall wall

| # | Principle | Memory Image | Meaning |
|---|-----------|-------------|---------|
| 1 | **Fairness** | ⚖️ Balanced scales | Don't discriminate |
| 2 | **Reliability & Safety** | 🌉 Sturdy bridge | Works consistently |
| 3 | **Privacy & Security** | 🔒 Locked vault | Protect user data |
| 4 | **Inclusiveness** | 🚪 Open door | Works for everyone |
| 5 | **Transparency** | 🪟 Glass window | Users know AI is involved |
| 6 | **Accountability** | ⚖️ Judge's gavel | Humans are responsible |

**Mnemonic: "FRPITA"** (Fair, Reliable, Private, Inclusive, Transparent, Accountable)

**Exam question you'll see:**
> "AI recruiting tool favors male candidates. Which principle violated?"
> ✅ Fairness
> ❌ Transparency (that's about EXPLAINING how AI works)

---

## 🎯 The Service Map (Which Robot for Which Job)

**This is the MOST IMPORTANT table for the exam. Memorize it.**

| You Need To... | Use This Service |
|----------------|-----------------|
| Analyze text (sentiment, entities, PII) | **Azure Language** |
| Translate text between languages | **Azure Translator** |
| Convert speech ↔ text | **Azure Speech** |
| Analyze images (tags, objects, captions) | **Azure Vision** |
| Train custom image classifier | **Custom Vision** |
| Analyze video content | **Video Indexer** |
| Extract data from forms/invoices | **Document Intelligence** |
| Analyze complex docs (text+images+tables) | **Content Understanding** |
| Search and index documents | **Azure AI Search** |
| Generate text, images, code | **Azure OpenAI** |
| Build AI agents that take actions | **Foundry Agent Service** |

---

## ✅ Self-Test (Cover answers, say out loud, then check)

1. What's the difference between AI and Machine Learning?
   <details><summary>Answer</summary>AI is the broad concept (any smart machine). ML is a subset where machines learn from data.</details>

2. Classify emails as spam/not-spam. Classification or Regression?
   <details><summary>Answer</summary>Classification (two categories)</details>

3. Predict house price. Classification or Regression?
   <details><summary>Answer</summary>Regression (predicting a number)</details>

4. AI creates a new image from text. Analytical AI or Generative AI?
   <details><summary>Answer</summary>Generative AI (creating new content)</details>

5. AI needs to check a database to answer questions. What capability?
   <details><summary>Answer</summary>Function calling / Tool use (Agent capability)</details>

6. AI loan system discriminates by zip code. Which principle violated?
   <details><summary>Answer</summary>Fairness</details>

7. What's the hierarchy? Subscription, Resource, Resource Group?
   <details><summary>Answer</summary>Subscription → Resource Group → Resource</details>

8. Hub, Project, Deployment — which contains which?
   <details><summary>Answer</summary>Hub → Project → Deployment</details>

9. Analyze customer review sentiment. Which service?
   <details><summary>Answer</summary>Azure Language</details>

10. Generate marketing copy from product specs. Which service?
    <details><summary>Answer</summary>Azure OpenAI (generative)</details>

---

## 🧠 Quick Recall — Walk Through the Town

Close your eyes and walk through Robot Factory Town:

**House 1 (Post Office)** → AI = machines making decisions
**House 2 (School)** → ML = learning from examples (classification, regression, clustering)
**House 3 (Art Studio)** → GenAI = creating new content (powered by LLMs)
**House 4 (Action Agency)** → Agents = AI + tools + memory + planning
**Town Hall** → Azure platform = Subscription → Resource Group → Resource
**Town Laws** → FRPITA = Fairness, Reliability, Privacy, Inclusiveness, Transparency, Accountability

**If you can walk through this town in your mind, you've mastered Day 1.**

---

## 🎯 Exam Tips for This Topic

### Common traps:
- ❌ AI = always machine learning (some AI uses simple rules)
- ❌ GenAI = analyzing content (GenAI CREATES, analytical AI ANALYZES)
- ❌ Chatbot = agent (chatbots just talk, agents take ACTIONS)
- ❌ Azure Vision for text analysis (Vision = images, Language = text)

### What they'll actually ask:
- ✅ "Which service for [specific task]?" → Match to service table
- ✅ "Which Responsible AI principle?" → Match scenario to FRPITA
- ✅ "What's the resource hierarchy?" → Subscription → RG → Resource
- ✅ "Classification or Regression?" → Categories vs numbers

### Time-saving trick:
- Question mentions **creating** new content → probably **Azure OpenAI**
- Question mentions **analyzing** existing content → probably **Vision/Language/Speech**
- Question mentions **extracting** from documents → probably **Document Intelligence**
- Question mentions **searching** documents → probably **Azure AI Search**