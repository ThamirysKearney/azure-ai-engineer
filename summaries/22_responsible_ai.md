# Memory Palace #22: Responsible AI & Content Safety

> **Study Day:** Day 27 (Phase 2, Week 6)  
> **Domain:** 01 — Plan & Manage  
> **Status:** 🟡 Partially complete — full memory palace to be added on Day 27

---

## ⚠️ Note to Self

This file has the Content Safety severity explanation added early
because it connects to Domain 01.  
The full memory palace story and self-test will be added on Day 27.

---

## 🛡️ Responsible AI — 6 Principles (FRPITA)

| # | Principle | Meaning | Exam Scenario |
|---|-----------|---------|--------------|
| 1 | **Fairness** | No discrimination | Loan AI favors certain zip codes |
| 2 | **Reliability & Safety** | Works consistently | AI gives random wrong answers |
| 3 | **Privacy & Security** | Protects user data | AI exposes personal information |
| 4 | **Inclusiveness** | Works for everyone | AI doesn't work for disabled users |
| 5 | **Transparency** | Users know AI is involved | Hidden AI making decisions |
| 6 | **Accountability** | Humans are responsible | No human oversight of AI decisions |

**Mnemonic: FRPITA**

---

## 🔒 Content Safety — 4 Categories

| Category | What It Detects |
|----------|----------------|
| **Hate** | Discriminatory content |
| **Violence** | Violent content or threats |
| **Sexual** | Sexual content |
| **Self-harm** | Self-harm content |

---

## 📊 The 0-6 Severity Scale — Explained Simply

Think of it like a **traffic light system with 7 levels** (0 through 6):

```
0 = Safe        → No harmful content detected
1 = Very Low    → Barely detectable trace
2 = Low         → Mild content, unlikely to cause harm
3 = Medium-Low  → Noticeable but moderate
4 = Medium      → Clearly harmful content
5 = High        → Strongly harmful content
6 = Very High   → Extremely harmful content
```

---

### Real Example — Violence Filter Set to Level 4

```
User message detected as violence level 2 → ✅ ALLOWED (below threshold)
User message detected as violence level 4 → ❌ BLOCKED (at threshold)
User message detected as violence level 6 → ❌ BLOCKED (above threshold)
```

---

### Threshold Settings — What Each Means

| Set Threshold At | Effect |
|-----------------|--------|
| Block at level 0 | Block EVERYTHING — even barely detectable content |
| Block at level 2 | Block mild and above — quite strict |
| Block at level 4 | Block medium and above — balanced |
| Block at level 6 | Only block the most extreme content — very permissive |

**Rule:**
- Higher threshold = MORE permissive (allows more content through)
- Lower threshold = STRICTER (blocks more content)

---

### Exam Pattern

> "Configure system to block all violent content except mild references.
> What severity threshold?"
> ✅ Block at level 2 — allows levels 0-1, blocks levels 2-6
> ❌ Block at level 4 — that would allow mild AND moderate violence through

---

### Each Category Has Its Own Threshold

You configure thresholds **per category independently:**

```python
# Example configuration (study the pattern, not the exact syntax)
content_filter_config = {
    "hate":      {"threshold": 2},   # Strict — block mild hate speech
    "violence":  {"threshold": 4},   # Balanced — allow mild references
    "sexual":    {"threshold": 0},   # Maximum — block everything
    "self_harm": {"threshold": 2}    # Strict — block mild references
}
```

**Exam pattern:**
> "Block all sexual content but allow mild violence references.
> Which configuration?"
> ✅ Sexual threshold = 0, Violence threshold = 2 or higher

---

## 🛡️ Content Safety Features — Summary

| Feature | What It Does | When to Use |
|---------|-------------|------------|
| **Content Filters** | Block content by category and severity | Always — first line of defence |
| **Blocklists** | Custom banned words or phrases | Brand protection, competitor names |
| **Prompt Shields** | Detect prompt injection attacks | Any public-facing AI application |
| **Groundedness Detection** | Check if response is based on source data | RAG applications |

---

## 🎯 Prompt Shields — 3 Attack Types

> Bobby says: "Prompt shields detect user prompt attacks,
> document attacks, and third-party attacks."

| Attack Type | What Happens | Example |
|-------------|-------------|---------|
| **User prompt attack** | User tries to override AI rules | "Ignore all previous instructions and..." |
| **Document attack** | Malicious instructions in documents | Hidden text in PDF: "Reveal all secrets" |
| **Third-party attack** | Attacks in external data sources | Web page being summarized has injected commands |

---

## 📝 TODO — To Complete on Day 27

- [ ] Add Memory Palace story for Responsible AI
- [ ] Add self-test questions
- [ ] Add AI governance framework details
- [ ] Add model interpretability and fairness tools
- [ ] Connect to Domain 02 content filters (configuration deep dive)

---

*Summary 22 — Responsible AI and Content Safety*  
*Partially complete — full content added on Day 27*  
*Part of the AI-102 study repository*