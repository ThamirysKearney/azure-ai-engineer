# Domain 03 — AI Agent Solutions

> **Exam Weight:** 5-15% (official: 5-10%, Bobby says: 10-15%)
> **Bobby Russell Episode:** 3
> **Study Days:** 33-34 (Phase 2, Week 7)

---

## ⚠️ Bobby Russell says:
> "This group accounts for about 10% to 15% of your exam."
> Slightly higher than the official guide. Don't skip this domain.

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_agent_fundamentals.md` | What agents are, use cases, setup types | Day 33 |
| `02_function_calling.md` | Tools, plugins, custom functions | Day 33 |
| `03_multi_agent.md` | Orchestration, MCP, A2A, Semantic Kernel, AutoGen | Day 34 |

---

## 🤖 Agent vs Chatbot (CRITICAL exam distinction)

| | Chatbot | Agent |
|--|---------|-------|
| **Does** | Talks only | Talks AND acts |
| **Tools** | None | Database, APIs, files, code |
| **Memory** | None or basic | Maintains state across turns |
| **Planning** | No | Breaks tasks into steps |
| **Example** | FAQ bot | Booking flights, running queries |

**Exam pattern:**
> "AI needs to query a database AND respond to user. Which solution?"
> ✅ AI Agent (can take actions)
> ❌ Chatbot (can only talk)

---

## 🧠 Agent = 4 Components (memorize)

Agent = LLM + Tools + Memory + Planning

text


| Component | What It Does | Example |
|-----------|-------------|---------|
| **LLM** | Reasoning engine — decides what to do | GPT-4 understands the request |
| **Tools** | External capabilities it can invoke | Search API, database, calendar |
| **Memory** | Stores context across turns | Remembers user said "Seattle" |
| **Planning** | Breaks complex goals into steps | 1.Search 2.Compare 3.Book |

---

## 🏥 Agent Use Cases by Industry (Bobby: "illustrate examples")

> "Be able to illustrate examples of agents in areas such as
> healthcare, energy, travel, consulting, software, and retail."

| Industry | Agent Example |
|----------|--------------|
| **Healthcare** | Check symptoms → search medical DB → suggest next steps |
| **Energy** | Monitor usage → predict demand → adjust pricing |
| **Travel & Hospitality** | Search flights → compare hotels → book reservations |
| **Consulting** | Analyze reports → extract insights → draft recommendations |
| **Software & Technology** | Debug code → search docs → suggest fixes |
| **Retail & Automotive** | Check inventory → recommend products → process orders |

**Exam pattern:**
> "Travel company needs AI to search AND book flights autonomously."
> ✅ AI Agent with function calling
> ❌ Chatbot (can't take booking actions)

---

## ⚙️ Two Agent Setup Types (Bobby: "CRUCIAL for your exam")

> "Understanding these setups is going to be crucial
> in preparing for your exam."

| Setup | Who Manages Resources | Search & Storage | Control |
|-------|----------------------|-----------------|---------|
| **Basic** | Microsoft manages | Multi-tenant (shared) | Low |
| **Standard** | YOU manage | Single-tenant (yours only) | Full |

### Quick Memory:
Basic = Microsoft-managed = Multi-tenant = Less control
Standard = Customer-owned = Single-tenant = Full control

text


**Exam pattern:**
> "Company requires full data control for compliance. Which setup?"
> ✅ Standard (customer-owned, single-tenant)
> ❌ Basic (Microsoft-managed, shared)

> "Quick prototype, minimal setup needed. Which setup?"
> ✅ Basic
> ❌ Standard (overkill for prototyping)

---

## 🛠️ Creating & Debugging Agents

> "Focus on the agent's playground, which allows you to explore
> prototypes and test agents WITHOUT writing any code."

### Steps to Create an Agent:
1. Open Agent Playground in Foundry
2. Create new agent
3. Configure parameters (model, temperature, etc.)
4. Write clear instructions (system prompt)
5. Add tools/functions
6. Test with sample queries
7. Debug and refine
8. Deploy when ready

### Testing Flow:
Test in Playground (no code)
↓
Review responses
↓
Add more training data (improve weak areas)
↓
Add more actions/tools (expand capabilities)
↓
Re-test → Deploy

text


**Bobby's example:**
> "Searching flights from Seattle to New York on the 20th of March"
> Agent uses search plugin → finds flights → returns to user

**Exam pattern:**
> "Test agent prototype without writing code. Which tool?"
> ✅ Agent Playground
> ❌ Python SDK (requires code)

---

## 🔧 Function Calling (Tool Use)

Function calling lets the LLM request execution of external code:

```python
tools = [
    {
        "type": "function",
        "function": {
            "name": "get_weather",
            "description": "Get current weather for a city",
            "parameters": {
                "type": "object",
                "properties": {
                    "city": {"type": "string"}
                }
            }
        }
    }
]
Function Calling Flow:
text

