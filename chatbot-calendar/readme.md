# 🤖 Enterprise-Grade AI Autonomous Calendar Assistant

![Workflow Canvas](./Image%2019-03-2026%20at%2016.54%20(1).jpeg)

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

---

## 📝 Executive Summary
This **n8n-native autonomous agent** is engineered by [Gijs Hulsebos](https://gijshulsebos.com) as a high-reliability personal assistant. Moving beyond simple linear automation, this project utilizes an **Agentic Framework** with tool-calling capabilities to manage complex scheduling logic, ensuring robust data integrity and professional continuity.

---

## 🔥 Technical Highlights (Recruiter & Engineering Focus)

* **🛡️ Advanced Fallback & Error Handling**: Implementation of a multi-layer fallback system. If the AI Agent fails to interpret a request or a tool returns an error, the system triggers a graceful degradation path to prevent workflow crashes.
* **🧠 State-Aware Memory Management**: Utilizes a rolling window memory (last 15 interactions). This ensures the agent maintains context during long scheduling dialogues without exceeding LLM token limits or losing "thread" coherence.
* **🔒 Identity-First Security Layer**: Built-in mandatory email verification. The agent is restricted from accessing or modifying sensitive calendar data until the requester's identity is logically validated.
* **⚡ Optimized Tool-Calling**: Configured via **OpenRouter** to use cost-effective yet high-precision models (Gemini 1.5 Flash). The agent executes precise JSON-schema tool calls for **Google Calendar (CRUD)** and **Gmail** integrations.
* **🌍 Deterministic Business Logic**: Hardcoded constraints for business hours (Mon-Fri, 09:00 - 17:00) and fixed meeting durations, preventing the AI from "hallucinating" or creating impossible bookings.
* **🛰️ Webhook-Driven Architecture**: Designed for sub-second response times, allowing the assistant to be integrated into any frontend via a RESTful API trigger.

---

## 🛠️ Architecture & Stack

* **Orchestration**: n8n (Cloud-hosted)
* **AI Engine**: OpenRouter (Gemini 1.5 Flash / GPT-4o Mini)
* **Logic**: Node-based Agentic Reasoning + Custom JavaScript Data Transformation
* **Integrations**: Google Calendar API (OAuth2), Gmail API, Webhooks

---

## ⚙️ Deployment & Governance

> [!TIP]
> **Engineering Excellence:** For the full technical breakdown, credential mapping, and error-handling documentation, see the **[Technical Setup Guide](./set-up.md)**.

---

## ⚠️ Compliance & Security
This workflow follows the **Principle of Least Privilege**. API scopes are strictly limited to necessary calendar and mail actions. All sensitive data is handled via n8n's encrypted credential manager; no secrets or tokens are stored within this repository's JSON.

---

## 🌐 Let's Connect
Currently open for new opportunities and high-impact collaborations.

Website: gijshulsebos.com
Email: gijs@gijshulsebos.com

---

<p align="center">
  <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
</p>
