# Practice Questions & Self-Tests

> Use these to quiz yourself. Cover the answer, read the question, then check.
> Add your own questions as you study!

---

## 📊 Practice Assessment Log

| Date | Score | Weak Areas Identified |
|------|-------|----------------------|
| Day 20 (May 8) | __%  | _(fill in after taking)_ |
| Day 35 (May 27) | __%  | _(fill in after taking)_ |
| Day 45 (Jun 12) | __%  | _(fill in after taking)_ |
| Day 50 (Jun 18) | __%  | _(fill in after taking)_ |
| Day 51 (Jun 19) | __%  | _(fill in after taking)_ |

🔗 [Free Microsoft Practice Assessment](https://learn.microsoft.com/credentials/certifications/azure-ai-engineer/?practice-assessment-type=certification)

---

## 🔐 Domain 1 — Plan & Manage

**Q1:** Your team needs to authenticate to Azure AI services using identities managed in Azure Active Directory. Which authentication method should you use?
> **A:** Entra ID with `DefaultAzureCredential()`

**Q2:** You deploy a single AI container that runs independently. Which Azure service should you use?
> **A:** Azure Container Instances (ACI) — not Kubernetes

**Q3:** You want to be notified when the error rate for your Azure AI service exceeds 5% in a 5-minute window. What Azure Monitor component do you configure?
> **A:** Alerts

**Q4:** A user's prompt is trying to override the system instructions and make the model behave maliciously. What Content Safety feature detects this?
> **A:** Prompt Shields

**Q5:** You need to estimate the monthly cost of running Azure OpenAI before deploying it. What tool do you use?
> **A:** Azure Pricing Calculator

---

## 🤖 Domain 2 — Generative AI

**Q6:** You want the model to answer questions specifically about your company's internal documentation. The model should not use knowledge outside those documents. Which approach?
> **A:** RAG (Retrieval Augmented Generation)

**Q7:** You want the model to always respond in a specific formal tone and structured JSON format. Training data is not the issue. Which approach?
> **A:** Fine-tuning (behavior/style/format)

**Q8:** What is the role of the `system` message in the Chat Completions API?
> **A:** Defines persistent behavior instructions for the assistant

**Q9:** In the RAG pattern, what converts both documents and user questions into vectors?
> **A:** Azure OpenAI Embeddings API

**Q10:** Which evaluation metric measures whether the AI response is based on the source documents (not hallucinated)?
> **A:** Groundedness

---

## 🦾 Domain 3 — Agents

**Q11:** What is the key difference between a chatbot and an AI agent?
> **A:** Agents can use tools to take actions; chatbots only generate text

**Q12:** An orchestrator agent breaks a task into subtasks and delegates to specialized agents. What pattern is this?
> **A:** Multi-agent pattern

**Q13:** What protocol standardizes how AI agents connect to external tools?
> **A:** MCP (Model Context Protocol)

---

## 👁️ Domain 4 — Computer Vision

**Q14:** You need to identify and locate multiple objects in an image, returning a bounding box for each. Which service?
> **A:** Custom Vision — Object Detection

**Q15:** You need to verify whether two photos are of the same person for a security application. Which API?
> **A:** Azure Face API — Verification

**Q16:** You want to extract handwritten text from scanned forms. Which Azure Vision feature?
> **A:** Read API (OCR)

**Q17:** What is the difference between Image Classification and Object Detection?
> **A:** Classification labels the whole image; Object Detection locates multiple objects with bounding boxes

---

## 📝 Domain 5 — NLP

**Q18:** You need to automatically find and redact Social Security Numbers from text documents. Which feature?
> **A:** Azure Language — PII Detection

**Q19:** You want to extract "ClaimNumber" and "PolicyHolder" as entities — types specific to your insurance company. Which feature?
> **A:** Azure Language — Custom NER (prebuilt NER doesn't know your custom types)

**Q20:** You want to control the speaking speed and pitch of a TTS response. What do you use?
> **A:** SSML (Speech Synthesis Markup Language)

**Q21:** What replaced LUIS in Azure AI services?
> **A:** CLU (Conversational Language Understanding)

**Q22:** In CLU, what is an "utterance"?
> **A:** An example phrase a user might say to express an intent

---

## 📄 Domain 6 — Info Extraction & Knowledge Mining

**Q23:** You need to extract data from invoices from multiple vendors — each with a different layout. Which Document Intelligence approach?
> **A:** Custom Extraction model (or Composed model if multiple custom models needed)

**Q24:** What Document Intelligence model would you use to extract tables and text structure from any arbitrary document?
> **A:** Layout model

**Q25:** In Azure AI Search, what component reads from the data source and populates the index?
> **A:** The Indexer

**Q26:** You want to combine keyword search and vector search in Azure AI Search. What is this called?
> **A:** Hybrid search

**Q27:** What Azure AI Search feature saves enriched document data to Azure Storage for further analysis?
> **A:** Knowledge Store

---

## ❓ My Own Questions (add as you study)

| Question | Answer | Domain |
|----------|--------|--------|
| _(add your questions here)_ | | |

---

*Resources — Part of the AI-102 study repository*