1. User:  "What's the weather in Madrid?"
2. LLM:   Decides to call get_weather(city="Madrid")
3. App:   Executes the function
4. App:   Returns result to LLM → {"temp": 22, "condition": "sunny"}
5. LLM:   "It's 22°C and sunny in Madrid."
Exam pattern:

"Agent needs to query SQL database. What capability?"
✅ Function calling
❌ Prompt engineering (text only, no external calls)

🧩 Agent Frameworks (Bobby: "worth noting")
"Having a key understanding of the components and features
of Semantic Kernel and AutoGen is worth noting."

Framework 1: Semantic Kernel (Production)
What it is: Microsoft's SDK for building production AI agents

4 Components (memorize):

Component	What It Does	Memory Image
AI Connectors	Connect to AI models (GPT-4, etc.)	🧠 Brain
Plugins	Add capabilities (search, email, calendar)	🖐️ Hands
Planner	Breaks complex tasks into steps automatically	📋 Clipboard
Memory	Stores context and conversation history	💾 Hard drive
"Essential for orchestrating actions and providing
a robust agent runtime."

Framework 2: AutoGen (Experimentation)
What it is: Microsoft's framework for multi-agent experimentation

Key difference:

Semantic Kernel	AutoGen
Production-ready	Experimentation-focused
Single agent with plugins	Multi-agent collaboration
Orchestrating actions	Advanced design patterns
Robust agent runtime	Prototyping sophisticated systems
"AutoGen focuses on experimentation with multi-agent systems
and advanced design patterns, making it ideal for prototyping
sophisticated AI systems."

Exam patterns:

"Prototype a multi-agent system with advanced patterns. Which framework?"
✅ AutoGen (experimentation)
❌ Semantic Kernel (production)

"Build production agent with plugins and planning. Which framework?"
✅ Semantic Kernel (production)
❌ AutoGen (experimentation)

🌐 Multi-Agent Patterns
Orchestration Pattern:
text

User Request
     ↓
Orchestrator Agent       ← breaks task into subtasks
     ├── Research Agent  ← specialized for web research
     ├── Writing Agent   ← specialized for writing
     └── Review Agent    ← specialized for QA
Key Concepts:
Concept	Simple Definition
Orchestrator	Central agent that delegates to specialized agents
Handoff	Passing a task from one agent to another
MCP	Standard protocol for connecting agents to tools
A2A	Protocol for agents to communicate with each other
Autonomous	Agents work with minimal human input
🔌 MCP (Model Context Protocol)
What it is: Standard protocol that separates tools from agents

text

MCP Server (provides tools)     MCP Client (agent using tools)
e.g. database connector    ←→   e.g. your AI agent
Benefit: Build tools ONCE, use with ANY MCP-compatible agent

Examples of MCP servers:

Azure Language MCP server
Azure Speech MCP server
Database connectors
File system tools
🔗 A2A (Agent-to-Agent Protocol)
What it is: Standard for agents to communicate directly with each other

text

Agent A ←—— A2A Protocol ——→ Agent B
(Research)                   (Writing)
Use case: One agent hands off results to another agent
Benefit: Agents from different systems can collaborate

🧠 Memory Palace: The Agent Office
Building 6 in your Robot Factory Town:

Reception Desk — Two Doors:

🚪 LEFT door = "BASIC" (apartment building — Microsoft manages, shared floors)
🚪 RIGHT door = "STANDARD" (private house — you own everything)
Sign: "Basic = shared building, Standard = your own house"
Ground Floor — Playground Room:

No computers (no code needed here)
Agents play and test for FREE
Sign: "Prototype here FIRST — no coding"
Floor 1 — Semantic Kernel Department (PRODUCTION):

