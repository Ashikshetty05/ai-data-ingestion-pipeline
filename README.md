# Production-Grade Asynchronous AI Data Ingestion Pipeline

## 📌 Project Overview
An automated backend data pipeline that captures live, streaming e-commerce transaction events via a cloud-hosted HTTP POST webhook, routes the dynamic payload to an LLM cognitive orchestration layer for real-time contextual analysis, and permanently persists the data into a structured cloud ledger.

This architecture replaces rigid, hardcoded rule engines with an elastic AI analyst capable of interpreting unstructured customer data streams on the fly, optimized for enterprise token efficiency and minimal latency.

---

## 🏗️ System Architecture

[ Raw Client Payload ] ──( HTTP POST / Live URL Parameters )──>
│
▼
┌─────────────────────────────────────────────┐
│  1. Webhook Ingestor Endpoint               │
│  (Parses: customer_name, device, price)     │
└─────────────────────────────────────────────┘
│
▼ (Dynamic State Variables)
┌─────────────────────────────────────────────┐
│  2. Cognitive LLM Orchestration Tier        │
│  (Model: gpt-5.4-mini / Zero-Shot Logic)    │
└─────────────────────────────────────────────┘
│
▼ (Structured Text Analytics)
┌─────────────────────────────────────────────┐
│  3. Relational Data Sink Store              │
│  (Target Ledger: Cloud Database / Sheets)    │
└─────────────────────────────────────────────┘

<img width="1920" height="1020" alt="20260708-0904-52 9245686" src="https://github.com/user-attachments/assets/7b6ef134-a21d-44d7-b44c-b75b24dc5eb9" />

---

## 🛠️ Technical Deep Dive

### 1. Data Ingestion (The Source)
*   **Protocol:** Asynchronous HTTP POST endpoint.
*   **Mechanism:** Built an active cloud webhook container designed to listen for data payloads. 
*   **Payload Parsing:** Programmatically isolates and maps incoming parameters (`customer_name`, `device`, `price`) from raw URL data streams into local runtime variables, ensuring data types are preserved for downstream computation.

### 2. Cognitive Orchestration Layer (The Transform)
*   **LLM Core:** `gpt-5.4-mini` (Selected deliberately to optimize for execution speed, processing cost, and model latency limits).
*   **Execution Profile:** Utilizing a strict system prompt instruction block to enforce predictable output constraints. The model processes the injected transaction data and outputs a singular, highly targeted product recommendation sentence, suppressing standard conversational filler text.
*   **Resource Efficiency:** Operational footprint minimized to a highly efficient **1.24 platform tokens/credits** per ingestion cycle.

### 3. Data Persistence Layer (The Sink)
*   **Execution:** Automated write operation to a relational cloud schema layout.
*   **Data Integrity:** Once the AI transformation resolves, a dynamic append-row execution updates the database instantly, pairing the original client metrics side-by-side with the AI-generated operational intelligence.

---

## 💼 Business Metrics & Impact
*   **Zero Human Overhead:** Eliminates manual data manipulation or static conditional string parsing.
*   **Processing Latency:** End-to-end data transit (Ingestion ➡️ AI Inference ➡️ Database Commit) resolves in **under 3.0 seconds**.
