# 🎙️ Voice AI Assistant using n8n

## 📌 Overview

The **Voice AI Assistant** is an intelligent automation workflow built using **n8n**, **OpenAI GPT-4.1 Mini**, and **Telegram**. It allows users to interact with an AI assistant using **both voice messages and text messages**.

The workflow automatically detects whether the incoming Telegram message is a voice recording or text. Voice messages are transcribed into text using OpenAI Speech-to-Text, processed by an AI Agent capable of using multiple productivity tools, summarized for better speech output, converted back into natural-sounding audio using OpenAI Text-to-Speech, and finally returned to the user through Telegram.

---

# 🚀 Features

* 🎤 Voice Message Support
* 💬 Text Message Support
* 🤖 OpenAI GPT-4.1 Mini AI Agent
* 🧠 Conversation Memory
* 🎧 Speech-to-Text (Voice Transcription)
* 🔊 Text-to-Speech (AI Voice Response)
* 📧 Gmail Integration
* 📅 Google Calendar Integration
* 📊 Google Sheets Integration
* 📄 Google Docs Integration
* 🌐 Internet Search using SerpAPI
* 📱 Telegram Bot Interface
* 🕒 IST Time Awareness
* 🔄 Automatic Tool Calling

---

# 🛠 Tech Stack

* n8n
* OpenAI GPT-4.1 Mini
* OpenAI Speech-to-Text
* OpenAI Text-to-Speech
* Telegram Bot API
* Gmail API
* Google Calendar API
* Google Sheets API
* Google Docs API
* SerpAPI

---

# 🏗 Workflow Architecture

```text
                User
                  │
      ┌───────────┴───────────┐
      │                       │
      ▼                       ▼
 Voice Message          Text Message
      │                       │
      ▼                       ▼
 Telegram Trigger & Switch Node
              │
      ┌───────┴────────┐
      │                │
      ▼                ▼
Speech-to-Text      Text Input
      │                │
      └───────┬────────┘
              ▼
         AI Agent
              │
     ┌────────┼───────────┐
     │        │           │
     ▼        ▼           ▼
 Gmail   Calendar   Google Tools
     │        │           │
     └────────┼───────────┘
              ▼
        AI Response
              ▼
     Response Summarizer
              ▼
      Text-to-Speech
              ▼
     Telegram Audio Reply
```

---

# 📋 Workflow Components

## 1. Telegram Trigger

Receives incoming Telegram messages and starts the workflow.

---

## 2. Switch Node

Automatically determines whether the incoming message is:

* 🎤 Voice Message
* 💬 Text Message

---

## 3. Voice Processing

For voice messages:

1. Download the audio file from Telegram.
2. Convert speech into text using OpenAI Speech-to-Text.
3. Store the transcription.
4. Send the text to the AI Agent.

---

## 4. Text Processing

For text messages:

* Directly forward the text to the AI Agent.

---

## 5. AI Agent

The AI Agent is the central decision-making component.

Capabilities include:

* Answering user questions
* Sending emails
* Creating calendar events
* Updating Google Sheets
* Editing Google Docs
* Searching the internet
* Using conversation memory
* Automatically selecting the correct tool

---

## 6. Conversation Memory

Maintains the last **3 conversations** to provide contextual and natural interactions.

---

## 7. Gmail Tool

Send professional emails directly through Gmail.

Example:

> Send an email to [john@example.com](mailto:john@example.com) about tomorrow's meeting.

---

## 8. Google Calendar

Create meetings and reminders.

Example:

> Schedule a meeting tomorrow at 3 PM.

---

## 9. Google Sheets

Append data into spreadsheets.

Example:

> Add Rahul to the student sheet.

---

## 10. Google Docs

Insert or update document content.

Example:

> Create today's meeting notes.

---

## 11. SerpAPI

Search the internet for real-time information.

Example:

> Search the latest AI news.

---

## 12. Response Summarizer

The AI summarizes long responses into concise and speech-friendly text to improve audio quality.

---

## 13. Text-to-Speech

Converts the summarized response into natural AI-generated speech using OpenAI Text-to-Speech.

---

## 14. Telegram Audio Output

Returns the generated audio response back to the user via Telegram.

---

# 📂 Workflow Sequence

```text
Telegram User
      │
      ▼
Telegram Trigger
      │
      ▼
Switch Node
      │
 ┌────┴────┐
 │         │
 ▼         ▼
Voice     Text
 │         │
 ▼         ▼
Speech-to-Text
 │
 ▼
AI Agent
 │
 ├── Gmail
 ├── Calendar
 ├── Google Sheets
 ├── Google Docs
 └── SerpAPI
 │
 ▼
Response Summarizer
 │
 ▼
Text-to-Speech
 │
 ▼
Telegram Audio Reply
```

---

# 📦 Prerequisites

Before running the workflow, ensure you have:

* n8n (Local or Cloud)
* Telegram Bot
* OpenAI API Key
* Gmail OAuth Credential
* Google Calendar OAuth Credential
* Google Sheets OAuth Credential
* Google Docs OAuth Credential
* SerpAPI Key

---

# 🔑 Required Credentials

### Telegram

* Bot Token

### OpenAI

* API Key
* GPT-4.1 Mini
* Speech-to-Text
* Text-to-Speech

### Gmail

* OAuth2 Credential

### Google Calendar

* OAuth2 Credential

### Google Sheets

* OAuth2 Credential

### Google Docs

* OAuth2 Credential

### SerpAPI

* API Key

---

# 💬 Example Commands

### Voice

🎤 "Schedule a meeting tomorrow at 10 AM."

🎤 "Search today's AI news."

🎤 "Send an email to my manager."

---

### Text

* Add Rahul to the student sheet.
* Create today's meeting notes.
* Search the latest OpenAI updates.
* Schedule a project review meeting.

---

# 📁 Project Structure

```text
Voice-AI-Agent/
│
├── README.md
├── voice_agent_workflow.json
└── screenshots/
    ├── workflow.png
    ├── telegram_voice.png
    ├── telegram_text.png
    ├── audio_response.png
    └── architecture.png
```

---

# 🔮 Future Enhancements

* WhatsApp Integration
* Slack Integration
* Microsoft Teams Support
* PDF Generation
* Image Generation
* OCR Support
* Multi-language Voice Translation
* RAG Document Search
* CRM Integration
* Database Connectivity
* Long-Term Memory
* Voice Cloning

---

# 📊 Workflow Summary

| Component           | Purpose                                   |
| ------------------- | ----------------------------------------- |
| Telegram Trigger    | Receives incoming voice and text messages |
| Switch              | Detects voice or text input               |
| Speech-to-Text      | Converts voice into text                  |
| AI Agent            | Understands requests and selects tools    |
| Conversation Memory | Maintains recent chat history             |
| Gmail               | Sends emails                              |
| Google Calendar     | Creates events                            |
| Google Sheets       | Updates spreadsheets                      |
| Google Docs         | Creates or edits documents                |
| SerpAPI             | Searches the web                          |
| Response Summarizer | Optimizes responses for speech            |
| Text-to-Speech      | Converts text into AI-generated audio     |
| Telegram Output     | Sends audio response back to the user     |

---

# 👨‍💻 Author

**Ponmathi Radhakrishnan**

Built using **n8n**, **OpenAI GPT-4.1 Mini**, **Telegram**, **OpenAI Speech-to-Text**, **OpenAI Text-to-Speech**, **Google Workspace**, and **SerpAPI**.
