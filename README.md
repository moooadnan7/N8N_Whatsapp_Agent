# 🤖 WhatsApp AI Personal Assistant

A multi-modal AI-powered WhatsApp assistant built with **n8n**, **Google Gemini**, **OpenAI**, **Gmail API**, and **Google Calendar API**.

The assistant can communicate through **text, voice, and images**, understand user intent, manage emails, schedule calendar events, maintain conversation memory, and respond using either text or voice directly within WhatsApp.

---

## 🚀 Features

### 💬 WhatsApp Integration
- Receive WhatsApp messages in real time.
- Support for:
  - Text messages
  - Voice notes
  - Images

### 🎤 Voice AI
- Convert voice messages into text using OpenAI Speech-to-Text.
- Understand spoken commands naturally.
- Generate realistic voice responses using OpenAI Text-to-Speech.

### 🖼️ Image Understanding
- Analyze images using GPT-4o Vision.
- Extract visual context from images.
- Combine image understanding with user captions for more accurate responses.

### 📧 Email Management
- Send emails.
- Read inbox messages.
- Reply to emails.
- Delete emails.
- Mark emails as read/unread.

### 📅 Calendar Management
- Create calendar events.
- Retrieve upcoming events.
- Update event details.
- Delete events.
- Manage Google Calendar directly from WhatsApp.

### 🧠 Conversational Memory
- Maintains context across conversations.
- Stores up to 50 previous interactions per user.
- Provides personalized responses based on conversation history.

### 🔊 Smart Response System
- Returns text responses for text/image messages.
- Returns voice responses for voice messages.
- Provides a seamless conversational experience.

---

# 🏗️ Architecture

```text
User (WhatsApp)
        │
        ▼
 WhatsApp Trigger
        │
        ▼
      Switch
 ┌──────┼──────┐
 │      │      │
 ▼      ▼      ▼
Text  Audio  Image
 │      │      │
 ▼      ▼      ▼
Process Process Process
 │      │      │
 └──────┴──────┘
        │
        ▼
 Orchestrator Agent
        │
 ┌──────┼────────┐
 ▼      ▼        ▼
Email Calendar Think
Agent  Agent   Tool
        │
        ▼
 AI Response
        │
 ┌──────┴──────┐
 ▼             ▼
Text        Audio
Output      Output
```

---

# ⚙️ Workflow Breakdown

## 1. WhatsApp Trigger

Receives incoming WhatsApp messages and triggers the workflow.

Supported inputs:
- Text
- Audio
- Images

---

## 2. Switch Node

Determines the incoming message type and routes it accordingly.

### Text Path

```text
WhatsApp Trigger
      ↓
     Text
      ↓
Orchestrator Agent
```

### Audio Path

```text
WhatsApp Trigger
      ↓
 Download URL
      ↓
 Download Audio
      ↓
 Speech-to-Text
      ↓
    Voice
      ↓
Orchestrator Agent
```

### Image Path

```text
WhatsApp Trigger
      ↓
Download Image URL
      ↓
 Download Image
      ↓
 Analyze Image
      ↓
  Image + Text
      ↓
Orchestrator Agent
```

---

# 🤖 AI Orchestrator Agent

The central brain of the system.

Responsibilities:

- Understand user intent.
- Decide which specialized agent should handle the request.
- Route tasks automatically.
- Generate final responses.

Supported task categories:

- Email Management
- Calendar Management
- Information Retrieval
- General Conversation
- Image Understanding

---

# 📧 Email Agent

Handles Gmail-related operations.

### Supported Actions

- Send emails
- Read inbox
- Reply to emails
- Delete emails
- Mark emails as read
- Mark emails as unread

### Example

User:

```text
Send an email to Sarah about tomorrow's meeting.
```

Agent:

```text
Email sent successfully to Sarah.
```

---

# 📅 Calendar Agent

Handles Google Calendar operations.

### Supported Actions

- Create events
- Update events
- Retrieve events
- Delete events

### Example

User:

```text
Schedule a meeting tomorrow at 2 PM.
```

Agent:

```text
Meeting scheduled successfully for tomorrow at 2 PM.
```

---

# 🧠 Memory System

The workflow includes a memory buffer that stores user conversations.

### Benefits

- Context-aware responses
- Personalized interactions
- Multi-turn conversations
- Better understanding of ongoing tasks

Configuration:

```text
Memory Window: 50 Messages
Session ID: WhatsApp User Number
```

---

# 🎤 Voice Processing

### Incoming Voice

```text
Voice Message
      ↓
OpenAI Speech-to-Text
      ↓
Text
      ↓
AI Processing
```

### Outgoing Voice

```text
AI Response
      ↓
OpenAI Text-to-Speech
      ↓
WhatsApp Audio Message
```

Voice Model:

```text
Shimmer
```

Output Format:

```text
OPUS
```

---

# 🖼️ Image Processing

The assistant uses GPT-4o Vision to analyze uploaded images.

Workflow:

```text
Image
   ↓
Download
   ↓
GPT-4o Vision
   ↓
Image Description
   ↓
AI Processing
```

Example:

User uploads an image and asks:

```text
What's happening here?
```

The assistant analyzes the image and provides contextual answers.

---

# 🛠️ Technology Stack

| Component | Technology |
|------------|------------|
| Workflow Automation | n8n |
| Messaging Platform | WhatsApp Cloud API |
| Primary AI Model | Google Gemini |
| Speech-to-Text | OpenAI Whisper |
| Vision Analysis | GPT-4o Vision |
| Text-to-Speech | OpenAI TTS |
| Email Integration | Gmail API |
| Calendar Integration | Google Calendar API |
| Memory Management | LangChain Memory Buffer |

---

# 📂 Workflow Components

### Input Layer

- WhatsApp Trigger
- Switch Router
- Text Processing
- Audio Processing
- Image Processing

### AI Layer

- Orchestrator Agent
- Google Gemini
- Think Tool
- Memory Buffer

### Productivity Layer

- Gmail Agent
- Google Calendar Agent

### Output Layer

- Text Response
- Voice Response

---

# 🌟 Highlights

✅ Multi-Agent Architecture

✅ Multi-Modal AI (Text, Voice, Image)

✅ WhatsApp Automation

✅ Gmail Integration

✅ Google Calendar Integration

✅ Voice Assistant Capability

✅ Contextual Memory

✅ Real-Time AI Responses

✅ Gemini + OpenAI Hybrid Architecture

---

# 📈 Future Enhancements

- Web Search Agent
- Social Media Agent
- CRM Integration
- RAG Knowledge Base
- Meeting Booking Automation
- Multi-language Support
- Task Management Integration
- Document Understanding

---

# 👨‍💻 Author

**Mohamed Adnan**

AI Engineer | Data Scientist | Automation Developer

- AI Agents
- Generative AI
- Workflow Automation
- Computer Vision
- NLP
- LLM Applications

---
⭐ If you found this project useful, consider giving it a star.
