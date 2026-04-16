# Domain 05 — NLP Solutions

> **Exam Weight:** 15-20%  
> **Bobby Russell Episode:** 5  
> **Study Days:** 39-41 (Phase 2, Weeks 8-9)

---

## ⚠️ Bobby Russell Says

> "This group accounts for 15 to 20% of your exam."  
> Confirmed same as official guide. This is a heavily tested domain.

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_text_analysis.md` | Sentiment, NER, entity linking, PII, key phrases | Day 39 |
| `02_custom_language.md` | CLU — intents, entities, utterances, lifecycle | Day 39 |
| `03_speech.md` | STT, TTS, SSML, Custom Speech, WER, keyword | Day 40 |
| `04_translation.md` | Translator, Document Translation, Speech Translation, Custom | Day 40 |
| `05_question_answering.md` | QnA knowledge bases, multi-turn, chitchat | Day 41 |

---

## 🧠 Service Selection — NLP (CRITICAL)

| You Need To... | Use This |
|----------------|---------|
| Detect sentiment (positive/negative/neutral) | **Azure Language — Sentiment Analysis** |
| Find named entities (people, places, orgs) | **Azure Language — NER** |
| Link entities to a knowledge base (Wikipedia) | **Azure Language — Entity Linking** |
| Find and redact personal data | **Azure Language — PII Detection** |
| Extract main topics from text | **Azure Language — Key Phrase Extraction** |
| Detect what language the text is in | **Azure Language — Language Detection** |
| Build custom entity types for your domain | **Azure Language — Custom NER** |
| Build intent recognition model | **Azure Language — CLU** |
| Build FAQ / Q&A system | **Azure Language — Question Answering** |
| Convert speech to text | **Azure Speech — STT** |
| Convert text to speech | **Azure Speech — TTS** |
| Translate spoken language in real-time | **Azure Speech — Speech Translation** |
| Train for specific accents or terminology | **Azure Speech — Custom Speech** |
| Recognize a specific wake word | **Azure Speech — Keyword Recognition** |
| Translate text between languages | **Azure Translator** |
| Translate whole files (PDF, Word) | **Azure Translator — Document Translation** |
| Train on your own domain vocabulary | **Custom Translator** |

---

## 🗣️ Azure Language — Text Analysis

> **Bobby says:** "Make sure to understand how to extract key phrases,
> how entity extraction works, especially the difference between
> named entity recognition and entity linking."

### Key Phrase Extraction

| Property | Detail |
|----------|--------|
| **What it does** | Pulls out main topics and concepts from text |
| **How to use** | Language Studio, REST API, client library, Docker container |
| **Returns** | List of key phrases with confidence scores |

> **3 ways to use (Bobby specifically lists these):**

| Method | When to Use |
|--------|-------------|
| **Language Studio** | No-code testing and exploration |
| **Programmatically** | REST API or Python/Java SDK |
| **Docker container** | Offline or on-premises deployment |

---

### NER vs Entity Linking (Bobby: "know the difference")

| Property | Named Entity Recognition (NER) | Entity Linking |
|----------|-------------------------------|----------------|
| **What it does** | Finds and classifies entities in text | Links entities to a knowledge base |
| **Output** | Entity type (Person, Location, Org, Date) | Entity + Wikipedia URL |
| **Example input** | "Satya Nadella works at Microsoft in Seattle" | "Satya Nadella works at Microsoft" |
| **Example output** | Person: Satya Nadella, Org: Microsoft, Location: Seattle | Satya Nadella → wikipedia.org/Satya_Nadella |
| **Use case** | Extract structured info from raw text | Disambiguate entities (which "Paris"?) |

> **Exam trap:**
> NER = classify the entity type
> Entity Linking = connect entity to external knowledge source

---

### Prebuilt NER vs Custom NER (Bobby: "critical distinction")

| Service | Use When | Example |
|---------|----------|---------|
| **Prebuilt NER** | Recognize standard entity types | People, places, organizations, dates |
| **Custom NER** | Define YOUR OWN entity types | "ClaimNumber", "ProductCode", "PolicyID" |
| **PII Detection** | Find personal data for compliance | SSN, email, phone number, credit card |

> **Bobby says:**
> "Detecting and redacting sensitive information such as PII or PHI
> would use PII detection."
> "If you're looking to extract categories of information using a model
> specific to your data, you'd use custom named entity recognition."

---

### Sentiment Analysis

> **Bobby says:** "Explore how sentiment analysis works, especially
> how it breaks down text. Also useful for opinion mining, which
> digs deeper to connect specific subjects with opinions."

| Feature | What It Does | Example |
|---------|-------------|---------|
| **Sentiment Analysis** | Overall tone of text | "Positive — confidence 0.95" |
| **Opinion Mining** | Links opinions to specific subjects | "Battery life" → Negative |

| Sentiment | Score Range |
|-----------|------------|
| Positive | High confidence positive score |
| Neutral | Balanced scores |
| Negative | High confidence negative score |

---

### Language Detection

| Property | Detail |
|----------|--------|
| **What it returns** | Detected language + confidence score |
| **Supports** | 100+ languages |
| **Output** | Language name, ISO code, confidence score |
| **Use case** | Route content to correct translation or analysis service |

> **Bobby says:** "Knowing how language detection operates
> and the confidence scores is a key concept."

---

### PII Detection

> **Bobby says:** "Understand how to detect PII in text.
> Know how to create a language service resource and use
> the key and endpoint to send requests with raw text."

| Property | Detail |
|----------|--------|
| **What it finds** | Names, SSN, email, phone, credit card, address |
| **Output** | Entity text, category, confidence score, offset |
| **Action** | Detect only OR detect and redact |
| **Use case** | GDPR compliance, data anonymization |

| Access Method | When to Use |
|---------------|------------|
| **REST API** | Any programming language |
| **Python SDK** | Python applications |
| **Java SDK** | Java applications |
| **Language Studio** | Testing without writing code |

> **Bobby also says:** "Check out how Language Studio can be used
> for entity linking and testing WITHOUT needing Azure accounts."

---

## 🤖 CLU — Conversational Language Understanding

> **Bobby says:** "Make sure you understand how intents, entities,
> and utterances work together."

Replaces LUIS. Used to build custom conversation models.

### Core Concepts

| Concept | Definition | Example |
|---------|-----------|---------|
| **Intent** | What the user wants to do | `BookFlight` |
| **Entity** | Specific details in the request | `Paris` (destination), `June 25` (date) |
| **Utterance** | Example phrase a user might say | "I want to fly to Paris on June 25" |

---

### Entity Component Types (Bobby: "get familiar with these")

> "Get familiar with the different types of entity components:
> learned, list, pre-built, and regex."

| Type | What It Is | Example |
|------|-----------|---------|
| **Learned** | Model learns from labeled utterances | "Paris" recognized as destination |
| **List** | Exact match from a fixed list | ["London", "Paris", "Madrid"] |
| **Pre-built** | Built-in types from Azure | Numbers, dates, email addresses |
| **Regex** | Pattern matching | Flight numbers like "BA-123" |

---

### Full CLU Lifecycle (Bobby: "be familiar with the full lifecycle")

| Step | Action |
|------|--------|
| 1 | Select and prepare data |
| 2 | Define schema — intents and entities |
| 3 | Label data accurately — add utterances per intent |
| 4 | Train model — choose training mode and data split |
| 5 | Evaluate performance — identify weak areas |
| 6 | Deploy for real-time use |
| 7 | Call prediction API from client application |

---

### How a Client App Uses CLU

```
Step 1 → User speaks or types input
Step 2 → App captures the input
Step 3 → App sends input to CLU model
Step 4 → CLU returns: predicted intent + extracted entities
Step 5 → App takes action based on intent and entities
```

---

### Pattern Matching vs CLU

> **Bobby says:** "Pattern matching can be used for quick offline
> intent recognition. CLU builds more advanced models."

| Property | Pattern Matching | CLU |
|----------|-----------------|-----|
| **Works offline** | Yes | No — needs Azure connection |
| **Setup complexity** | Simple — configure in code | Complex — train a model |
| **Accuracy** | Lower — exact patterns only | Higher — understands variations |
| **Best for** | Quick prototyping, offline scenarios | Production applications |

---

## ❓ Question Answering

> **Bobby says:** "Know how to create a custom Q&A project,
> how to pull in Q&A pairs from source URLs, and how to manually
> add pairs."

### Creating a Q&A Project

| Step | Action |
|------|--------|
| 1 | Create new project |
| 2 | Choose appropriate language |
| 3 | Import Q&A pairs from source URLs (automated) |
| 4 | OR manually add question and answer pairs |
| 5 | Edit and review content in knowledge base |
| 6 | Test the knowledge base |
| 7 | Train the model |
| 8 | Publish to your application |

---

### Document Processing in Q&A

> **Bobby says:** "Structured files like docs and PDFs are processed
> based on formatting, with headings and subheadings used to
> generate questions."

| Document Type | How It Is Processed |
|---------------|-------------------|
| **Word / PDF with headings** | Headings become questions, content becomes answers |
| **Plain text** | Processed as continuous content |
| **URLs** | Content scraped and converted to Q&A pairs |
| **Manual entry** | You write questions and answers directly |

---

### Multi-Turn Conversations

> **Bobby says:** "Understand the key steps to create a multi-turn
> conversation — selecting and adding a follow-up prompt or
> creating a link for a new pair."

| Step | Action |
|------|--------|
| 1 | Select an existing Q&A pair |
| 2 | Add a follow-up prompt |
| 3 | OR select option to create link for a new pair |
| 4 | Select Done |

**What multi-turn does:**
```
User: "What are your store hours?"
Bot:  "We are open 9am-9pm. Would you like to know about weekend hours?"
User: "Yes"
Bot:  "On weekends we are open 10am-6pm."
```

---

### Alternative Phrasing and Chitchat

| Feature | What It Does | Example |
|---------|-------------|---------|
| **Alternative phrasing** | Add different ways to ask the same question | "Hours?" / "When are you open?" / "What time do you close?" |
| **Chitchat** | Add small talk to make bot feel natural | "How are you?" → "I'm doing great, thanks for asking!" |

> **Bobby asks:** "What is chitchat used for? Understand what that is."
> Answer: Makes the bot feel more human and conversational.
> Not for answering real questions — just social interaction.

---

### Model Optimization

> **Bobby says:** "Know about active learning, backing up and
> recovering models, exporting a knowledge base, and creating
> a multi-language Q&A solution."

| Feature | What It Does |
|---------|-------------|
| **Active learning** | Captures real user queries the model is unsure about, suggests improvements |
| **Backup and recover** | Export and import knowledge base to restore or copy |
| **Export knowledge base** | Download as file for backup or migration |
| **Multi-language Q&A** | One knowledge base that supports multiple languages |

---

## 🎤 Speech Services

### Four Core Features

| Feature | Direction | Use Case |
|---------|-----------|----------|
| **STT (Speech-to-Text)** | Audio → Text | Transcribe meetings, voice commands |
| **TTS (Text-to-Speech)** | Text → Audio | Voice assistants, accessibility |
| **Speech Translation** | Spoken language → Different spoken language | Real-time conference translation |
| **Custom Speech** | Train for specific accents or terminology | Medical, legal, industry-specific |

---

### Speech-to-Text Features (Bobby: "recall the features")

| Feature | Detail |
|---------|--------|
| **High-quality transcription** | Accurate conversion of speech to text |
| **Customizable models** | Train on your own data |
| **Flexible deployment** | Cloud, on-premises, edge |
| **Production ready** | Enterprise-grade reliability |
| **WER (Word Error Rate)** | Main metric for measuring accuracy |

---

### WER — Word Error Rate (Bobby: "know what WER percentages mean")

> "WER helps identify how many words are inserted, deleted,
> or substituted incorrectly in a transcript."

| Metric | Simple Explanation |
|--------|-------------------|
| **WER** | Percentage of words that were wrong in the transcript |
| **Lower WER** | Better accuracy |
| **WER = 0%** | Perfect transcription |
| **WER = 10%** | 1 in 10 words is wrong |

| WER Range | Model Quality |
|-----------|--------------|
| Under 5% | Excellent — ready for production |
| 5% to 15% | Good — acceptable for most uses |
| Over 15% | Needs improvement — more training required |

---

### Custom Speech Testing (Bobby: "know how online testing works")

| Property | Detail |
|----------|--------|
| **What it does** | Compares custom model accuracy to baseline model |
| **Uses** | Custom language model OR acoustic model |
| **Tool** | Custom Speech portal |
| **How** | Add tests, evaluate results, review WER |

---

### Keyword Recognition (Bobby: "implement keyword recognition")

> "Focus on implementing keyword recognition, including creating
> a project in Speech Studio, defining custom keywords, and tuning."

| Model Type | Best For |
|------------|---------|
| **Basic keyword model** | Quick testing and prototyping |
| **Advanced keyword model** | Full product integration and production |

| Step | Action |
|------|--------|
| 1 | Create project in Speech Studio |
| 2 | Define custom keywords |
| 3 | Tune the model |
| 4 | Test with microphone input |
| 5 | Deploy — basic for testing, advanced for production |

---

### Text-to-Speech Features (Bobby: "understand key features of speech synthesis")

> "Speech synthesis offers a variety of natural sounding voices
> and supports use cases like accessibility and multitasking.
> Deep neural networks improve expressiveness."

| Feature | Detail |
|---------|--------|
| **Neural voices** | Natural sounding, powered by deep neural networks |
| **Expressiveness** | Improved stress and intonation |
| **Custom Neural Voice (CNV)** | Create your own brand voice |
| **Batch synthesis API** | Generate audio for long documents |
| **Accessibility** | Supports visually impaired users |
| **Multitasking** | Listen while doing other things |

---

### SSML — Speech Synthesis Markup Language

> **Bobby says:** "Know how SSML can be used to fine-tune output,
> like choosing the voice, language style, or inserting
> pre-recorded audio. Know how to control pronunciation
> and structure input text."

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

| SSML Element | What It Controls | Example |
|--------------|-----------------|---------|
| `<voice>` | Which voice to use | `name="en-US-JennyNeural"` |
| `<prosody rate>` | Speaking speed | `rate="slow"` or `rate="fast"` |
| `<prosody pitch>` | Voice pitch | `pitch="+5%"` |
| `<prosody volume>` | Volume level | `volume="loud"` |
| `<break>` | Pause in speech | `time="500ms"` |
| `<lang>` | Language within speech | Switch to French mid-sentence |

---

### Speech Translation — 4 Tools (Bobby: "know all four")

> "Walk through how each of the four translation tools can be used
> depending on the level of customization or coding required."

| Tool | Coding Required | Best For |
|------|----------------|---------|
| **Speech Translator** | Minimal | Quick translation tasks |
| **Speech API** | Yes — REST calls | Custom integrations |
| **Speech CLI** | No — command line | Testing without code |
| **Speech SDK** | Yes — Python/C# | Full application development |
| **Speech Studio** | No — browser UI | Exploration and testing |

---

## 🌍 Translation Services

> **Bobby says:** "Explore the full range of operations available
> in both text and document translation."

### Text Translation

| Feature | What It Does |
|---------|-------------|
| **Translation** | Translate text between 100+ languages |
| **Transliteration** | Convert text to different script (e.g., Arabic to Latin) |
| **Language detection** | Automatically detect source language |
| **Dictionary lookup** | Find alternative translations with context |
| **Dictionary examples** | See how words are used in sentences |

---

### Document Translation

> **Bobby says:** "Know how document translation works with large
> files, including how it preserves formatting and supports
> multiple languages in a single document."

| Property | Detail |
|----------|--------|
| **What it handles** | Large files — PDF, Word, PowerPoint, Excel |
| **Preserves** | Original formatting and layout |
| **Supports** | Multiple languages in one document |
| **Auto-detect** | Automatically detects source language |

---

### Translation vs Document Translation

> **Bobby says:** "Knowing the difference between translating a
> sentence and translating a full document will help clarify
> when and what tool to use."

| Property | Text Translation | Document Translation |
|----------|-----------------|---------------------|
| **Input** | Short text strings | Full files |
| **Output** | Translated string | Translated file |
| **Formatting** | Not preserved | Preserved |
| **Size** | Small | Large |
| **Use case** | Chat apps, snippets | Legal docs, manuals |

---

### Custom Translation

| Feature | Detail |
|---------|--------|
| **What it does** | Train on YOUR domain vocabulary and glossaries |
| **When to use** | Industry-specific terms not in standard translation |
| **Glossaries** | Upload word pairs to enforce specific translations |
| **Example** | "Azure AI" should never be translated |

---

## 🧠 Memory Palace — The Language District

**Building 8 in your Robot Factory Town:**

```
🗣️ BUILDING 8: THE LANGUAGE DISTRICT (5 departments)

