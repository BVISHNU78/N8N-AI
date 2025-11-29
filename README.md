# Chat-Agentic-AI – n8n AI Chatbot using Google Gemini + Google Sheets
<img width="311" height="162" alt="download" src="https://github.com/user-attachments/assets/4cc6b237-bf3a-4197-ae35-264d18e2f278" />


This project is an **n8n automation workflow** that creates an AI-powered chat assistant using the **Google Gemini API**. It understands user messages, validates dates, extracts order details, and stores them automatically in **Google Sheets**.

---

## 🚀 Features

### 🤖 AI Chatbot (Google Gemini)
- Uses **Google Gemini Chat Model**
- Understands natural language messages
- Extracts order details (item, quantity, date)
- Validates incorrect/ambiguous dates (“today evening”)

### 🧠 Simple Memory
- Maintains short-term conversation context
- Enables multi-turn conversation flow

### 📨 Chat Trigger
- Workflow starts with **When Chat Message Received**
- Works inside n8n’s built-in Chat UI

### 📊 Google Sheets Integration
- Reads from a Google Sheet using **Get Rows**
- Appends new orders using **Append Rows**
- Saves fields like:
  - Item  
  - Quantity  
  - Date  
  - Status (“Pending”)  
  - User message  
  - Timestamp  

### 💬 Built-in Chat UI
- Use the **Open Chat** button to test the bot
- Includes real-time logs and responses

---

## 🏗️ Workflow Overview


<img width="1920" height="1020" alt="Chat-Agentic-AI" src="https://github.com/user-attachments/assets/796e13b6-025f-47e8-a792-18971c5c1faf" />
When Chat Message Received
↓
AI Agent (Google Gemini)
/ |
Model Memory Tools
| |
Gemini Simple Google Sheets (Read/Write)
Memory


---

## 📂 Repository Structure (Suggested)



Chat-Agentic-AI/
│── workflows/
│ └── chat-agentic-ai.json
│── sheets/
│ └── example-sheet-template.xlsx (optional)
│── README.md


---

## 🛠️ Setup Instructions

### 1. Import Workflow
1. Go to **n8n → Workflows → Import**
2. Upload `chat-agentic-ai.json`
3. Save the workflow

### 2. Configure Google Gemini API
1. Go to **Credentials**
2. Add **Google Gemini / AI Studio**
3. Paste your **API Key**

### 3. Configure Google Sheets
1. Add a **Google Sheets** credential (OAuth2 or Service Account)
2. Link it to your order sheet
3. The sheet should contain:

| Date | Quantity | Item | Status | Message | Timestamp |
|------|----------|------|---------|---------|-----------|

### 4. Test the Chat
Use the built-in Chat Panel:

Example:


I need 4 chapathis on 29/11/2025


The bot will:
- Validate the date  
- Extract order details  
- Append the order to Google Sheets  
- Respond with confirmation  

---

## 📦 Requirements

- n8n Cloud or Self-Hosted  (iam used free tier n8n-cloud)
- Google Gemini API key  
- Google Sheets API access  
- A Google Sheet to store orders  

---

<img width="1920" height="1020" alt="Chat-Agentic -AI-1" src="https://github.com/user-attachments/assets/60f3cbf6-a0f8-4dfa-b7e2-0c90ad9dc107" />