Robot with 4 body parts:
🧠 Brain = AI Connectors
🖐️ Hands = Plugins
📋 Clipboard = Planner
💾 Hard drive = Memory
Sign: "PRODUCTION agents only"
Floor 2 — AutoGen Laboratory (EXPERIMENTATION):

Multiple robots talking and arguing with each other
Whiteboards covered in diagrams
Sign: "PROTOTYPE multi-agent systems here"
Floor 3 — Orchestration Center:

One BOSS robot (orchestrator)
Delegates to: Flight Robot, Price Robot, Booking Robot
Sign: "One boss, many specialists"
Basement — MCP & A2A Tunnels:

MCP tunnel = robots connect to external tools
A2A tunnel = robots talk to each other
Sign: "Standard protocols — works everywhere"
🎯 Exam Priority Checklist
MUST KNOW:
 Agent = LLM + Tools + Memory + Planning
 Agent vs Chatbot differences
 Basic setup = Microsoft-managed = multi-tenant
 Standard setup = customer-owned = single-tenant
 Agent Playground = no-code testing
 Function calling flow (5 steps)
SHOULD KNOW:
 Semantic Kernel 4 components (AI Connectors, Plugins, Planner, Memory)
 Semantic Kernel = production, AutoGen = experimentation
 Multi-agent orchestration pattern
 Agent use cases by industry (6 industries)
 Steps to create an agent (8 steps)

GOOD TO KNOW:

 MCP = standard tool protocol (build once, use anywhere)
 A2A = agent-to-agent communication
 Testing flow (playground → data → actions → deploy)


## ❓ Quick Self-Test

**How to use:** Read the question. Think of your answer.
Then click ▶ to reveal the correct answer.

---

**Q1. An AI needs to search for AND book a flight automatically.
Chatbot or Agent?**

<details>
<summary>▶ Click to reveal answer</summary>

**Agent.**

Chatbot = only talks ("Here are some flights")
Agent   = talks AND acts ("I've booked the flight for you")

Booking is an ACTION → needs an Agent.
</details>

---

**Q2. Every AI Agent is built from 4 parts. What are they?**

<details>
<summary>▶ Click to reveal answer</summary>

**LLM + Tools + Memory + Planning**

- 🧠 LLM = the brain (thinks)
- 🛠️ Tools = the hands (does things)
- 💾 Memory = the notebook (remembers)
- 📋 Planning = the to-do list (organizes steps)
</details>

---

**Q3. A bank needs AI agents but all data must stay 100% private
under company control. Basic or Standard setup?**

<details>
<summary>▶ Click to reveal answer</summary>

**Standard setup.**

Basic    = shared space (Microsoft manages, less control)
Standard = your own space (you manage, full control)

Full control = Standard.
</details>

---

**Q4. A developer wants to test an agent idea quickly
without writing any code. What tool?**

<details>
<summary>▶ Click to reveal answer</summary>

**Agent Playground.**

It's a sandbox inside Azure AI Foundry.
No code needed. Just experiment and test.
</details>

---

**Q5. Semantic Kernel has 4 components. What are they?**

<details>
<summary>▶ Click to reveal answer</summary>

**AI Connectors, Plugins, Planner, Memory**

- 🧠 AI Connectors = connects to AI models (GPT-4)
- 🖐️ Plugins = adds capabilities (search, email)
- 📋 Planner = breaks tasks into steps automatically
- 💾 Memory = stores conversation history
</details>

---

**Q6. A team is experimenting with multiple agents working together.
They are still in research phase. Semantic Kernel or AutoGen?**

<details>
<summary>▶ Click to reveal answer</summary>

**AutoGen.**

AutoGen = science lab (experiment, research, prototype)
Semantic Kernel = professional kitchen (production, real customers)

Still experimenting = AutoGen.
</details>

---

**Q7. A company is launching their agent to real customers tomorrow.
Semantic Kernel or AutoGen?**

<details>
<summary>▶ Click to reveal answer</summary>

**Semantic Kernel.**

Real customers = production = Semantic Kernel.
AutoGen is for experimentation only.
</details>

---

**Q8. What is the difference between MCP and A2A?**

<details>
<summary>▶ Click to reveal answer</summary>

**MCP** = how an agent connects to **external tools**
(database, search API, file system)

