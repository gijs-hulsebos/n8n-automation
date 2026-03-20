# 🤖 Enterprise-Grade AI Autonomous Calendar Assistant

![Workflow Canvas](./Image%2020-03-2026%20at%2016.02.jpeg)

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

---

## 📝 Executive Summary
This **n8n-native autonomous agent** is engineered by [Gijs Hulsebos](https://gijshulsebos.com) as a high-reliability personal assistant. Beyond linear automation, this project utilizes an **Agentic Framework** with dynamic tool-calling to manage complex scheduling, knowledge retrieval, and professional communication through a single API gateway.

---

## 🔥 Technical Highlights 

* **🛡️ Dual-Model Fallback Architecture**: A robust multi-layer system using **Gemini 2.5 Flash** as the primary engine with an automated fallback to **GPT-4o Mini** via OpenRouter, ensuring high availability and reasoning continuity.
* **🧠 Context-Aware Buffer Memory**: Implementation of a `memoryBufferWindow` that retains the last 15 interactions. dit stelt de agent in staat om complexe, meerstaps conversaties te voeren zonder de draad kwijt te raken.
* **🔒 Logic-Based Identity Verification**: De agent is geprogrammeerd met een strikte 'Identity-First' regel: er worden geen agenda-gegevens getoond of gewijzigd voordat de gebruiker zijn e-mailadres heeft geverifieerd in de chat.
* **📊 Dynamic RAG (Retrieval-Augmented Generation)**: Gebruikt een gespecialiseerde Google Sheets-tool om real-time technische data en portfolio-informatie op te halen. De agent summarizeert deze data direct voor de gebruiker.
* **🖱️ Interactive Metadata Output**: Een aangepaste JavaScript-node filtert AI-outputs om interactieve buttons (GitHub, PageSpeed, etc.) als metadata door te geven aan de frontend, wat de gebruikerservaring aanzienlijk verbetert.
* **🌍 Deterministic Business Logic**: De workflow hanteert strikte tijdzones (Europe/Amsterdam) en zakelijke parameters (Ma-Vr, 09:00 - 17:00), waardoor boekingen buiten kantooruren onmogelijk zijn.

---

## 🛠️ Architecture & Stack

* **Orchestration**: n8n (Cloud-hosted)
* **AI Models**: Google Gemini 2.5 Flash & OpenAI GPT-4o Mini
* **Post-Processing**: Custom Node.js/JavaScript for URL filtering and metadata extraction
* **Integrations**: 
    * **Google Calendar API**: Voor volledige CRUD-operaties op events.
    * **Google Sheets API**: Als vector-vrije database voor RAG.
    * **Gmail API**: Voor geautomatiseerde bevestigingen en communicatie.
    * **Webhook Gateway**: Voor naadloze integratie met web-frontends.

---

## ⚙️ Deployment & Governance

> [!TIP]
> **Engineering Excellence:** Voor de volledige technische breakdown, credential mapping en error-handling documentatie, zie de **[Technical Setup Guide](./set-up.md)**.

---

## ⚠️ Compliance & Security
Dit systeem hanteert het **Principle of Least Privilege**. Alle API-scopes zijn strikt gelimiteerd tot de noodzakelijke acties. Gevoelige data wordt verwerkt via n8n's encrypted credential manager; er worden geen secrets of tokens opgeslagen in deze repository.

---

## 🌐 Let's Connect
Momenteel beschikbaar voor high-impact samenwerkingen op het gebied van AI-automatisering.

Website: [gijshulsebos.com](https://gijshulsebos.com)
Email: gijs@gijshulsebos.com
