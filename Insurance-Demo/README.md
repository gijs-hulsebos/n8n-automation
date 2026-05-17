# 🛡️ Enterprise-Grade AI Autonomous Insurance Triage Adjuster

![Workflow Canvas](https://raw.githubusercontent.com/gijs-hulsebos/n8n-automation/main/Insurance-Demo/Image%2017-05-2026%20at%2020.43.jpeg)

---

## 📝 Executive Summary
This **n8n-native autonomous agent** is engineered by [Gijs Hulsebos](https://gijshulsebos.com) as a high-reliability insurance processing layer. Moving beyond linear automation, this project utilizes an **Agentic Framework** to perform complex visual and textual damage assessments, implement automated triage, and manage sensitive PII data through a secure vaulting strategy.

---

## 🔥 Technical Highlights 

* **🛡️ Dual-Model Fallback Architecture**: A robust multi-layer system using **GPT-5-mini** as the primary engine with an automated fallback to **Gemini 2.5 Flash**, ensuring reasoning continuity and high availability.
* **🧠 PII Isolation & GDPR Vaulting**: Implementation of a specialized "Separate Sensitive Data" phase that strips PII before AI processing, ensuring only anonymized incident data reaches the LLM providers.
* **🔒 Logic-Based Triage Gate**: The workflow utilizes a "Human Review?" logic gate that automatically triggers manual adjuster intervention if AI confidence scores fall below 40 or if the incident is flagged as high-urgency (Level 3).
* **📊 Structured Output Parsing**: Integrated Structured Output Parser ensures the AI Agent returns strictly formatted JSON objects for seamless database integration and automated decision-making.
* **🖱️ Multi-Channel Response Orchestration**: Automatically coordinates professional client communications via Gmail, internal adjuster alerts, and real-time status updates to the Vercel-hosted web portal.
* **🌍 Resilient Error Management**: A dedicated "Phase 5B" sub-layer that logs system errors to a secondary "Error Log" sheet and notifies engineers via Gmail if the pipeline encounters unexpected data.

---

## 🛠️ Chatbot Technical Specifications
These core features are integrated into the agent's logic to ensure a reliable and professional insurance adjusting experience.

| Architecture | Technical Description | Tools Stack | Business Impact |
| :--- | :--- | :--- | :--- |
| **Data Intake** | Secure Webhook entry point that structures incoming incident reports, policy numbers, and images. | n8n Webhook, Header Auth | Secure Global Entry |
| **Privacy Layer** | Mandatory PII vaulting that logs sensitive data to a master sheet before stripping it for AI analysis. | n8n GDPR Logic, Google Sheets | 100% GDPR Compliance |
| **Damage Assessment** | High-fidelity analysis of incident descriptions and images to determine technical component damage. | AI Agent, GPT-5-mini | Reduced Adjuster Workload |
| **Triage Logic** | Categorizes claims into "Approved" or "Rejected" based on custom-tuned "Senior Adjuster" system prompts. | n8n If/Else, System Message | Instant Claim Processing |
| **Escalation Protocol** | Identifies high-risk/fatal incidents (Level 3) and escalates them to senior technical adjusters immediately. | Human-in-the-Loop Approval | High-Risk Mitigation |
| **Client Comms** | Dispatches automated HTML-formatted emails for confirmation, approval updates, and rejection notices. | Gmail API, OAuth2 | Enhanced Client Transparency |
| **Audit Logging** | Real-time synchronization of AI reasoning, confidence scores, and technical summaries to a master sheet. | Google Sheets API v4 | Fully Audit-Ready Pipeline |
| **Model Redundancy** | High-availability architecture that switches to Gemini 2.5 Flash if the primary model hits constraints. | Dual LLM Setup (Gemini + GPT) | 99.9% Triage Uptime |

---

## 🛠️ Architecture & Stack

* **Orchestration**: n8n (Cloud-hosted)
* **AI Models**: OpenAI GPT-5-mini (Standard) & Google Gemini 2.5 Flash (Fallback)
* **Data Privacy**: PII Isolation Layer (Phase 3)
* **Integrations**: 
    * **Google Sheets API**: Serving as the master claim database and PII Vault.
    * **Gmail API**: For automated adjuster escalations and client feedback loops.
    * **Webhook Gateway**: Secure bridge between the Vercel frontend and the n8n execution layer.

---

## ⚙️ Deployment & Governance

> [!TIP]
> **Engineering Excellence:** For the full technical breakdown, credential mapping, and step-by-step installation instructions, see the **[Technical Setup Guide](./Setup.md)**.

---

## ⚠️ Compliance & Security
This system adheres to the **Principle of Least Privilege**. All API scopes (Gmail, Sheets) are limited to the specific claim workbook. Sensitive policyholder data is isolated and never shared with AI models. All secrets are managed via n8n's encrypted credential manager.

---

## 🌐 Let's Connect
Currently open for high-impact collaborations in the field of AI automation for Fintech and Insurance.

Website: [gijshulsebos.com](https://gijshulsebos.com)
Email: gijs@gijshulsebos.com

---

<p align="center">
  <a href="https://gijshulsebos.com" target="_blank">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
  </a>
</p>
