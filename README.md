# 15n8n-error-handling-branching-logic

# Project 15: Error Handling & Branching Logic in n8n Workflows

## 📋 Business Problem
In production-grade automation environments, external APIs and third-party services can fail unexpectedly (due to timeouts, server errors, or invalid payloads). Without robust error handling, entire workflows halt, leading to unhandled data loss, missed notifications, and system downtime.

## 💡 Proposed Solution
Engineered a **Resilient Workflow Architecture** in n8n utilizing conditional **Branching Logic (IF Node)** and node-level configurations to gracefully intercept system failures, isolate error states, and divert erratic payloads into dedicated alternative paths (*False Branch* / *Error Handlers*).

## 🛠️ Architecture & Flow
1. **Trigger & Request:** Initiates data retrieval from an external service via an `HTTP Request` node.
2. **Conditional Validation (IF Node):** Evaluates incoming JSON responses or schema properties (e.g., verifying mandatory data blocks like `slideshow.author`).
3. **Happy Path (True Branch):** Processes normal operational data seamlessly when conditions are met.
4. **Error Handler Path (False Branch):** Automatically routes failed or malformed payloads into a secondary handler branch for logging, alerting, or retry mechanisms.

<img width="1145" height="457" alt="image" src="https://github.com/user-attachments/assets/4bd9772a-6c6a-42ac-aa73-548a2fe5173d" />


## 🧰 Tools & Nodes Used
- **Platform:** n8n (Self-hosted / Cloud)
- **n8n Nodes:** 
  - Manual Trigger
  - HTTP Request (with configuration for failure isolation)
  - IF Node (Conditional data routing)
  - Code Node / Set Node (Data transformation & labeling)
 
<img width="1124" height="748" alt="image" src="https://github.com/user-attachments/assets/37fd6e3d-8792-4848-983e-7673292cd4a3" />


## 🚀 Business Value & Impact
- **System Reliability:** Prevents total workflow crashes when external endpoints fail.
- **Proactive Alerting:** Enables teams to catch issues instantly via segregated error branches rather than discovering failures days later.
