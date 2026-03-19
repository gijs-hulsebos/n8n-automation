🛠️ Setup Guide: AI Autonomous Calendar Assistant
This guide provides the technical specifications required to replicate and deploy the Chatbot + Calendar workflow.

🔐 1. Required Credentials
Based on the workflow nodes, you must configure the following three credential sets:

Node Type	Service	Required Scopes / Permissions
OpenRouter API	lmChatOpenRouter	Access to google/gemini-2.5-flash model.
Google Calendar	googleCalendarOAuth2Api	https://www.googleapis.com/auth/calendar.events (Read/Write)
Gmail	gmailOAuth2	https://www.googleapis.com/auth/gmail.send
⚙️ 2. Environment Variables & Configuration
The following hardcoded values are present in the AI Agent's System Message and Settings. You should update these to match your own environment:

Owner Identity: Currently set to "Gijs Hulsebos". Update the systemMessage in the AI Agent node to reflect your name/role.

Target Email: The tools are hardcoded to gijs@gijshulsebos.com. You must update the Calendar ID in all Google Calendar nodes to your email.

Timezone:

Workflow Settings: Europe/Amsterdam

AI System Message: Europe/Amsterdam

Business Hours: Mon-Fri, 09:00 - 17:00 (defined in the Agent instructions).

Calendar Year: Explicitly set to 2026.

🌐 3. Webhook / Trigger Setup
The workflow is triggered via a Webhook Node.

Endpoint Path: Gijs-Chat

HTTP Method: POST

Expected Input (JSON):

JSON
{
  "body": {
    "message": "I want to book a meeting for tomorrow at 10am",
    "sessionId": "unique-user-id-123"
  }
}
Response: The workflow uses a Respond to Webhook node, returning a JSON object: { "output": "AI_RESPONSE_TEXT" }.

🤖 4. Node-Specific Notes
AI Model Configuration
Model ID: google/gemini-2.5-flash via OpenRouter.

Temperature: Default (Managed by OpenRouter node).

Memory: Uses a Window Buffer Memory set to a contextWindowLength of 15. This ensures the agent remembers the user's email and context during the booking flow.

Logic Constraints (Prompt Engineering)
End Time Logic: The agent is strictly instructed to ensure the End time is exactly 60 minutes after the Start time.

Privacy Gate: The agent will refuse to call the Get many events tool until a user provides an email address.

🚀 5. Step-by-Step Installation
Import: Create a new workflow in n8n and paste the provided JSON.

Auth:

Click on the OpenRouter Chat Model and add your API Key.

Click on the Google Calendar nodes and connect your Google account via OAuth2.

Click on the Gmail node and connect your Google account.

Update Calendar ID:

Open the Create, Update, and Get Many nodes.

Change the "Calendar" field from gijs@gijshulsebos.com to your own email address.

Test:

Click "Execute Workflow".

Send a test POST request using a tool like Postman or cURL to your n8n Webhook URL.

Deploy: Change the workflow toggle from Inactive to Active.

