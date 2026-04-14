# Domain 03 — AI Agent Solutions

> **Exam Weight:** 5-10%
> **Bobby Russell Episode:** 3
> **Study Days:** 33-34 (Phase 2, Week 7)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_agents_intro.md` | What is an agent, tools, function calling | Day 33 |
| `02_multi_agent.md` | Multi-agent patterns, MCP, A2A | Day 34 |

---

## 🤖 Agent vs Chatbot

| | Chatbot | Agent |
|--|---------|-------|
| **Does** | Talks | Talks + Acts |
| **Tools** | None | Database, APIs, files, code |
| **Memory** | None or basic | Can maintain state |
| **Planning** | No | Can break tasks into steps |
| **Example** | FAQ bot | Booking flights, running queries |

---

## 🧠 Agent = 4 Components

```
Agent = LLM + Tools + Memory + Planning
```

| Component | What it does |
|-----------|-------------|
| **LLM** | Reasoning engine — decides what to do |
| **Tools** | External capabilities it can invoke |
| **Memory** | Stores context across turns |
| **Planning** | Breaks complex goals into steps |

---

## 🔧 Function Calling

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
```

Flow:
```
1. User: "What's the weather in Madrid?"
2. LLM: requests get_weather(city="Madrid")
3. App: executes the function
4. App: returns result to LLM
5. LLM: "It's 22°C and sunny in Madrid."
```

---

## 🌐 Multi-Agent Patterns

```
User Request
     ↓
Orchestrator Agent        ← breaks task into subtasks
     ├── Research Agent   ← specialized for web research
     ├── Writing Agent    ← specialized for writing
     └── Review Agent     ← specialized for QA
```

Key concepts:
- **Orchestrator** — central agent that delegates
- **Handoff** — passing a task from one agent to another
- **MCP** — standard protocol for connecting agents to tools
- **A2A** — protocol for agents to communicate with each other

---

## 🔌 MCP (Model Context Protocol)

Standard protocol that separates:
- **MCP Server** — provides tools (e.g., a database connector)
- **MCP Client** — the agent that uses those tools

Benefit: Build tools once, use them with any MCP-compatible agent.

---

*Domain 03 — Part of the AI-102 study repository*
