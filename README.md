# 🤖 AI-Powered Telegram Bot (n8n Workflow)

[![n8n](https://img.shields.io/badge/n8n-Cloud-FF6C37?style=flat&logo=n8n&logoColor=white)](https://n8n.io/)
[![Groq](https://img.shields.io/badge/Groq-LLaMA%203.3%2070B-orange?style=flat)](https://groq.com/)
[![Telegram](https://img.shields.io/badge/Telegram-Bot%20API-26A69A?style=flat&logo=telegram&logoColor=white)](https://core.telegram.org/bots/api)
[![AI Architecture](https://img.shields.io/badge/AI-LangChain%20%2F%20Agent-blue?style=flat)](https://n8n.io/)

A production-ready **n8n automation workflow** that deploys an intelligent, context-aware chatbot on Telegram. Powered by Groq's lightning-fast inference engine and utilizing conversational memory, this bot can handle complex multi-turn interactions autonomously, making it perfect for automated customer support.

---

## ⚙️ What It Does

Unlike traditional rule-based chatbots, this workflow utilizes an advanced AI Agent infrastructure. When a user sends a message on Telegram, the workflow intercepts the text, retrieves the context of past messages from its internal memory, processes the query via the LLaMA 3.3 70B model, and replies dynamically.

### ✨ Key Features
*   🧠 **Stateful Memory:** Remembers preceding context within the chat, preventing repetitive or robotic responses.
*   ⚡ **Ultra-Fast Inference:** Utilizes Groq API for near-instantaneous language model execution.
*   🕒 **24/7 Availability:** Functions completely unattended in the cloud to manage user interactions around the clock.

### 💼 Key Use Cases
*   **Automated Customer Support:** Resolve client queries, FAQs, and service assistance instantly on Telegram.
*   **Interactive Virtual Assistant:** Deploy a personal or group assistant capable of summarizing data, brainstorming, or answering general knowledge questions.
*   **Lead Engagement:** Keep prospects warm by answering pre-sales questions before routing them to a human agent.

---

## 🛠️ Built With

*   **n8n Cloud:** The core automation platform running the orchestrator agent.
*   **Telegram Bot API:** Secure webhook-based communication channel for text ingestion.
*   **Groq API (LLaMA 3.3 70B):** High-performance Large Language Model (LLM) driving the cognitive engine.

### Nodes Architecture
1.  **Telegram Trigger Node:** Listens to incoming chat strings or group interactions in real time.
2.  **AI Agent Node:** Actively coordinates the memory, prompt templates, and the language model.
3.  **Groq Chat Model Node:** Connects to Groq cloud using the advanced `llama-3.3-70b` model.
4.  **Simple Memory Node:** Temporarily retains session logs to ensure seamless context continuity.
5.  **Telegram Node:** Dispatches the final AI-generated response back to the respective chat ID.

---

## 🚀 How to Setup & Import

Follow these steps to deploy this AI chatbot inside your own n8n instance:

### 1. Create a Telegram Bot
*   Open Telegram, search for `@BotFather`, and create a new bot using `/newbot`.
*   Copy the generated **API Token**.

### 2. Import the Workflow
*   Copy the raw JSON content from the `workflow.json` file in this repository.
*   Open your **n8n canvas** and press `Ctrl + V` (Windows) or `Cmd + V` (Mac) to import the nodes.

### 3. Connect API Keys & Credentials
*   **Telegram Nodes:** Open both the *Telegram Trigger* and *Telegram* nodes, add a new credential, and paste your Bot API Token.
*   **Groq Node:** Get an API key from the [Groq Console](https://console.groq.com/). Open the *Groq Chat Model* node and link your Groq API Key.

### 4. Activate the Bot
*   Ensure the model parameter inside the Groq node is set to `llama-3.3-70b` (or your preferred variant).
*   Toggle the workflow status to **Active** (Top Right Corner).
*   Go to Telegram and send a message to your bot to start testing!

---

## 🔒 Security Note
> **Note:** The `workflow.json` file uploaded here does **not** contain any personal API keys, secret bot tokens, or private chat logs. n8n automatically strips credentials during export, ensuring a safe open-source distribution on GitHub.
