# 🤖 MENTOR.AI — Agentic AI Learning System

> Upload any PDF. An autonomous AI agent plans, adapts, and teaches — diagnosing your mistakes in real-time and building a personalized learning path just for you.

![Version](https://img.shields.io/badge/version-3.0.0-orange)
![Claude](https://img.shields.io/badge/powered%20by-Claude%20Sonnet-purple)
![License](https://img.shields.io/badge/license-MIT-green)

---

## ✨ What Makes It Truly Agentic

Unlike regular AI apps that just call an API once, this system runs a **multi-step autonomous agent loop** powered by Claude's tool use:

| Tool | What the Agent Does |
|------|-------------------|
| `analyze_student_profile` | Profiles your level, weak spots, accuracy before every lesson |
| `extract_key_concepts` | Autonomously maps and categorizes PDF content |
| `generate_lesson` | Crafts personalized lessons adapted to your learning style |
| `generate_adaptive_questions` | Targets your specific weak spots with smart difficulty |
| `diagnose_misconception` | When you're wrong, finds out *why* and remediates it |
| `generate_hint` | 3-level progressive hints without giving away the answer |
| `update_learning_path` | Reorders lessons based on your performance |
| `assess_mastery` | Decides if you're truly ready to advance |

The agent runs up to **10 autonomous iterations** per request — calling tools, reading results, and deciding next steps without any hardcoded logic.

---

## 🚀 Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/mentor-ai.git
cd mentor-ai
```

### 2. Install dependencies
```bash
npm install
```

### 3. Add your Claude API key
Open `server.js` and replace line 17:
```js
apiKey: 'YOUR_CLAUDE_API_KEY_HERE'
```
Get your key at → https://console.anthropic.com

### 4. Start the server
```bash
node server.js
```

### 5. Open the frontend
Open `index.html` in your browser (or serve it with any static server).

---

## 📁 Project Structure

```
mentor-ai/
├── index.html        # Frontend — full UI with agentic features
├── server.js         # Backend — Express + Claude agentic loop
├── package.json      # Dependencies
└── README.md         # This file
```

---

## 🎮 Features

- **Autonomous Agent Loop** — Claude decides which tools to use and when
- **Real-time Misconception Diagnosis** — AI diagnoses *why* you got it wrong
- **Adaptive Difficulty** — Questions adapt based on your weak spots
- **Progressive Hints** — 3 levels of hints that guide without giving away answers
- **Companion Evolution** — 🥚 → 🐣 → 🐉 as you level up
- **Weak Spot Tracking** — Agent tracks every topic you struggle with
- **Clarifying Questions** — AI asks questions to personalize your experience
- **Achievement System** — Unlockable badges as you progress
- **Custom Cursor + Animations** — Polished UI with editorial design

---

## 🛠 Tech Stack

- **Frontend** — Vanilla HTML/CSS/JS (no framework needed)
- **Backend** — Node.js + Express
- **AI** — Anthropic Claude Sonnet (claude-sonnet-4-5) with Tool Use
- **PDF Parsing** — pdf-parse
- **File Upload** — Multer

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Health check |
| POST | `/api/upload-pdf` | Upload PDF, triggers agent loop |
| POST | `/api/get-lesson` | Get current lesson |
| POST | `/api/submit-answer` | Submit answers + get diagnosis |
| POST | `/api/next-lesson` | Advance to next lesson |
| GET | `/api/progress/:userId` | Get full progress |
| POST | `/api/get-hint` | Get progressive hint |
| POST | `/api/clarify` | Get clarifying question |
| POST | `/api/reset-user` | Reset progress |

---

## 📦 Dependencies

```json
{
  "@anthropic-ai/sdk": "^0.24.0",
  "cors": "^2.8.5",
  "express": "^4.18.2",
  "multer": "^1.4.5-lts.1",
  "pdf-parse": "^1.1.1"
}
```

---

## 🔐 Environment Variables (Optional)

Instead of hardcoding the API key, you can use a `.env` file:

```env
ANTHROPIC_API_KEY=your_key_here
PORT=5000
```

Then in `server.js`:
```js
require('dotenv').config();
const anthropic = new Anthropic({ apiKey: process.env.ANTHROPIC_API_KEY });
```

Install dotenv: `npm install dotenv`

---

## 📄 License

MIT — free to use, modify, and distribute.

---

Made with ❤️ using Claude AI
