# 🛠️ Technical Setup Guide: AI Calendar Assistant

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

This technical documentation, maintained by **[Gijs Hulsebos](https://gijshulsebos.com)**, provides the specifications required to replicate and deploy the AI Autonomous Calendar Assistant.

---

## 🔐 1. Required Credentials

To ensure the Agentic framework functions correctly, you must configure the following three credential sets in your n8n instance:

| Service | Node Type | Required Scopes / Permissions |
| :--- | :--- | :--- |
| **OpenRouter API** | `lmChatOpenRouter` | Access to `google/gemini-2.5-flash` model. |
| **Google Calendar** | `googleCalendarOAuth2Api` | `https://www.googleapis.com/auth/calendar.events` (Read/Write) |
| **Gmail** | `gmailOAuth2` | `https://www.googleapis.com/auth/gmail.send` |

---

## ⚙️ 2. Environment Variables & Configuration

The following parameters are hardcoded within the **AI Agent's System Message** and **Settings**. Update these to align with your specific environment:

* **Owner Identity**: Currently set to `Gijs Hulsebos`. Update the `systemMessage` in the AI Agent node to reflect your name/role.
* **Target Calendar ID**: The tools are currently mapped to `gijs@gijshulsebos.com`. You **must** update the *Calendar ID* field in all Google Calendar nodes to your own email address.
* **Timezone Settings**:
    * **Workflow Settings**: `Europe/Amsterdam`
    * **AI System Message**: `Europe/Amsterdam`
* **Business Hours**: Mon-Fri, 09:00 - 17:00 (defined in Agent instructions).
* **Current Context**: Calendar Year is explicitly set to `2026`.

---

## 🌐 3. Webhook / Trigger Architecture

The workflow is exposed via a RESTful Webhook Node for easy integration with any frontend.

* **Endpoint Path**: `Gijs-Chat`
* **HTTP Method**: `POST`
* **Payload Format (JSON)**:

```json
{
  "body": {
    "message": "I want to book a meeting for tomorrow at 10am",
    "sessionId": "unique-user-id-123"
  }
}
