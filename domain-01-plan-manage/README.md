# Domain 01 — Plan & Manage Azure AI Solutions

> **Exam Weight:** 20-25%
> **Bobby Russell Episode:** 1
> **Study Days:** 21-25 (Phase 2, Week 5)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_foundry_platform.md` | Azure AI Foundry — Hub, Project, Resources | Day 21 |
| `02_model_deployment.md` | Model Catalog, Serverless vs Managed | Day 22 |
| `03_auth_and_apis.md` | Authentication (3 methods), SDK patterns | Day 23 |
| `04_monitoring_cost.md` | Azure Monitor, Cost Management | Day 24 |
| `05_responsible_ai_content_safety.md` | Content Safety, Prompt Shields, Filters | Day 25 |
| `06_containers_cicd.md` | Docker, Kubernetes, CI/CD, Edge | Day 26 |

---

## 🧠 Key Exam Points for This Domain

### What Bobby Russell says to focus on:
> "When you come to the Foundry portal, all paths lead to a project."
> "Practice creating resources in the Azure AI Foundry portal."
> "Understand the three main ways to authenticate: subscription key, token, or Entra ID."
> "Know that you can use the Azure pricing calculator to estimate costs."
> "Each Azure AI service provides you two keys."
> "Deploy to a standalone Docker when you have an independent container. Deploy to Kubernetes if you have a container with multiple moving parts."

---

## 🏗️ Azure AI Foundry Hierarchy

```
Azure Subscription
└── Resource Group
    └── Azure AI Foundry Hub          ← shared infrastructure
        ├── Shared resources (storage, key vault, etc.)
        └── Foundry Project           ← individual app workspace
            ├── Models (from catalog)
            ├── Endpoints
            ├── Deployments
            └── Connections
```

---

## 🔐 3 Authentication Methods

| Method | When | Code Pattern |
|--------|------|--------------|
| **API Key** | Testing, simple apps | `AzureKeyCredential("key")` |
| **Bearer Token** | Short-lived access | `Authorization: Bearer <token>` |
| **Entra ID** | Enterprise, managed identity | `DefaultAzureCredential()` |

---

## 📊 Azure Monitor — 4 Components

| Component | Purpose |
|-----------|---------|
| **Metrics** | Real-time numbers (requests/sec, latency) |
| **Alerts** | Notify when threshold exceeded |
| **Diagnostic Settings** | Route logs to storage/analysis |
| **Activity Log** | Audit trail — who did what |

---

## 🛡️ Content Safety Categories

| Category | Detects | Severity |
|----------|---------|----------|
| Hate | Discriminatory content | 0-6 |
| Violence | Violent content/threats | 0-6 |
| Sexual | Sexual content | 0-6 |
| Self-harm | Self-harm content | 0-6 |

Features: Content Filters | Blocklists | Prompt Shields | Groundedness Detection

---

## 🐳 Container Deployment Decision

```
Single container, no dependencies → Docker / ACI
Multi-container app, orchestration needed → Kubernetes (AKS)
No internet connection required → Edge deployment
```

---

*Domain 01 — Part of the AI-102 study repository*