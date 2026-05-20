# PromptPilot

PromptPilot is a context-aware AI prompt enhancer Chrome extension that improves user prompts using the current prompt + recent chat context.

It works with:

- ChatGPT
- Claude
- Gemini
- Perplexity

The extension reads the current prompt and recent visible messages, sends them to a FastAPI backend, analyzes the context, and returns a sharper, goal-focused optimized prompt.

---

# Features

- Context-aware prompt optimization
- Prompt scoring system
- Detects vague prompts
- One-click prompt replacement
- Copy optimized prompt
- Multi-platform support
- Privacy-focused design
- Optional OpenAI-powered optimization
- Local backend support

---

# Tech Stack

## Frontend

- Chrome Extension Manifest V3
- JavaScript
- HTML/CSS

## Backend

- Python
- FastAPI
- Pydantic

## Optional AI

- OpenAI API
- Ollama

---

# Project Structure

```txt
promptpilot/
├── backend/
│   ├── requirements.txt
│   ├── Dockerfile
│   └── app/
│       ├── main.py
│       ├── schemas.py
│       ├── config.py
│       ├── context_extractor.py
│       ├── prompt_analyzer.py
│       ├── prompt_optimizer.py
│       ├── llm_optimizer.py
│       └── privacy.py
│
└── extension/
    ├── manifest.json
    ├── content.js
    ├── styles.css
    ├── popup.html
    ├── popup.js
    └── platforms/
        ├── chatgpt.js
        ├── claude.js
        ├── gemini.js
        └── perplexity.js
```

---

# Folder Overview

## backend/

Handles:

- prompt analysis
- context extraction
- optimization
- scoring
- AI integration

### Important Files

| File | Purpose |
|------|----------|
| main.py | FastAPI entry point |
| schemas.py | API request/response models |
| context_extractor.py | Extracts recent chat context |
| prompt_analyzer.py | Detects weak/vague prompts |
| prompt_optimizer.py | Rule-based optimization |
| llm_optimizer.py | OpenAI-powered optimization |
| privacy.py | Removes sensitive data |

---

## extension/

Chrome extension frontend.

### Important Files

| File | Purpose |
|------|----------|
| manifest.json | Extension configuration |
| content.js | Main extension logic |
| styles.css | Floating widget UI |
| popup.html | Popup UI |
| popup.js | Extension settings |
| platforms/ | Platform-specific DOM handlers |

---

# System Flow

```txt
User Types Prompt
        │
        ▼
Chrome Extension Reads:
- Current Prompt
- Recent Messages
        │
        ▼
FastAPI Backend
        │
        ▼
Context Extraction
        │
        ▼
Prompt Analysis
        │
        ▼
Prompt Optimization
        │
        ▼
Return:
- Optimized Prompt
- Score
- Issues
        │
        ▼
Extension Floating Panel
        │
        ▼
Replace Prompt / Copy
```

---

# Local Setup

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/promptpilot.git

cd promptpilot
```

---

## 2. Backend Setup

```bash
cd backend

python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Mac/Linux

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run backend:

```bash
uvicorn app.main:app --reload --port 8000
```

Backend runs at:

```txt
http://localhost:8000
```

---

## 3. Load Extension

Open:

```txt
chrome://extensions
```

Enable:

```txt
Developer Mode
```

Click:

```txt
Load unpacked
```

Select:

```txt
promptpilot/extension
```

---

# Testing

## Test Backend

Open:

```txt
http://localhost:8000/health
```

Expected:

```json
{
  "status": "ok"
}
```

---

## Test Extension

1. Open ChatGPT
2. Type a prompt:

```txt
how to deploy this
```

3. Click:

```txt
Improve Prompt
```

Expected:

- optimized prompt appears
- score appears
- Replace Prompt works
- Copy works

---

# Deployment

## Local Version

```txt
Chrome Extension
        │
        ▼
Local FastAPI Backend
```

No server cost.

---

# Chrome Web Store

Steps:

1. Build extension
2. Add privacy policy
3. Add screenshots
4. Zip extension folder
5. Upload to Chrome Web Store
6. Submit for review

---

# Future Improvements

- LangGraph agents
- Prompt history
- Hallucination detection

---

# Vision

PromptPilot aims to become:

```txt
“Grammarly for AI prompts”
```

A tool that automatically transforms weak prompts into high-quality context-aware prompts.