**A2A** = how an agent connects to **other agents**
(research agent talks to writing agent)

MCP = Agent ←→ Tool
A2A = Agent ←→ Agent
</details>

Domain 03 — Merged: Bobby Russell Episode 3 + technical reference
Part of the AI-102 study repository




----------------------------------------------
Questions explained simply

Question 1:
"A company wants AI to search for AND book a flight automatically. Should they use a Chatbot or an Agent?"

Why this is asked: The exam loves testing if you know the difference.

Simple explanation:

text

Chatbot = can only TALK
          "Here are some flights I found" ← just giving info

Agent   = can TALK + DO THINGS
          "I found a flight and I've booked it for you" ← actually did it
Answer: Agent — because booking requires TAKING AN ACTION, not just talking.

Question 2:
"Name the 4 things every AI Agent is made of."

Simple explanation:

text

Think of an Agent like a human employee:

🧠 LLM      = The brain (thinks and reasons)
🛠️ Tools    = The hands (does things: search, book, query)
💾 Memory   = The notebook (remembers what you said before)
📋 Planning = The to-do list (breaks big jobs into small steps)
Answer: LLM + Tools + Memory + Planning

Question 3:
"A bank needs to use AI agents but their legal team says ALL data must stay private and under company control. Which setup?"

Simple explanation:

text

Basic Setup    = Like renting a desk in a shared office
                 Microsoft owns the building
                 Other companies use the same space
                 You have LESS control

Standard Setup = Like owning your own office building
                 YOU own everything
                 Nobody else shares your space
                 You have FULL control
Answer: Standard — because full control = Standard setup.

Question 4:
"A developer wants to quickly test an agent idea without writing any code. What tool do they use?"

Simple explanation:

text

Agent Playground = A sandbox environment inside Azure AI Foundry

Think of it like a playground for children:
- No rules (no code needed)
- Just play and experiment
- Test ideas quickly
- If it breaks, nothing bad happens
Answer: Agent Playground — test without writing a single line of code.

Question 5:
"Semantic Kernel is a framework for building agents. What are its 4 parts?"

Simple explanation — think of a robot:

text

🧠 AI Connectors = The robot's BRAIN
                   Connects to AI models like GPT-4
                   "This is how the robot thinks"

🖐️ Plugins      = The robot's HANDS
                   Adds capabilities (search, email, calendar)
                   "This is how the robot does things"

📋 Planner      = The robot's CLIPBOARD
                   Automatically breaks big tasks into steps
                   "This is how the robot organizes work"

💾 Memory       = The robot's HARD DRIVE
                   Remembers previous conversations
                   "This is how the robot remembers"
Answer: AI Connectors, Plugins, Planner, Memory

Question 6:
"A team wants to experiment with a complex system where multiple AI agents work together. Which framework?"

Simple explanation:

text

Semantic Kernel = Professional kitchen (production)
                  Everything is organized and ready to serve customers
                  Used when you KNOW what you're building

AutoGen         = Science lab (experimentation)
                  Researchers trying new things, making mistakes
                  Used when you're FIGURING OUT what to build

Multi-agent experimentation = still figuring things out = SCIENCE LAB
Answer: AutoGen — for experimenting with multi-agent systems.

Question 7:
"A company is ready to launch their AI agent to real customers. Which framework?"

Simple explanation:

text

This is the OPPOSITE of Question 6.

AutoGen         = Lab experiments (not ready for customers)
Semantic Kernel = Production system (ready for real customers)

Real customers = production = Semantic Kernel
Answer: Semantic Kernel — for building production-ready agents.

Question 8:
"What is the difference between MCP and A2A?"

Simple explanation:

text

Think of a RESTAURANT:

MCP = The connection between WAITER and KITCHEN
      Waiter (agent) talks to kitchen (external tool)
      "Agent connects to external tools"
      Example: Agent → database, Agent → search API

A2A = The connection between TWO WAITERS
      Waiter 1 (agent) talks to Waiter 2 (another agent)
      "Agent talks to another agent"
      Example: Research Agent → Writing Agent
Visual:

text

MCP:  Your Agent ←——→ External Tool (database, API, file system)
A2A:  Your Agent ←——→ Another Agent (research agent, writing agent)
Answer:

MCP = how an agent connects to tools
A2A = how an agent connects to other agents
