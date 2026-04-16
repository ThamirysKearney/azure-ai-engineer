# AI-102 Azure AI Engineer Associate — Study Repository

> **Exam:** AI-102 — Designing and Implementing a Microsoft Azure AI Solution  
> **Exam Date:** June 25, 2026  
> **Study Period:** April 13 – June 24, 2026  
> **Total Study Days:** 53 weekdays  
> **Total Hours:** 205 hours  
> **Cost:** €0 (100% free resources)

---

## 📊 Exam Domain Weights

| Domain | Official Weight | Bobby Russell Weight | Study Days |
|--------|----------------|---------------------|------------|
| 1. Plan & Manage Azure AI | 20-25% | 10-15% | Days 21-25 |
| 2. Generative AI Solutions | 15-20% | 25-30% ⭐ HIGHEST | Days 27-32 |
| 3. AI Agent Solutions | 5-10% | 10-15% | Days 33-34 |
| 4. Computer Vision | 10-15% | 15-20% | Days 36-38 |
| 5. NLP Solutions | 15-20% | 15-20% | Days 39-41 |
| 6. Info Extraction & Knowledge Mining | 15-20% | 10-15% | Days 42-45 |

> ⚠️ Bobby Russell (Microsoft Technical Trainer) says Domain 2 (Generative AI)
> is the **largest group** on the exam. Prioritize it.

---

## 📅 Study Phases

| Phase | Dates | Hours/Day | Total Hours | Focus |
|-------|-------|-----------|-------------|-------|
| **Phase 1: Foundation** | Apr 13 – May 8 | 2h | 40h | AI-900 concepts |
| **Phase 2: Deep Dive** | May 9 – Jun 13 | 5h | 130h | AI-102 six domains |
| **Phase 3: Final Review** | Jun 15 – Jun 24 | 5h | 35h | Practice exams + review |

---

## 📁 Repository Structure

```
azure-ai-engineer/
│
├── README.md                           ← You are here
├── AI102_Study_Plan.md                 ← Full 53-day calendar
├── exam_tips.md                        ← Exam strategies and question types
├── glossary.md                         ← 150+ terms with definitions
├── setup_instructions.md               ← VS Code + Git + GitHub setup
├── free_lab_replacement.md             ← Video alternatives to paid labs
│
├── summaries/                          ← Memory palace summaries per topic
│   ├── 01_ai_intro.md                  ← AI, ML, GenAI fundamentals
│   ├── 02_ml_concepts.md               ← ML types, metrics, workflow
│   ├── 03_azure_ml.md                  ← Azure ML workspace, AutoML
│   ├── 04_genai_agents.md              ← GenAI and agents intro
│   ├── 05_nlp_concepts.md              ← NLP fundamentals
│   ├── 06_azure_language.md            ← Azure Language service
│   ├── 07_speech.md                    ← Speech services
│   ├── 08_translation.md              ← Translation services
│   ├── 09_cv_concepts.md              ← Computer Vision concepts
│   ├── 10_azure_vision.md             ← Azure Vision API
│   ├── 11_ocr.md                      ← OCR and Read API
│   ├── 12_custom_vision.md            ← Custom Vision training
│   ├── 13_video.md                    ← Video Indexer
│   ├── 14_info_extraction.md          ← Information extraction concepts
│   ├── 15_content_understanding.md    ← Azure Content Understanding
│   ├── 16_doc_intelligence_1.md       ← Document Intelligence prebuilt
│   ├── 17_doc_intelligence_2.md       ← Document Intelligence custom
│   ├── 18_ai_search.md                ← Azure AI Search
│   ├── 19_planning_ai.md             ← Planning AI solutions
│   ├── 20_foundry_platform.md         ← Microsoft Foundry platform
│   ├── 21_security.md                 ← Security and auth
│   ├── 22_responsible_ai.md           ← Responsible AI principles
│   ├── 23_model_deployment.md         ← Model deployment
│   ├── 24_monitoring.md               ← Monitoring and diagnostics
│   ├── 25_containers.md               ← Container deployments
│   ├── 26_cicd.md                     ← CI/CD for AI
│   ├── 27_genai_apps.md               ← GenAI applications
│   ├── 28_prompt_engineering.md        ← Prompt engineering techniques
│   ├── 29_rag.md                      ← RAG pattern
│   ├── 30_azure_openai.md            ← Azure OpenAI service
│   ├── 31_fine_tuning.md              ← Fine-tuning models
│   ├── 32_evaluation.md               ← Evaluation metrics
│   ├── 33_agents_intro.md             ← AI agents fundamentals
│   └── 34_multi_agent.md              ← Multi-agent systems
│
├── domain-01-plan-manage/              ← Domain 1 exam notes
│   ├── README.md                       ← Domain overview + Bobby tips
│   └── 03_auth_and_apis.md            ← Authentication and APIs
│
├── domain-02-generative-ai/           ← Domain 2 exam notes
│   ├── README.md                       ← Domain overview + Bobby tips
│   └── 03_rag_pattern.md             ← RAG pattern deep dive
│
├── domain-03-agents/                  ← Domain 3 exam notes
│   └── README.md                       ← Domain overview + Bobby tips
│
├── domain-04-computer-vision/         ← Domain 4 exam notes
│   └── README.md                       ← Domain overview + Bobby tips
│
├── domain-05-nlp/                     ← Domain 5 exam notes
│   └── README.md                       ← Domain overview + Bobby tips
│
├── domain-06-info-extraction/         ← Domain 6 exam notes
│   └── README.md                       ← Domain overview + Bobby tips
│
├── notes/                             ← Daily session guides
│   └── DAY01_SESSION_GUIDE.md
│
├── code-examples/                     ← Python reference code
│
└── resources/                         ← Reference materials
    ├── video_links.md                 ← Video recommendations
    └── practice_questions.md          ← Practice Q&A
```

