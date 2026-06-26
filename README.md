# 🛡️ VibeGuard

<div align="center">

### **Autonomous Reliability & AI Code Auditor**

*"You vibe the code into existence. VibeGuard makes sure it doesn't blow up in production."*

---

![License](https://img.shields.io/badge/License-MIT-blue.svg)
![Python](https://img.shields.io/badge/Python-3.10+-green)
![Next.js](https://img.shields.io/badge/Next.js-15-black)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688)
![Gemini](https://img.shields.io/badge/Gemini-AI-orange)
![LangGraph](https://img.shields.io/badge/LangGraph-MultiAgent-red)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen)

---

**An AI-native platform that continuously audits code, detects production failures, reasons over historical fixes, and autonomously proposes safe remediations through a multi-agent architecture.**

</div>

---

# 📑 Table of Contents

* Overview
* Why VibeGuard?
* Key Features
* System Architecture
* Agent Workflow
* Memory-Augmented Reasoning
* Tech Stack
* Folder Structure
* Screenshots
* Installation
* Configuration
* Running the Project
* API Overview
* Roadmap
* Contributing
* License

---

# 🚀 Overview

Modern software teams ship features at incredible speed.

Unfortunately, production failures still require engineers to manually investigate logs, search documentation, inspect dashboards, identify root causes, and apply fixes.

VibeGuard automates this entire reliability workflow.

Instead of merely detecting issues, it:

* detects failures
* diagnoses root causes
* retrieves similar historical incidents
* generates safe remediation plans
* requests human approval
* executes fixes
* validates success
* learns from every incident

Every successful repair becomes organizational knowledge stored in a semantic memory database, allowing the system to continuously improve.

---

# 🎯 Why VibeGuard?

Traditional observability platforms answer:

> **"What failed?"**

AI coding assistants answer:

> **"Here's a possible fix."**

VibeGuard answers:

> **"I know why this failed because I've seen it before. Here's the safest fix. Approve it and I'll execute it."**

---

# ✨ Key Features

## 🔍 AI Static Code Auditor

* Deep AST parsing
* Dependency graph analysis
* API misuse detection
* Security vulnerability scanning
* Configuration drift detection
* Interactive architecture visualization

---

## 🚨 Autonomous Incident Detection

Continuously monitors:

* application logs
* exceptions
* latency spikes
* CPU usage
* memory usage
* failed deployments
* infrastructure health

---

## 🧠 Fix-Memory RAG

Unlike traditional RAG systems that embed entire codebases, VibeGuard stores only:

* Incident fingerprint
* Root cause
* Successful remediation
* Validation metrics

This drastically reduces:

* token usage
* latency
* hallucinations

while improving retrieval quality.

---

## 🤖 Multi-Agent Reliability Engine

Four specialized AI agents collaborate exactly like a real Site Reliability Engineering (SRE) team.

### 🐛 Monitor Agent

Responsible for:

* anomaly detection
* metrics collection
* log aggregation
* incident creation

---

### 🔍 Diagnosis Agent

Responsible for:

* root cause analysis
* semantic retrieval
* dependency inspection
* environment validation

---

### ⚡ Action Agent

Responsible for:

* remediation planning
* rollback generation
* infrastructure patching
* configuration repair

---

### ✅ Verification Agent

Responsible for:

* execution
* health verification
* rollback if required
* memory update

---

# 🏗 System Architecture

```
                     Developer
                         │
                         ▼
               Source Code / Deployment
                         │
         ┌───────────────┴──────────────┐
         │                              │
         ▼                              ▼

 Static Code Analysis            Production Monitoring

         │                              │
         └───────────────┬──────────────┘
                         ▼

                  Monitor Agent
                         │
                         ▼
                 Diagnosis Agent
                         │
          Semantic Search (pgvector)
                         │
                         ▼
                Historical Fix Memory
                         │
                         ▼
                  Action Agent
                         │
                         ▼

             Human Approval Dashboard

                         │
                         ▼
               Verification Agent
                         │
                         ▼
               Execute + Validate
                         │
                         ▼
           Store Successful Fix in Memory
```

---

# 🔄 Incident Workflow

```
Production Error
       │
       ▼
Collect Logs
       │
       ▼
Root Cause Analysis
       │
       ▼
Retrieve Similar Incident
       │
       ▼
Generate Safe Fix
       │
       ▼
Human Approval
       │
       ▼
Execute Remediation
       │
       ▼
Verify Success
       │
       ▼
Store Knowledge
```

---

# 🧠 Memory-Augmented Reasoning

Traditional LLM pipelines often suffer from **context bloat** by sending massive logs and entire repositories to the model.

VibeGuard introduces **Fix-Memory RAG**.

### Incident Fingerprinting

Every incident is transformed into:

* stack trace hash
* exception type
* endpoint
* service
* deployment metadata
* runtime metrics

---

### Semantic Retrieval

Instead of searching raw logs, the fingerprint queries a **pgvector** database containing historical:

```
Problem

↓

Root Cause

↓

Verified Solution

↓

Outcome
```

---

### Context Minimization

Only the most relevant remediation is supplied to the LLM.

Benefits:

* lower latency
* fewer hallucinations
* lower token costs
* faster reasoning

---

### Continuous Learning

Every successful remediation becomes searchable organizational knowledge.

The more incidents solved...

the smarter the platform becomes.

---

# 🛠 Tech Stack

| Layer           | Technologies                              |
| --------------- | ----------------------------------------- |
| AI Agents       | LangGraph, Gemini ADK                     |
| LLM             | Gemini Pro, Gemini Ultra, Groq Llama3-70B |
| Backend         | FastAPI                                   |
| Frontend        | Next.js, React                            |
| Visualization   | React Flow, Recharts                      |
| Static Analysis | Tree-sitter, Semgrep, Bandit, ESLint      |
| Vector Database | PostgreSQL + pgvector                     |
| Local Storage   | SQLite                                    |
| Cache           | Redis                                     |
| Async Jobs      | Celery                                    |
| Deployment      | Docker, Cloud Run                         |

---

# 📂 Project Structure

```
vibeguard/

apps/
│
├── backend/
├── frontend/

packages/
│
├── agents/
├── database/

analysis/
│
├── static/
└── ai/

parser/

workers/

ingestion/

docker-compose.yml
```

---

# 📸 Screenshots

> Replace these placeholders with actual screenshots.

```
Dashboard

Risk Assessment

Architecture Flow

Code Graph

Incident Timeline

Approval Console
```

---

# ⚙ Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/vibeguard.git

cd vibeguard
```

---

## Install Dependencies

```bash
npm install
```

Backend

```bash
pip install -r requirements.txt
```

---

## Configure Environment

```
DATABASE_URL=

GROQ_API_KEY=

GOOGLE_API_KEY=

REDIS_URL=

NEXT_PUBLIC_API_URL=
```

---

## Start Development

```bash
npm run dev
```

Backend

```bash
uvicorn main:app --reload
```

---

Frontend

```
http://localhost:3005
```

Backend

```
http://localhost:8000
```

---

# 🌐 API Overview

| Endpoint       | Description          |
| -------------- | -------------------- |
| POST /scan     | Static code analysis |
| POST /upload   | Upload repository    |
| GET /incidents | Retrieve incidents   |
| POST /diagnose | Root cause analysis  |
| POST /approve  | Human approval       |
| POST /execute  | Execute remediation  |

---

# 📊 Business Value

## Reduce MTTR

Hours → Seconds

---

## Reduce Token Cost

Historical retrieval instead of full-context prompting.

---

## Improve Reliability

Every production incident strengthens future reasoning.

---

## Human Safety

No production action executes without explicit approval.

---

# 🚀 Future Roadmap

* Kubernetes integration
* AWS CloudWatch connector
* Azure Monitor support
* Grafana plugin
* Slack notifications
* GitHub PR comments
* Auto-generated postmortems
* Kubernetes auto-remediation
* AI deployment risk prediction
* Multi-cloud support

---

# 🤝 Contributing

Contributions are always welcome.

```
Fork

↓

Create Feature Branch

↓

Commit Changes

↓

Push Branch

↓

Open Pull Request
```

---

# 📄 License

Licensed under the MIT License.

---

# 🙌 Acknowledgements

Built using

* LangGraph
* Gemini
* FastAPI
* Next.js
* PostgreSQL
* pgvector
* Tree-sitter
* Semgrep
* React Flow

---

<div align="center">

### ⭐ If you found this project interesting, consider giving it a star!

**Built for developers who ship fast and want to sleep at night.**

</div>