┌─────────────────────────────────────────────┐
│  DEPT 5 — TRANSLATION OFFICE               │
│  📄 Text counter: short strings             │
│  📁 Document counter: full files            │
│  🗣️ Speech booth: real-time spoken          │
│  📚 Custom desk: your own vocabulary        │
├─────────────────────────────────────────────┤
│  DEPT 4 — SPEECH STUDIO                    │
│  🎤 Microphone → Text (STT)                │
│  🔊 Text → Speaker (TTS)                   │
│  📊 WER scoreboard on wall                 │
│  🎯 Keyword detector by door               │
│  SSML control panel with dials:            │
│    [SPEED] [PITCH] [VOLUME] [PAUSE]        │
├─────────────────────────────────────────────┤
│  DEPT 3 — Q&A LIBRARY                      │
│  📚 Books = knowledge base                 │
│  🔄 Multi-turn path between shelves        │
│  💬 Chitchat lounge in corner              │
│  🤖 Active Learning robot taking notes     │
├─────────────────────────────────────────────┤
│  DEPT 2 — CLU LAB                          │
│  🎯 Intent wall with labels                │
│  🏷️ Entity tags hanging from ceiling       │
│  💬 Utterance examples pinned everywhere   │
│  4 entity boxes: LEARNED LIST PRE-BUILT    │
│                  REGEX                     │
├─────────────────────────────────────────────┤
│  DEPT 1 — TEXT ANALYSIS ROOM               │
│  😊😐😢 Sentiment meters on wall           │
│  🏷️ NER scanner: finds names/places/orgs  │
│  🔒 PII detector: redacts personal data    │
│  🔑 Key phrase extractor: pulls topics     │
│  🌍 Language detector: identifies scripts  │
└─────────────────────────────────────────────┘
```

---

## 🎯 Exam Priority Checklist

### Must Know

- [ ] NER vs Entity Linking — classify vs connect to knowledge base
- [ ] Prebuilt NER vs Custom NER vs PII Detection — when to use each
- [ ] Sentiment Analysis vs Opinion Mining — overall vs subject-specific
- [ ] 4 CLU entity types — Learned, List, Pre-built, Regex
- [ ] Full CLU lifecycle — 7 steps in order
- [ ] Q&A multi-turn steps — follow-up prompt, create link, done
- [ ] What chitchat is and when to use it
- [ ] WER — what it is and what percentages mean
- [ ] SSML elements and what each controls
- [ ] Text Translation vs Document Translation differences
- [ ] 4 Speech Translation tools — Translator, API, CLI, SDK, Studio

### Should Know

- [ ] 3 ways to use key phrase extraction — Studio, programmatic, Docker
- [ ] Pattern matching vs CLU — offline vs cloud
- [ ] Custom Speech — when to use and how to test
- [ ] Keyword recognition — basic vs advanced model
- [ ] Active learning for Q&A optimization
- [ ] Custom Neural Voice (CNV) and batch synthesis API
- [ ] Document translation — preserves formatting, multi-language support

### Good to Know

- [ ] How client app interacts with CLU — 5 step flow
- [ ] Backup and recover knowledge base
- [ ] Export knowledge base
- [ ] Multi-language Q&A solution
- [ ] Custom translation with glossaries
- [ ] Alternative phrasing in Q&A

---

## ❓ Quick Self-Test

**Q1. Difference between NER and Entity Linking?**

<details>
<summary>▶ Click to reveal answer</summary>

| Property | NER | Entity Linking |
|----------|-----|----------------|
| **Does** | Classifies entity type | Links entity to knowledge base |
| **Output** | Person, Location, Org | Entity + Wikipedia URL |
| **Example** | "Microsoft" → Organization | "Microsoft" → wikipedia.org/Microsoft |

</details>

---

**Q2. Customer support tickets contain customer names and phone
numbers that must be removed. Which feature?**

<details>
<summary>▶ Click to reveal answer</summary>

**PII Detection** — finds and redacts personally identifiable information
like names, phone numbers, email addresses, SSN

</details>

---

**Q3. Company needs to extract "PolicyNumber" and "ClaimCode"
from insurance documents. Prebuilt NER or Custom NER?**

<details>
<summary>▶ Click to reveal answer</summary>

**Custom NER** — "PolicyNumber" and "ClaimCode" are not standard
entity types. You need to define and train your own entity types.

Prebuilt NER only recognizes standard types like Person, Location, Organization.

</details>

---

**Q4. What are the 4 CLU entity types?**

<details>
<summary>▶ Click to reveal answer</summary>

| Type | What It Matches |
|------|----------------|
| **Learned** | Patterns learned from labeled examples |
| **List** | Exact values from a fixed list |
| **Pre-built** | Built-in types (numbers, dates, emails) |
| **Regex** | Text matching a specific pattern |

</details>

---

**Q5. A speech model transcribes 100 words and gets 8 wrong.
What is the WER and is the model production ready?**

<details>
<summary>▶ Click to reveal answer</summary>

**WER = 8%**

| WER Range | Quality |
|-----------|---------|
| Under 5% | Excellent |
| **5% to 15%** | **Good — acceptable for most uses** |
| Over 15% | Needs improvement |

8% = Good — acceptable for most uses but not excellent.
More training could improve it.

</details>

---

**Q6. What does SSML control and name 3 elements?**

<details>
<summary>▶ Click to reveal answer</summary>

SSML controls HOW text is spoken — not just what is said.

| Element | Controls |
|---------|---------|
| `<voice>` | Which voice to use |
| `<prosody rate>` | Speaking speed |
| `<prosody pitch>` | Voice pitch |
| `<break>` | Pauses in speech |

</details>

---

**Q7. Translate a 200-page legal document preserving all
formatting. Which service?**

<details>
<summary>▶ Click to reveal answer</summary>

**Document Translation**

| Property | Detail |
|----------|--------|
| Handles | Large files — PDF, Word, PowerPoint |
| Preserves | Original formatting |
| Use case | Full documents, not short strings |

Text Translation = short strings only, no formatting preserved.

</details>

---

**Q8. Difference between Pattern Matching and CLU?**

<details>
<summary>▶ Click to reveal answer</summary>

| Property | Pattern Matching | CLU |
|----------|-----------------|-----|
| Works offline | ✅ Yes | ❌ No |
| Setup | Simple | Complex — train a model |
| Accuracy | Lower | Higher |
| Best for | Quick offline prototypes | Production applications |

</details>

---

*Domain 05 — Merged: Bobby Russell Episode 5 and technical reference*  
*Part of the AI-102 study repository*