---

## 🎯 Quick Service Selection Guide

Print this table and memorize it:

| Task | Azure Service |
|------|--------------|
| Analyze text — sentiment, entities, PII | **Azure Language** |
| Translate text between languages | **Azure Translator** |
| Convert speech to text or text to speech | **Azure Speech** |
| Analyze images — tags, objects, captions | **Azure Vision** |
| Custom image classification or detection | **Custom Vision** |
| Analyze video content | **Video Indexer** |
| Monitor people movement in video | **Spatial Analysis** |
| Extract data from forms and invoices | **Document Intelligence** |
| Analyze complex multimodal documents | **Content Understanding** |
| Search and index document collections | **Azure AI Search** |
| Generate text, images, or code | **Azure OpenAI** |
| Build AI agents that take actions | **Foundry Agent Service** |

---

## 🛡️ Responsible AI — 6 Principles (FRPITA)

| Principle | Meaning |
|-----------|---------|
| **F**airness | No discrimination |
| **R**eliability & Safety | Works consistently |
| **P**rivacy & Security | Protects user data |
| **I**nclusiveness | Works for everyone |
| **T**ransparency | Users know AI is involved |
| **A**ccountability | Humans are responsible |

---

## 🔐 Authentication Methods (3 ways)

| Method | When to Use |
|--------|-------------|
| **API Key** | Simple apps and testing |
| **Token** | Short-lived access |
| **Entra ID** | Enterprise — granular permissions |

---

## 📺 Free Video Resources

| Channel | Content | Link |
|---------|---------|------|
| **John Savill** | Full AI-102 course, exam-focused | [YouTube](https://www.youtube.com/c/intikitneil) |
| **Adam Marczak** | Step-by-step Azure AI demos | [YouTube](https://www.youtube.com/c/AdamMarczakIO) |
| **Microsoft Learn Live** | Official training recordings | [YouTube](https://www.youtube.com/c/MicrosoftLearn) |
| **Bobby Russell** | 6-part exam prep series | Search "AI-102 Exam Prep Bobby Russell" |

---

## ✅ Study Progress Tracker

### Phase 1: Foundation (Apr 13 – May 8)

- [ ] Week 1 (Days 1-5): AI, ML, GenAI fundamentals
- [ ] Week 2 (Days 6-10): NLP and Speech basics
- [ ] Week 3 (Days 11-15): Computer Vision basics
- [ ] Week 4 (Days 16-20): Info Extraction + First practice test

### Phase 2: Deep Dive (May 9 – Jun 13)

- [ ] Week 5 (Days 21-25): Domain 1 — Plan & Manage
- [ ] Week 6 (Days 26-30): Domain 2 — Generative AI
- [ ] Week 7 (Days 31-35): Domain 2 cont. + Domain 3 — Agents
- [ ] Week 8 (Days 36-40): Domain 4 — Vision + Domain 5 — NLP
- [ ] Week 9 (Days 41-45): Domain 5 cont. + Domain 6 — Info Extraction
- [ ] Week 10 (Day 46): Gap day — weakest areas

### Phase 3: Final Review (Jun 15 – Jun 24)

- [ ] Days 47-49: Full domain reviews
- [ ] Days 50-51: Practice exams
- [ ] Days 52-53: Final review and weak spots
- [ ] Jun 24: Rest day
- [ ] Jun 25: EXAM DAY

---

## 💡 How to Use This Repo

1. **Start with** `AI102_Study_Plan.md` — follow the daily schedule
2. **Read** domain READMEs before each study block — get the big picture
3. **Fill in** summary files as you study — use memory palace format
4. **Track progress** — check boxes in this README as you complete weeks
5. **Commit daily** — save your progress to GitHub

### Daily Git Workflow

```bash
# Before studying
git checkout dev
git pull origin dev

# After studying
git add .
git commit -m "feat(day-XX): [topic studied today]"
git push origin dev
```

---

## 📝 Commit Convention

| Prefix | When to Use |
|--------|------------|
| `feat(day-XX):` | Add new study notes for a specific day |
| `feat(domain-XX):` | Update a domain file |
| `fix:` | Correct mistakes in existing files |
| `docs:` | Update README or documentation |
| `refactor:` | Reorganize file structure |

---

## ⚠️ Exam Details

| Property | Detail |
|----------|--------|
| **Exam code** | AI-102 |
| **Passing score** | 700 / 1000 (approximately 70%) |
| **Questions** | 40-60 questions |
| **Duration** | 100 minutes |
| **Question types** | Multiple choice, drag-and-drop, case studies, code completion |
| **Free practice** | [Microsoft Practice Assessment](https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/?practice-assessment-type=certification) |
| **Retires** | June 30, 2026 |

---

*Built with 🎯 focus and 0€ budget. Let's pass AI-102.*