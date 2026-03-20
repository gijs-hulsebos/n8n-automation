# 🤖 Enterprise-Grade AI Autonomous Calendar Assistant

![Workflow Canvas](./Image%2020-03-2026%20at%2016.02.jpeg)

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

---

## 📝 Executive Summary
This **n8n-native autonomous agent** is engineered by [Gijs Hulsebos](https://gijshulsebos.com) as a high-reliability personal assistant. Moving beyond linear automation, this project utilizes an **Agentic Framework** with dynamic tool-calling to manage complex scheduling, knowledge retrieval, and professional communication through a single API gateway.

---

### 🎥 Technical Demo Walkthrough
*A 45-second deep-dive into the agent's decision-making logic, tool-calling capabilities, and seamless integration across the Google Workspace ecosystem.*
<p align="center">
  <a href="https://www.youtube.com/watch?v=4Zaoo0YbYaw&t=627s">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/n8n-automation/main/chatbot-calendar/Image%2020-03-2026%20at%2016.02.jpeg" alt="n8n Workflow Architecture" width="750">
    <br><br>
    <img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>

---

## 🔥 Technical Highlights 

* **🛡️ Dual-Model Fallback Architecture**: A robust multi-layer system using **Gemini 2.5 Flash** as the primary engine with an automated fallback to **GPT-4o Mini** via OpenRouter, ensuring high availability and reasoning continuity.
* **🧠 Context-Aware Buffer Memory**: Implementation of a `memoryBufferWindow` that retains the last 15 interactions, enabling the agent to conduct complex, multi-step conversations without losing coherence.
* **🔒 Logic-Based Identity Verification**: The agent is programmed with a strict **Identity-First** rule: no calendar data is displayed or modified until the user has verified their email address within the chat session.
* **📊 Dynamic RAG (Retrieval-Augmented Generation)**: Utilizes a specialized Google Sheets tool to retrieve real-time technical data and portfolio information. The agent summarizes this data directly for the user to provide up-to-date responses.
* **🖱️ Interactive Metadata Output**: A custom JavaScript node filters AI outputs to pass interactive buttons (GitHub, PageSpeed, etc.) as metadata to the frontend, significantly enhancing the user experience.
* **🌍 Deterministic Business Logic**: The workflow enforces strict time zones (Europe/Amsterdam) and business parameters (Mon-Fri, 09:00 - 17:00), making bookings outside business hours impossible.

---

## 🛠️ Architecture & Stack

* **Orchestration**: n8n (Cloud-hosted)
* **AI Models**: Google Gemini 2.5 Flash & OpenAI GPT-4o Mini
* **Post-Processing**: Custom Node.js/JavaScript for URL filtering and metadata extraction
* **Integrations**: 
    * **Google Calendar API**: For full CRUD operations on calendar events.
    * **Google Sheets API**: Serving as a vector-free database for RAG operations.
    * **Gmail API**: For automated appointment confirmations and professional communication.
    * **Webhook Gateway**: For seamless integration with web frontends.

---

## ⚙️ Deployment & Governance

> [!TIP]
> **Engineering Excellence:** For the full technical breakdown, credential mapping, and error-handling documentation, see the **[Technical Setup Guide](./set-up.md)**.

---

## ⚠️ Compliance & Security
This system adheres to the **Principle of Least Privilege**. All API scopes are strictly limited to necessary actions. Sensitive data is processed via n8n's encrypted credential manager; no secrets or tokens are stored within this repository.

---

## 🌐 Let's Connect
Currently open for high-impact collaborations in the field of AI automation.

Website: [gijshulsebos.com](https://gijshulsebos.com)
Email: gijs@gijshulsebos.com

---

<p align="center">
  <a href="https://gijshulsebos.com" target="_blank">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
  </a>
</p>

