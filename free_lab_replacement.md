# Free Lab Replacements

> Hands-on practice without requiring Azure credits.
> These alternatives let you get practical experience with the exam concepts for free.

---

## 🆓 Option 1 — Microsoft Learn Sandbox (BEST)

Microsoft Learn modules include **free sandbox environments** — no Azure subscription needed.

How to use:
1. Go to [Microsoft Learn AI-102 path](https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/)
2. Open any module with a "sandbox" tab
3. The sandbox gives you a temporary Azure subscription
4. Resources are auto-provisioned — you just run the exercises

**Available for most AI-102 topics:**
- Language service labs
- Vision API labs
- Document Intelligence labs
- Azure AI Search labs
- Azure OpenAI labs (limited)

---

## 🔬 Option 2 — Azure Free Trial

- Get $200 credit for 30 days
- Link: https://azure.microsoft.com/free/
- Good for: testing deployments, running full labs

---

## 💻 Option 3 — Local SDK Practice (No Azure Needed)

You can practice Python SDK patterns with mock data — no real API calls.

```python
# Practice the structure without real credentials
# Replace with mock responses to understand the code pattern

mock_sentiment_response = {
    "documents": [{
        "id": "1",
        "sentiment": "positive",
        "confidenceScores": {
            "positive": 0.98,
            "neutral": 0.01,
            "negative": 0.01
        }
    }]
}

# Practice parsing responses
doc = mock_sentiment_response["documents"][0]
print(f"Sentiment: {doc['sentiment']}")
print(f"Confidence: {doc['confidenceScores']['positive']:.0%}")
```

---

## 🎮 Option 4 — Microsoft Learn AI Skills Challenge

Microsoft often runs free challenges with prizes:
- Check: https://learn.microsoft.com/challenges/
- These sometimes include free exam vouchers!

---

## 📝 Study Without Azure Access

For topics where you can't run code, study the request/response patterns instead:

### Language Service — Sentiment Request
```json
POST https://<endpoint>/text/analytics/v3.1/sentiment
{
  "documents": [
    { "id": "1", "language": "en", "text": "I love Azure AI!" }
  ]
}
```

### Language Service — Sentiment Response
```json
{
  "documents": [{
    "id": "1",
    "sentiment": "positive",
    "confidenceScores": { "positive": 0.99, "neutral": 0.01, "negative": 0.0 },
    "sentences": [{
      "sentiment": "positive",
      "text": "I love Azure AI!"
    }]
  }]
}
```

### Vision API — Image Analysis Response (excerpt)
```json
{
  "tags": [
    { "name": "sky", "confidence": 0.99 },
    { "name": "outdoor", "confidence": 0.97 }
  ],
  "description": {
    "captions": [
      { "text": "a blue sky with clouds", "confidence": 0.89 }
    ]
  }
}
```

---

## 🗓️ Suggested Lab Schedule

| Week | Lab Focus | Method |
|------|-----------|--------|
| Week 2-3 (Foundation) | Language & Vision APIs | MS Learn Sandbox |
| Week 5 (Domain 1) | Foundry portal navigation | MS Learn Sandbox |
| Week 6 (Domain 2) | Azure OpenAI Chat API | MS Learn Sandbox |
| Week 7 (Domain 3) | Agent function calling | MS Learn Sandbox |
| Week 8 (Domain 4) | Custom Vision training | MS Learn Sandbox |
| Week 9 (Domain 6) | AI Search index + query | MS Learn Sandbox |

---

*Resources — Part of the AI-102 study repository*