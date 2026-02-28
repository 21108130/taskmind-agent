# 🧠 TaskMind — Agentic AI To-Do List

> A natural language to-do list powered by Claude AI. Talk to your task manager like a human — no buttons, no forms, just conversation.

![TaskMind Screenshot](screenshot.png)

---

## ✨ Features

- 💬 **Natural Language Commands** — Add, complete, and delete tasks by just talking
- 🎯 **Smart Priority Detection** — Detects urgency from words like "urgent", "important", "whenever"
- 📅 **Due Date Parsing** — Understands "tomorrow", "friday", "next week"
- 🔍 **Filter Tasks** — View All / Active / Done / High Priority
- ⚡ **Real-time AI Agent** — Powered by Claude claude-sonnet-4-20250514
- 🎨 **Beautiful Dark UI** — Minimal, sleek, production-grade design

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/taskmind-agent.git
cd taskmind-agent
```

### 2. Open in browser
Just open `index.html` in your browser — no build step needed!

```bash
open index.html
# or
npx serve .
```

### 3. Get an Anthropic API Key
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Create an account and generate an API key
3. Paste it into the app when prompted

---

## 💬 Example Commands

| You say | Agent does |
|---|---|
| `Add buy groceries, high priority` | Adds task with high priority |
| `Remind me to call John tomorrow` | Adds task with due date "Tomorrow" |
| `Submit the report by friday, urgent!` | Adds high priority task due Friday |
| `Mark buy groceries as done` | Completes that task |
| `Delete task 3` | Removes task by ID |
| `Clear all completed tasks` | Removes all done tasks |
| `What do I have due this week?` | Agent replies with a summary |

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| AI Agent | Claude claude-sonnet-4-20250514 via Anthropic API |
| Fonts | Syne + DM Mono (Google Fonts) |
| Hosting | Any static host (GitHub Pages, Netlify, Vercel) |

---

## 📁 Project Structure

```
taskmind-agent/
├── index.html        # entire app (single file)
└── README.md         # this file
```

---

## 🌐 Deploy to GitHub Pages

1. Push to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Visit `https://yourusername.github.io/taskmind-agent`

---

## 🔑 Security Note

Your API key is stored **only in memory** (JavaScript variable) and is never logged, saved to localStorage, or sent anywhere except directly to the Anthropic API over HTTPS. It resets when you close the tab.

For production use, consider building a backend proxy so the API key is never exposed client-side.

---

## 🧩 How It Works (Agentic Loop)

```
User Input → Claude API → JSON Response → Execute Actions → Update UI
                ↑                                               |
                └──────── Updated task list fed back ──────────┘
```

Each message sends the **full current task list** as context so Claude always knows the current state. Claude responds with structured JSON containing a `reply` and a list of `actions` (add/complete/delete/clear_done) that the app executes.

---

## 📄 License

MIT — free to use, modify, and distribute.
