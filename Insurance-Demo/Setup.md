<p align="center">
  <img src="https://raw.githubusercontent.com/gijs-hulsebos/n8n-automation/main/n8n-automations%20banner%20(1).png" alt="n8n AI Automation Gijs Hulsebos" width="100%" />
</p>

<p align="center">
  <a href="https://gijshulsebos.com">
    <img src="https://img.shields.io/badge/gijshulsebos.com-121212?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website">
  </a>
  &nbsp;
  <a href="https://www.linkedin.com/in/gijs-hulsebos">
    <img src="https://img.shields.io/badge/LinkedIn-121212?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
</p>

---
*TEXT UPDATE*

### 🛠️ Step-by-Step Setup Guide

**Step 1: API & Credential Configuration**
- **Google OAuth2:** Create a project in Google Cloud Console. Enable the **Gmail API** and **Google Sheets API**. Connect your account in n8n.
- **AI Models:** - Obtain an API key for **Google AI Studio** (for the Gemini 2.5 Flash fallback).
  - Obtain an API key for **OpenAI** (for the GPT-5-mini standard model).
- **Header Auth:** In the "Insurance Demo" Webhook node, set up a Header Auth credential to protect your endpoint.

**Step 2: Database Setup (Google Sheets)**
- Open Google Sheets and create a new file (or clone the existing one using ID: `1bxIjX3...TWDVg`).
- Rename the first tab to **"Overview"** and the second tab to **"Error Log"**.
- Ensure the "Overview" tab has columns for: `timestamp`, `policy_number`, `claim_id`, `user_email`, and `approval`.

**Step 3: n8n Node Localization**
- **Spreadsheet ID:** Paste your Sheet ID into the following nodes: `Create Row with New Submission`, `Add PII`, `Log Error`, and `Approval Update`.
- **Adjuster Routing:** Open the `Manual Review` node and change the `sendTo` email from `gijs@gijshulsebos.com` to your team's adjuster email.
- **Thresholds:** (Optional) Adjust the `Human Review?` node if you want to change the auto-escalation score (currently set to < 40).

**Step 4: Testing the Pipeline**
- Set the workflow to **Active**.
- Copy your **Production Webhook URL** from the "Insurance Demo" node.
- Send a test `POST` request with this JSON structure:
  ```json
  {
    "policyNumber": "POL-12345",
    "email": "test@example.com",
    "incidentType": "Collision",
    "incidentDescription": "Front bumper damage after hitting a pole.",
    "image": "URL_OR_BASE64_STRING"
  }

  ---

<p align="center">
  <a href="https://gijshulsebos.com" target="_blank">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
  </a>
</p>