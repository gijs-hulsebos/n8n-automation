# 🛠️ Enterprise-Grade Global Error Governance Engine

![Workflow Canvas](./Image%2025-03-2026%20at%2004.04.jpg)

[![Website](https://img.shields.io/badge/Visit-gijshulsebos.com-blue?style=for-the-badge&logo=googlechrome&logoColor=white)](https://gijshulsebos.com)

---

## 📝 Executive Summary
This **n8n-native error handling system** is engineered by [Gijs Hulsebos](https://gijshulsebos.com) as a centralized governance layer. It serves as a high-reliability watchdog that monitors all production workflows. By intercepting execution failures in real-time, this engine ensures zero silent failures and provides immediate technical diagnostic data to the administrator.

---

## 🔥 Technical Highlights 

* **🛡️ Global Error Interception**: Utilizes the `Error Trigger` node to act as a universal listener, capturing crashes from any connected workflow within the n8n instance.
* **📊 Diagnostic Intelligence**: Automatically extracts critical failure metadata, including the specific **Node Name**, the **Execution ID**, and the raw **Error Message** for rapid debugging.
* **📧 Instant Admin Notification**: Integrated with the **Gmail API (OAuth2)** to deliver formatted incident reports directly to the developer's inbox, ensuring a 99.9% system awareness rate.
* **🎨 Visual Logic Separation**: Implements a high-contrast UI design using custom-colored Sticky Notes to distinguish between **Error Logging** (Crimson) and **Notification Dispatch** (Emerald).

---

## 🛠️ Technical Specifications

| Component | Technical Description | Tools Stack | Business Impact |
| :--- | :--- | :--- | :--- |
| **Error Trigger** | Real-time monitoring of failed workflow executions across the entire environment. | n8n Error Trigger | 0% Silent Failures |
| **Data Extraction** | Dynamic expression mapping to identify the root cause and location of the bug. | n8n Expression Engine | Fast Recovery Time (MTTR) |
| **Gmail Alerting** | Automated dispatch of incident reports with direct links to the failed execution. | Gmail API / OAuth2 | 24/7 System Monitoring |
| **Governance** | Centralized architecture that eliminates the need for individual error nodes in every workflow. | n8n System Logic | Scalable Infrastructure |

---

## 🛠️ Architecture & Stack

* **Orchestration**: n8n (Global Settings Integration)
* **Communication**: Gmail API (Enterprise Scopes)
* **Framework**: Event-Driven Error Handling
* **Governance**: Principal of High Availability

---

## ⚙️ Deployment Note

> [!IMPORTANT]
> **Implementation:** To activate this engine, it must be selected as the "Error Workflow" within the individual **Workflow Settings** of all production-ready automations.

---

## 🌐 Let's Connect
Specialized in building robust, self-healing AI automation ecosystems.

Website: [gijshulsebos.com](https://gijshulsebos.com)
Email: gijs@gijshulsebos.com

---

<p align="center">
  <a href="https://gijshulsebos.com" target="_blank">
    <img src="https://raw.githubusercontent.com/gijs-hulsebos/gijs-hulsebos/main/readme.md.banner.png" alt="Gijs Hulsebos AI Automation Footer" width="100%" />
  </a>
</p>
