# Setup Instructions

> Tools and environment setup for AI-102 study and hands-on practice.

---

## 🛠️ Required Tools

### Git & GitBash
- Already installed (you're using it!)
- Fix your git identity to avoid the "configured automatically" warning:

```bash
git config --global user.name "Thamirys Kearney"
git config --global user.email "thamirys.kearney@cibervoluntarios.org"
```

### Python (for SDK examples)
```bash
# Check if installed
python --version

# Install Azure AI SDK packages
pip install azure-ai-textanalytics
pip install azure-ai-vision-imageanalysis
pip install azure-cognitiveservices-speech
pip install azure-ai-formrecognizer
pip install azure-search-documents
pip install azure-identity
pip install openai
pip install azure-ai-inference
```

### VS Code (recommended)
- Extensions to install:
  - Python
  - Azure Tools
  - Markdown All in One
  - GitLens

---

## 📋 Git Workflow (your standard)

### Branch Strategy
```
main     ← stable, reviewed content only
dev      ← active study notes (push here daily)
feature/ ← optional, for big additions
```

### Daily Commit Pattern
```bash
# After studying each day
git add .
git commit -m "feat: add day-XX notes - [topic name]"
git push origin dev
```

### Commit Message Convention
```
feat:    new content (new file, new notes)
update:  changes to existing content
fix:     corrections to errors
refactor: restructuring without content change
docs:    README or documentation updates
```

### Examples
```bash
git commit -m "feat: add domain-02 RAG pattern notes"
git commit -m "update: exam_tips - add content safety table"
git commit -m "fix: correct authentication method description"
git commit -m "feat: complete memory palace 05 - NLP concepts"
```

---

## 🔗 Key Links

| Resource | URL |
|----------|-----|
| Microsoft Learn AI-102 | https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/ |
| Practice Assessment | https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/?practice-assessment-type=certification |
| Azure AI Foundry Portal | https://ai.azure.com |
| Azure Portal | https://portal.azure.com |
| Azure Pricing Calculator | https://azure.microsoft.com/pricing/calculator/ |
| This Repo | https://github.com/ThamirysKearney/azure-ai-engineer |

---

## 🆓 Free Practice Alternatives (No Azure Credits Needed)

See `free_lab_replacement.md` for hands-on practice without spending money.

---

*Setup — Part of the AI-102 study repository*