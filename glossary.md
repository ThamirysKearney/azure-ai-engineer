# AI-102 Glossary

> All key terms for the Azure AI Engineer exam, organized alphabetically.
> ⭐ = high-frequency exam term

---

## A

**A2A (Agent-to-Agent)** — Protocol allowing AI agents to communicate with each other directly.

**Agent** ⭐ — AI system that combines a language model with tools, memory, and planning to take autonomous actions. Not just a chatbot — it *does* things.

**Alert (Azure Monitor)** — Notification triggered when a metric crosses a defined threshold.

**API Key (Subscription Key)** ⭐ — Authentication credential passed in the `Ocp-Apim-Subscription-Key` header. Each service has two keys for rotation.

**Azure AI Foundry** ⭐ — Microsoft's unified platform for building, deploying, and managing AI solutions. All paths lead to a Project.

**Azure AI Search** ⭐ — Fully managed search service with AI enrichment capabilities. Used for knowledge mining and RAG solutions.

**Azure Container Instances (ACI)** — Serverless container hosting for single containers with no orchestration needed.

**Azure Kubernetes Service (AKS)** — Managed Kubernetes for running complex multi-container applications.

**Azure Monitor** — Platform service for collecting metrics, logs, and alerts from Azure resources.

**Azure OpenAI** ⭐ — Azure-hosted version of OpenAI models (GPT-4, GPT-3.5, DALL-E, embeddings) with enterprise security.

---

## B

**Blocklist** — Custom list of words/phrases that Content Safety will automatically block.

**Bounding Box** — Rectangle coordinates identifying WHERE an object is located within an image. Used in object detection.

---

## C

**Chunking** ⭐ — Breaking documents into smaller pieces before indexing in vector search. Affects RAG quality.

**CI/CD** — Continuous Integration / Continuous Deployment. Automated pipeline: code change → test → deploy.

**Classification (ML)** ⭐ — Predict a category label. Examples: spam/not-spam, dog/cat/bird.

**CLU (Conversational Language Understanding)** ⭐ — Replaces LUIS. Used to build custom intent/entity recognition models for chatbots.

**Clustering (ML)** — Find natural groups in unlabeled data. No predefined categories.

**Composed Model** — Document Intelligence model combining multiple custom models to handle different document types.

**Content Filter** ⭐ — Azure OpenAI feature that blocks content by category (hate, violence, sexual, self-harm) and severity level.

**Custom NER** ⭐ — Train your own named entity recognizer for domain-specific entity types.

**Custom Speech** — Train Speech service with your own audio data for specific accents or terminology.

**Custom Translator** — Fine-tune translation models on your domain-specific vocabulary.

**Custom Vision** ⭐ — Train your own image classification or object detection model using labeled images.

---

## D

**DALL-E** — Azure OpenAI model for generating images from text prompts.

**Data Source (AI Search)** — Connection to where documents live (Blob Storage, SQL, Cosmos DB, etc.).

**DefaultAzureCredential()** ⭐ — Python SDK class for Entra ID authentication. Tries multiple credential methods automatically.

**Diagnostic Settings** — Azure Monitor component that routes logs to storage, Event Hub, or Log Analytics.

**Document Intelligence** ⭐ — Azure service for extracting structured data from documents (invoices, receipts, forms, IDs).

**Document Translation** — Azure Translator feature for translating entire files (PDFs, Word docs, etc.).

---

## E

**Embedding** ⭐ — Mathematical vector representation of text that captures semantic meaning. Similar texts have similar vectors. Used in vector search and RAG.

**Endpoint** ⭐ — The URL where you send API requests to call an Azure AI service.

**Entity (CLU)** — Specific piece of information extracted from an utterance. Example: "Paris" is a Location entity.

**Entra ID** ⭐ — Microsoft's identity platform (formerly Azure AD). Used for enterprise-grade authentication with RBAC.

---

## F

**Face API** ⭐ — Azure service for face detection, verification (same person?), and identification (who is this?).

**Fine-tuning** ⭐ — Retraining a model on your own data to change its behavior, style, or format. Different from RAG — use for behavior, not facts.

**Foundry Agent Service** — Azure's managed platform for building and hosting AI agents with tools.

**Foundry Hub** — Top-level container in Azure AI Foundry. Contains multiple projects and shared resources.

**Foundry Project** — Workspace for a single AI application within a Hub.

**Function Calling** ⭐ — Ability for an AI model to request execution of external functions/APIs.

---

## G

**GPT-4V** — GPT-4 with Vision — multimodal model that can analyze both text and images.

**Groundedness** — Evaluation metric: does the AI response stay true to the provided source documents? (Used in RAG evaluation)

**Groundedness Detection** — Content Safety feature that checks if model responses are grounded in source data.

---

## H

**Handoff** — In multi-agent systems, when one agent passes a task to another specialized agent.

**Hub → Project** ⭐ — Azure AI Foundry hierarchy. Hub = shared infrastructure. Project = individual app workspace.

