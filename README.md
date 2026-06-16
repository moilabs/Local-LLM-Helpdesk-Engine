# Local-LLM-Helpdesk-Engine

A privacy-first, autonomous ticket triage and routing engine powered by a local Large Language Model (LLM) and n8n workflow orchestration. This system is engineered to automatically intercept, analyze, classify, and draft context-aware responses for multilingual enterprise IT support tickets without exposing sensitive data to third-party cloud APIs.

---

## 🎯 Business Value & Problem Solved
In modern enterprise environments, IT helpdesks face high ticket volumes, language barriers, and data privacy risks (GDPR compliance). 
This project builds a **Secure Core Infrastructure** that:
- **Reduces Response Latency:** Automates the first line of defense via instant Ticket Triage & Categorization.
- **Ensures Absolute Data Privacy:** Uses a localized LLM via Ollama, keeping sensitive corporate emails and user credentials entirely within the local infrastructure.
- **Eliminates Language Barriers:** Operates seamlessly across multiple languages (English, Finnish, Bengali) without requiring manual translation layers.

---

## 🛠️ Architecture & Tech Stack

### Orchestration & Integration
- **n8n (Advanced Workflow Automation):** Manages the end-to-end data pipelines, conditional branching, and API webhooks.
- **Gmail API:** Acts as both the ingestion engine (incoming tickets) and the resolution dispatcher (HTML draft delivery).
- **Google Sheets API:** Serves as the centralized, structured audit log and ticket database.
- **Slack Webhooks:** Dispatches real-time alerting to IT infrastructure teams for instant operational awareness.

### Artificial Intelligence
- **Ollama (Local LLM Execution):** Runs optimized models (e.g., Llama 3 / Mistral) locally for high-speed, zero-cost semantic analysis and strict JSON schema generation.

---

## 🔄 Workflow Capabilities

### 1. Ingestion, Semantic Triage & Alerting (Workflow 1)
- **Multilingual Analysis:** Intercepts live emails in **English, Finnish, or any Languages**.
- **Local AI Triage:** Extracts the core intent and strictly categorizes tickets into structured tokens (`Set_Password`, `Set_Hardware`, `Set_Software`, or `Others`).
- **Data Logging & Operations:** Appends structured records to the Google Sheets database and simultaneously triggers a real-time Slack notification containing critical ticket payload summaries.

### 2. Resolution Feedback Loop & Auto-Responder (Workflow 2)
- **Status Trigger:** Fires automatically when an IT analyst updates a ticket status to `Resolved` in Google Sheets.
- **Conditional Branching:** Evaluates case-sensitive parameters via advanced `If` nodes.
- **Nordic Gold-Standard Communication:** Dispatches a professionally styled HTML resolution confirmation email to the user.
- **Anti-Duplication Control:** Enforces strict compliance notes instructing users on proper response protocols to prevent database and thread duplication.

---

## 📸 Core Architecture Layouts

> *The sections below illustrate the live execution maps, data payload validation, and multi-channel system outputs captured from the active engine environment.*

### 🖥️ 1. Ingestion & AI Triage Pipeline (Workflow 1)
<img width="1409" height="743" alt="Image_1" src="https://github.com/user-attachments/assets/9283b4b1-ce15-4614-8790-71cfccf955d1" />

*Figure 1: Comprehensive Ingestion, AI Categorization, and Multi-Channel Routing Pipeline built in n8n.*


### 🔄 2. Resolution Feedback Loop (Workflow 2)
<img width="1001" height="321" alt="2" src="https://github.com/user-attachments/assets/e22aac59-1beb-476f-9540-334e445a680f" />

*Figure 2: Resolution Feedback Loop executing case-sensitive validation and rendering HTML client communications.*


### 📊 3. Centralized Audit Log & Database (Google Sheets)
<img width="850" height="351" alt="google sheet" src="https://github.com/user-attachments/assets/0c60c9b1-6473-4b7f-a477-dace0ec67843" />

*Figure 3: Live structured ticket database showing automated LLM classification fields.*


### 🚨 4. Real-Time Incident Alerting (Slack Integration)
<img width="661" height="577" alt="46625dc2-a6de-4193-9b74-4f6fd7a1001a" src="https://github.com/user-attachments/assets/523b3dcf-575b-48c4-99b5-5b33df7c0bc8" />

*Figure 4: Automated Slack notifications delivered to the IT infrastructure channel for instant team awareness.*


### 📧 5. Production-Grade HTML Resolution Email
<img width="552" height="667" alt="e0941116-626e-43d5-b564-f108d8893d5f" src="https://github.com/user-attachments/assets/b7223407-c2cb-4aab-8052-ceca3aa10ca0" />

*Figure 5: Automated HTML response delivered to the end-user with strict thread isolation rules.*![Uploading Image_1.png…]()

---

## 🚀 Key Learning & Technical Takeaways
- **Agentic Logic Design:** Teaching an LLM to reliably output clean JSON for error-free programmatic execution.
- **API & Webhook Practicalities:** Working with OAuth credentials, polling configurations, and token payloads.
- **Edge-Case Handling:** Designing fallback mechanisms (like the `Others` classification route) to ensure zero ticket loss.
