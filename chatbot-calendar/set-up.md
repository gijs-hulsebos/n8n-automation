# 🛠️ Technical Implementation Guide: AI Autonomous Agent (v4.0)

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

This document provides the full technical blueprint for configuring, deploying, and managing the **n8n Autonomous Calendar Agent**. This system is engineered for high-reliability environments and utilizes advanced agentic reasoning.

---

## 🏗️ 1. Architecture Overview
The workflow operates on a **Modular Tool-Calling Framework**. Instead of following a linear path, the AI Agent independently determines which "tool" is required based on the user's intent.

### Core Components:
* **Brain**: Gemini 2.5 Flash (Primary) & GPT-4o Mini (Fallback).
* **Memory**: Window-based buffer (retaining the last 15 interactions).
* **RAG Layer**: Stateless knowledge retrieval from Google Sheets.
* **Action Layer**: Full-access Google Calendar & Gmail integration.

---

## 🔐 2. Required Credentials & Security Scopes
To fully activate all features, the following OAuth2 and API connections must be configured within n8n:

| Service | Connection Type | Required Scopes | Function |
| :--- | :--- | :--- | :--- |
| **OpenRouter** | API Key | `google/gemini-2.5-flash` | Primary reasoning and logic engine. |
| **Google Sheets** | OAuth2 | `spreadsheets.readonly` | Knowledge source for RAG operations. |
| **Google Calendar**| OAuth2 | `calendar.events` (CRUD) | Reading, creating, and modifying events. |
| **Gmail** | OAuth2 | `gmail.send` | Sending automated meeting confirmations. |

---

## ⚙️ 3. System Parameters & Business Rules
The AI Agent operates within strict deterministic boundaries defined in the **System Message** and **Workflow Settings**.

### 🕒 Time Management & Validation
* **Timezone**: Set to `Europe/Amsterdam` (UTC+1/2) across all nodes.
* **Business Hours**: Monday through Friday, 09:00 - 17:00.
* **Session Constraints**: Meetings have a fixed duration of 60 minutes. The final daily slot cannot start later than 16:00.
* **Identity Check**: The agent is programmed to deny access to calendar data until a valid email address is provided by the user.

### 📊 RAG Database Specifications
The agent is linked to a Google Sheet (`ID: 14S6222...`) acting as its "Living Memory."
* **Sections**: Website, Chatbot, Newsletter, LeadGen.
* **Process**: For queries regarding portfolio or methodology, the agent retrieves the specific tab, parses the `Technical_Description`, and presents the associated `Link`.

---

## 🖱️ 4. Metadata Processing (Filter URL Node)
A unique feature of this workflow is the **Post-Processing Layer**. Following the AI generation, a JavaScript node filters the output:
1.  **Link Extraction**: Automatically detects URLs (e.g., GitHub, PageSpeed).
2.  **UI-Mapping**: Transforms these URLs into a structured `buttons` object.
3.  **Content Cleaning**: Strips raw text links to ensure a clean frontend presentation while maintaining full button functionality.

---

## 🌐 5. Webhook Gateway & API Integration
The workflow is accessible via a secured Webhook endpoint.

* **HTTP Method**: `POST`
* **Path**: `Gijs-Chat`
* **Payload Format**:
```json
{
  "body": {
    "message": "Book a meeting for tomorrow at 2:00 PM",
    "sessionId": "user_12345"
  }
}
```
---

<p align="center">
  <a href="https://gijshulsebos.com" target="_blank">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
  </a>
</p>
