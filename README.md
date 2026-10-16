# 🤖 Discord AI Support & Ticket Bot (Powered by Gemini)

An intelligent, AI-powered Discord ticketing bot designed to streamline community support. Built with **discord.py** and powered by **Google Gemini AI**, this bot automates first-line support by creating dedicated private channels, diagnosing user issues against a custom knowledge base, and smoothly escalating unresolved queries to human staff members.

---

## ✨ Features

- **🎟️ Interactive Ticket System**: Simple embed-based buttons or commands to open private support tickets.
- **🔐 Automated Channel Management**: Creates a dedicated private channel for each ticket, inviting only the user and configured support/admin roles.
- **🧠 Gemini AI Support Agent**: Reads messages in ticket channels, understands context, and leverages a dynamic Knowledge Base to answer user questions instantly.
- **🚨 Human Escalation**: Automatically tags support staff and hands off control if the AI cannot solve the issue or if the user requests human assistance.
- **📚 Knowledge Base Integration**: Easily updated markdown or vector storage for product documentation, FAQs, and common troubleshooting steps.
- **🔒 Privacy & Security**: Role-based access controls and private temporary channels.

---

## 📸 Demo & Workflow

### 1. Opening a Support Ticket
Users click a reaction or button in a designated support channel to initiate a ticket.

![Ticket Creation Mockup]([https://via.placeholder.com/800x400.png?text=Ticket+Creation+Button+%26+Private+Channel+Creation](https://github.com/davidpalmer-git/discord_gemini_helpbot/blob/main/Gemini_Generated_Image_8gi39l8gi39l8gi3%20(1).jpg))

---

### 2. AI Agent Chat & Resolution
The Gemini AI agent introduces itself, asks clarifying questions, and pulls solutions directly from your project's knowledge base.

![AI Support Chat Demo]([https://via.placeholder.com/800x450.gif?text=Animated+GIF:+Gemini+AI+Chatting+and+Resolving+Issue](https://github.com/davidpalmer-git/discord_gemini_helpbot/blob/main/Gemini_Generated_Image_8gi39l8gi39l8gi3.jpg))

---

### 3. Automatic Escalation
If the AI detects that an issue requires human intervention (or if confidence is low), it alerts the support team.

![Human Escalation Mockup]([https://via.placeholder.com/800x350.png?text=Escalation+Alert:+Tagging+@Support+Team](https://github.com/davidpalmer-git/discord_gemini_helpbot/blob/main/Gemini_Generated_Image_8gi39l8gi39l8gi3%20(2).jpg))

---

## 🛠️ Tech Stack

- **Language**: Python 3.10+
- **Discord API Wrapper**: [`discord.py`](https://github.com/Rapptz/discord.py)
- **AI Model**: [`google-generativeai`](https://pypi.org/project/google-generativeai/) (Google Gemini API)
- **Configuration & Environment**: `python-dotenv`

---

## 🚀 Quick Start Guide

### Prerequisites

1. **Python 3.10+** installed on your machine or server.
2. A **Discord Bot Token** from the [Discord Developer Portal](https://discord.com/developers/applications).
   - Ensure **Message Content Intent** and **Server Members Intent** are enabled under the **Bot** tab.
3. A **Google Gemini API Key** from [Google AI Studio](https://aistudio.google.com/).

---

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/discord-ai-ticket-bot.git
   cd discord-ai-ticket-bot
   ```

2. **Create and activate a virtual environment**:
   ```bash
   # On macOS/Linux
   python3 -m venv venv
   source venv/bin/activate

   # On Windows
   python -m venv venv
   venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables**:
   Create a `.env` file in the root directory:
   ```env
   DISCORD_BOT_TOKEN=your_discord_bot_token_here
   GEMINI_API_KEY=your_gemini_api_key_here
   GUILD_ID=your_discord_server_id
   SUPPORT_ROLE_ID=your_support_team_role_id
   TICKET_CATEGORY_ID=your_discord_category_id_for_tickets
   ```

5. **Set up the Knowledge Base**:
   Add your FAQs, policies, and troubleshooting docs to `knowledge_base.txt` or `knowledge_base.json` in the root directory.

6. **Run the Bot**:
   ```bash
   python main.py
   ```

---

## 📁 Repository Structure

```text
├── cogs/
│   ├── ticket_system.py  # Ticket creation, permissions, and channel lifecycle
│   └── ai_agent.py      # Gemini API integration and conversation management
├── knowledge_base/
│   └── docs.md           # FAQ & product knowledge fed into Gemini context
├── .env.example          # Sample environment variables configuration
├── config.py             # Configuration loader and constants
├── main.py               # Bot initialization and startup entrypoint
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

---

## ⚙️ How the AI Agent Works

1. **Prompt Context**: When a channel is created, the bot loads system instructions and the contents of `knowledge_base/docs.md`.
2. **Conversation History**: The bot maintains an in-memory chat session per ticket channel using Gemini's chat mode.
3. **Escalation Triggers**:
   - Explicit keyword triggers (e.g., "speak to human", "agent").
   - Low confidence detection or consecutive failure flags parsed from the model's output.

---

## 🤝 Contributing

Contributions are welcome! If you'd like to report a bug or request a feature:
1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
