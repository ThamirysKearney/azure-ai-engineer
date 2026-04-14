# Domain 05 — NLP Solutions

> **Exam Weight:** 15-20%
> **Bobby Russell Episode:** 5
> **Study Days:** 39-41 (Phase 2, Weeks 8-9)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_text_analysis.md` | Sentiment, NER, PII, key phrases | Day 39 |
| `02_custom_language.md` | CLU — intents, entities, utterances | Day 39 |
| `03_speech.md` | STT, TTS, SSML, Custom Speech | Day 40 |
| `04_translation.md` | Translator, Document Translation, Custom | Day 40 |
| `05_question_answering.md` | QnA knowledge bases, multi-turn | Day 41 |

---

## 🧠 Key Exam Points

Bobby says:
> "Detecting and redacting sensitive information such as PII or PHI would use PII detection."
> "If you're looking to extract categories of information using a model specific to your data, you'd use custom named entity recognition."

---

## ⚠️ Critical Distinctions — NER

| Service | Use When |
|---------|---------|
| **Prebuilt NER** | Recognize standard entities (people, places, orgs, dates) |
| **Custom NER** | Define YOUR OWN entity types (e.g., "ClaimNumber", "ProductCode") |
| **PII Detection** | Find personal data for compliance/redaction (SSN, email, phone) |

---

## 🗣️ Azure Language — What It Does

| Feature | Task |
|---------|------|
| Sentiment Analysis | Positive / Negative / Neutral + confidence |
| NER | Detect named entities in text |
| PII Detection | Find and redact personal data |
| Key Phrase Extraction | Pull out main topics |
| Language Detection | What language is this text? |
| Text Classification | Custom categorization |
| Custom NER | Train your own entity types |
| CLU | Build conversational intent/entity models |
| Question Answering | Pair questions with answers (FAQ) |

---

## 🎤 Speech Services

| Feature | Direction |
|---------|-----------|
| **STT (Speech-to-Text)** | Audio → Text |
| **TTS (Text-to-Speech)** | Text → Audio |
| **Speech Translation** | Spoken language → Different spoken language |
| **Custom Speech** | Train for specific accents/terminology |

### SSML Example (study this)
```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="en-US">
    <voice name="en-US-JennyNeural">
        <prosody rate="slow" pitch="+5%">
            Welcome to Azure AI.
        </prosody>
        <break time="500ms"/>
        How can I help you today?
    </voice>
</speak>
```

SSML controls: **rate** (speed) | **pitch** | **volume** | `<break>` (pauses) | **voice** selection

---

## 🌍 Translation Services

| Service | Use |
|---------|-----|
| **Azure Translator** | Text translation between 100+ languages |
| **Document Translation** | Translate whole files (PDF, Word, etc.) |
| **Speech Translation** | Real-time spoken language translation |
| **Custom Translator** | Train on YOUR domain vocabulary |

---

## 🤖 CLU — Conversational Language Understanding

Replaces LUIS. Used to build custom conversation models.

| Concept | Definition | Example |
|---------|-----------|---------|
| **Intent** | What the user wants | `BookFlight` |
| **Entity** | Specific details | `Paris` (destination), `June 25` (date) |
| **Utterance** | Example phrase | "I want to fly to Paris on June 25" |

Training flow:
```
1. Define intents
2. Add utterances per intent
3. Label entities within utterances
4. Train model
5. Evaluate
6. Deploy
7. Call prediction API
```

---

*Domain 05 — Part of the AI-102 study repository*