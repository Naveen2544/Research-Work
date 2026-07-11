<h1 align="center">QueryLess</h1>
<h3 align="center">A Privacy-Preserving and Reasoning-Enhanced Multi-Agent Framework for Clinical Text-to-SQL Generation</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Domain-Clinical_NLP-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Architecture-Multi--Agent-purple?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Privacy-Differential_Privacy-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Reliability_Score-81.05%25-brightgreen?style=for-the-badge"/>
</p>

---

### 📋 Abstract

Electronic Health Records (EHRs) hold enormous clinical value, but extracting insights from them typically requires SQL expertise that most clinicians don't have — creating bottlenecks that can delay diagnosis and treatment. **QueryLess** is a web-based, privacy-first Text-to-SQL framework built specifically for clinical data. It combines a **"System 2" reasoning architecture** (built on GPT-5) with schema linking grounded in medical ontologies (SNOMED-CT / ICD-10), multi-agent query decomposition, and a differential privacy layer — enabling clinicians to query EHR data in natural language while staying HIPAA-compliant. On the EHRSQL and MIMIC-IV benchmarks, QueryLess achieves a state-of-the-art **Reliability Score of 81.05%**.

---

### 👥 Authors

| Name | Department |
|---|---|
| Martin David M | AI & Data Science, Agni College of Technology |
| Navaneetha Krishnan T M | AI & Data Science, Agni College of Technology |
| Johncy Rebecca F | AI & Data Science, Agni College of Technology |
| Tamil Selvi B | AI & Data Science, Agni College of Technology |
| Amala Preyadarchane | Electrical & Electronics Engineering, Agni College of Technology |

*Anna University, Chennai, India*

---

### 🧠 Core Contributions

- **System-2 Reasoning** — Deep, multi-step temporal reasoning over longitudinal patient records using GPT-5
- **Ontology-Aware Schema Linking** — LinkAlign maps natural language to standardized medical vocabularies (SNOMED-CT / RxNorm) before SQL generation
- **Modular Multi-Agent Decomposition** — MAC-SQL agents break complex clinical questions into verifiable logic chains (Decomposer → Selector → Refiner)
- **Differential Privacy** — A SmartNoise middleware layer injects calibrated statistical noise into query results, preserving HIPAA compliance without destroying analytical utility

---

### ⚙️ Architecture

QueryLess is formalized as a composite pipeline:

```
R = Privacy( Execute( Optimize( Reason( Link(Q, S) ) ) ) )
```

| Module | Function |
|---|---|
| **Semantic Alignment** | Prunes massive EHR schemas (e.g., OMOP CDM) down to a relevant sub-schema using bi-encoder retrieval + cross-encoder reranking |
| **Reasoning Core** | Multi-agent Chain-of-Thought decomposition of complex temporal clinical logic |
| **Optimization Layer** | Hybrid routing engine using semantic caching and adaptive model selection to cut latency and cost |
| **Privacy Enforcement** | Differential Privacy (Laplace mechanism) noise injection and PII masking before results are returned |

---

### 📊 Key Results

| Metric | QueryLess (Ours) | Best Baseline |
|---|---|---|
| Reliability Score (RS-10) | **82.1%** | 76.9% (PLUQ) |
| Execution Accuracy (Avg.) | **88.1%** | 81.0% (GPT-4o, CoT) |
| Schema Generation (Avg. ECS/PKC/FKC) | **93.7 / 100 / 100** | 78.8 / 100 / 100 (DeepSeek V2.5, CoT) |
| Token Efficiency (TEP Score) | **1.85** | 0.42 (Agentic CoT) |
| End-to-End Latency | **3.8s** (hybrid) | 16.5s (pure agentic) |
| Cost per 1,000 Queries | **$0.028** | $0.15 |
| Aggregation Relative Error (ε = 1.0) | **2.1%** | — |

- Schema linking (LinkAlign) cut average input tokens by **87.7%** versus full-schema ingestion
- Adaptive routing pushed throughput to **28 queries/minute**, a 7× improvement over the baseline
- Differential privacy added only **+1.5s** per query while keeping aggregation error under 2.1%

---

### 🩺 Proposed Deployment

A deployment framework is proposed for **Apollo Hospitals, Chennai**, on their existing Nutanix-based Hospital Information System. Projected impact: reducing administrative decision latency from **24–48 hours to under 15 seconds**, and cutting reporting costs from **~$50/analyst-hour to $0.028/query**.

---

### 🔭 Future Work

- Extending beyond single-cloud deployments via **Federated Learning** for cross-institutional collaboration while preserving data sovereignty

---

### 🔑 Keywords

`Large Language Models` `Privacy-Preserving AI` `Multi-Agent Systems` `Semantic Schema Linking` `Differential Privacy` `Clinical Decision Support`

---

### 📄 Citation

If you reference this work, please cite:

> Martin David M, Navaneetha Krishnan T M, Johncy Rebecca F, Tamil Selvi B, Amala Preyadarchane, "QueryLess: A Privacy-Preserving and Reasoning-Enhanced Multi-Agent Framework for Clinical Text-to-SQL Generation," Department of Artificial Intelligence & Data Science, Agni College of Technology, Anna University, Chennai, India.

---

### 📫 Contact

**Navaneetha Krishnan T M** — navaneeth.2860@gmail.com · [LinkedIn](https://linkedin.com/in/naveen2544)
