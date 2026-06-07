# Autonomous AI Restaurant Agent & Inventory Management System

A production-ready, event-driven automation pipeline that connects a public messaging infrastructure directly to an autonomous business database. This system leverages an advanced LLM agent to interact with customers, check live inventory availability, handle restaurant FAQs, and dynamically log orders onto a live ledger.

---

## 🛠️ Tech Stack & Architecture

* **Orchestration Engine:** n8n (Advanced Workflow Automation)
* **Cognitive Engine:** Google Gemini API (Function Calling & Agentic Logic)
* **Database & Storage:** Google Sheets API (Live Inventory & Transaction Ledger)
* **Messaging Gateway:** Meta WhatsApp Business API (Webhook Interface)

---

## 🏗️ System Architecture Flow

1. **User Request:** Customer texts the WhatsApp Business line.
2. **Webhook Ingestion:** Meta streams the messaging payload instantly via production webhooks to an active n8n trigger gateway.
3. **Contextual Evaluation:** The **AI Agent node** captures the text string, parses the sender's unique ID via a structured memory buffer window to maintain session history, and handles multi-turn conversation.
4. **Tool Execution (Function Calling):**
    * *FAQ Query:* Searches the knowledgebase sheet for store policies and restaurant hours.
    * *Inventory Verification:* Performs a live check of available stock from the database before confirming orders.
    * *Fulfillment Ledger:* Automatically appends customer details, item quantities, random unique Order IDs, and European/Berlin timestamps onto the order sheet.
5. **Payload Return:** The agent formats a clean response and routes it back to the user's mobile device.

---

## 🚀 How to Deploy This Workflow

1. Download the `workflow.json` file from this repository.
2. Open your n8n canvas, click on the top-right menu icon, and select **Import from File**.
3. Link your local account credentials for the Google Gemini Model, Google Sheets, and WhatsApp nodes.
4. Open the Google Sheet nodes and paste your own spreadsheet ID into the **Document ID** fields.
5. Switch the workflow toggle to **Publish**.
