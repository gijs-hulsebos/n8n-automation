n8n Workflow: AI Autonomous Calendar Assistant
This n8n workflow deploys a sophisticated AI Agent designed to act as a personal assistant for scheduling and communication. It leverages large language models (LLMs) via OpenRouter to handle natural language requests for booking, updating, and managing Google Calendar events, while maintaining strict business logic and privacy protocols.

🚀 Key Features
Multilingual Support: Automatically detects and mirrors the user's language (Dutch/English).

Intelligent Scheduling: Automatically enforces business hours (Mon-Fri, 09:00 - 17:00) and 60-minute meeting durations.

Privacy-First Logic: Mandatory email verification before accessing or modifying any existing calendar data.

Full CRUD Calendar Operations: Ability to create, read (check availability), and update events autonomously.

Context-Aware Memory: Remembers the last 15 interactions to maintain conversation flow and professional continuity.

Automated Communication: Integrated Gmail tool to send confirmations or follow-ups directly from the agent.

🛠 Workflow Logic ("The How it Works")
The workflow follows a circular, tool-based architecture centered around an AI Agent:

Trigger (Webhook): The process begins when a POST request is sent to the /Gijs-Chat endpoint. It expects a JSON body containing the user's message and a sessionId.

The Brain (AI Agent): The core node is the AI Agent, powered by Gemini 2.5 Flash (via OpenRouter). It processes the system instructions which define Gijs Hulsebos's identity and strict scheduling rules.

Memory (Window Buffer): The agent is connected to a Simple Memory node, ensuring it doesn't "forget" the user's email or the topic of discussion mid-conversation.

Tool Execution: Based on the user's intent, the agent dynamically selects and triggers one of the following tools:

Google Calendar: Get many events (Availability check), Create an event (New booking), or Update an event (Rescheduling).

Gmail: Send a message for outbound email communication.

Response (Respond to Webhook): Once the agent has either performed an action or needs more information, it sends a concise, formatted response back to the initial requester.

📋 Prerequisites
To run this workflow, you will need the following:

n8n Instance: Version 1.0+ recommended.

OpenRouter API Key: To access the google/gemini-2.5-flash model.

Google Cloud Console Project: With Google Calendar API and Gmail API enabled.

OAuth2 Credentials: Configured within n8n for both Google Calendar and Gmail.

⚙️ Setup & Installation
Import: Copy the JSON content and paste it into a new n8n workflow canvas.

Credentials:

Open the OpenRouter Chat Model nodes and select/create your OpenRouter API credentials.

Open the Google Calendar and Gmail nodes and complete the OAuth2 authentication flow for the account gijs@gijshulsebos.com (or your preferred email).

Configuration:

The workflow is currently set to the Europe/Amsterdam timezone. If you are in a different region, update the System Message in the AI Agent node and the workflow settings.

The Business Hours are hardcoded in the Agent's instructions; modify these if your availability differs.

Activation: Save the workflow and flip the toggle to Active.