**Hybrid Search** — Combines keyword search and vector search for best overall results.

---

## I

**Image Analysis** ⭐ — Azure Vision feature that returns tags, captions, objects, brands, and color from images.

**Image Classification** — Assign a whole-image label. What IS this? (Custom Vision)

**Index (AI Search)** ⭐ — The searchable data structure that stores processed document content.

**Indexer (AI Search)** ⭐ — The process that reads from a data source, runs enrichment, and populates the index.

**Intent (CLU)** — What a user wants to do. Example: "BookFlight", "CheckWeather".

---

## K

**Key Vault** — Azure service for securely storing and managing API keys, secrets, and certificates.

**Knowledge Store** — AI Search feature that saves enriched document data to storage for later analysis.

---

## L

**Layout Model (Document Intelligence)** — Prebuilt model that extracts tables, text, and structure from any document type.

**LUIS** — Legacy conversational AI service. Now replaced by CLU (Conversational Language Understanding).

---

## M

**MCP (Model Context Protocol)** ⭐ — Standard protocol for connecting AI agents to external tools and data sources.

**Managed Deployment** — Dedicated compute capacity for model deployment. Predictable throughput, more control.

**Metrics (Azure Monitor)** — Real-time numerical measurements (requests/second, latency, error rate).

**Model Catalog** — Library of 1,700+ AI models in Azure AI Foundry (Azure OpenAI, open-source, third-party).

**Multi-agent** ⭐ — Architecture where multiple specialized agents collaborate on a complex task.

**Multimodal** — AI system that processes multiple input types (text + images + audio).

---

## N

**NER (Named Entity Recognition)** ⭐ — Identify and classify entities in text: people, places, organizations, dates.

**NLP (Natural Language Processing)** — Field of AI focused on understanding and generating human language.

---

## O

**Object Detection** ⭐ — Locate and classify multiple objects in an image with bounding boxes. WHERE are things?

**OCR (Optical Character Recognition)** ⭐ — Extract text from images. Azure Vision's Read API handles printed + handwritten text.

**Orchestrator** — In multi-agent systems, the central agent that delegates subtasks to specialized agents.

---

## P

**PII (Personally Identifiable Information)** ⭐ — Personal data like SSN, email, phone number. Azure Language has a PII Detection feature.

**PHI (Protected Health Information)** — Medical personal data. Also detected by Azure Language PII feature.

**Prompt Engineering** — Designing better prompts to improve model output. No training required.

**Prompt Flow** — Azure AI Foundry tool for building and testing LLM-based workflows visually.

**Prompt Shield** ⭐ — Content Safety feature that detects prompt injection attacks (user attacks, document attacks, third-party attacks).

---

## Q

**Quota** — Limit on tokens per minute (TPM) for model deployments. Can be adjusted per deployment.

---

## R

**RAG (Retrieval Augmented Generation)** ⭐ — Pattern that injects relevant document chunks into an LLM prompt so it answers based on YOUR data.

**RBAC (Role-Based Access Control)** — Access management using roles: Owner, Contributor, Reader, etc.

**Read API** ⭐ — Azure Vision feature for extracting text from images and documents (printed + handwritten).

**Regression (ML)** — Predict a continuous number. Example: house price prediction.

**Resource Group** — Azure container that groups related resources for management and billing.

---

## S

**Semantic Search** — Search that understands meaning, not just keywords. Re-ranks results by relevance.

**Semantic Ranking** — AI Search feature that re-orders results based on semantic relevance to the query.

**Serverless Deployment** — Pay-per-token model hosting. No infrastructure management, auto-scales.

**Skillset (AI Search)** ⭐ — Collection of AI enrichment steps applied during indexing (OCR, NER, language detection, translation).

**Spatial Analysis** — Azure Vision feature for analyzing people movement and presence in video feeds.

**SSML (Speech Synthesis Markup Language)** ⭐ — XML format for controlling text-to-speech output (speed, pitch, pauses, voice).

**Subscription** — Top-level Azure billing account.

**Supervised Learning** — ML training with labeled examples (input + correct output provided).

---

## T

**Tokenization** — Breaking text into smaller units (tokens) for processing by NLP models.

**Tool (Agent)** ⭐ — External capability an agent can invoke: database queries, API calls, file operations, code execution.

**TTS (Text-to-Speech)** ⭐ — Convert written text to spoken audio. Controlled with SSML.

---

## U

**Unsupervised Learning** — ML training without labels. Model finds patterns on its own. Example: clustering.

**Utterance (CLU)** — Example phrase a user might say. Used to train intent recognition.

---

## V

**Vector Search** ⭐ — Find semantically similar content using mathematical distance between embeddings.

**Video Indexer** ⭐ — Azure service that extracts insights from video: faces, OCR, scenes, topics, transcription.

---

## W

**W-2 Tax Form Model** — Document Intelligence prebuilt model for extracting US tax form data.

---

*Last updated: April 2026*