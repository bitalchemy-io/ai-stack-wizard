<div align="center">

# 🤖 ai-stack-wizard

**Generate a complete local AI stack in the browser — private, powerful, no cloud required.**

Pick your services · Choose your models · Download a ready-to-use `docker-compose.yml`

[![Live Demo](https://img.shields.io/badge/Live%20Demo-→%20Try%20it%20now-7c6dff?style=for-the-badge)](https://bitalchemy-io.github.io/ai-stack-wizard)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![No Backend](https://img.shields.io/badge/Backend-none%20required-orange?style=for-the-badge)](#)

</div>

---

## 🎯 What is this?

Running a local AI stack means juggling Ollama, Open WebUI, n8n, vector databases, and more — before a single container is running. Finding the right images, configuring ports, wiring services together, and deciding which models fit your hardware takes hours.

**ai-stack-wizard** solves exactly that. Pick the services you need, select your Ollama models, enter your RAM to get tailored recommendations — and download a fully wired `docker-compose.yml` in seconds. No installation, no build system, no backend — a single HTML file.

---

## ✨ Features

| | |
|---|---|
| 🧠 **RAM-aware model picker** | Select your RAM and get instant model recommendations |
| ✅ **12 pre-configured AI services** | Ollama, n8n, Open WebUI, Flowise, LiteLLM and more |
| ✅ **Ollama model auto-pull** | Selected models are pulled automatically on container start |
| ✅ **Pre-wired networking** | All services communicate via a shared `ai-stack` Docker network |
| ✅ **Live YAML preview** | Syntax highlighting directly in the browser |
| ✅ **One-click download** | Finished `docker-compose.yml` ready to deploy |
| ✅ **No backend required** | A single HTML file — open locally or host on GitHub Pages |
| ✅ **Fully configurable** | Ports, paths, passwords, API keys — everything adjustable |

---

## 📦 Included Services

<details>
<summary><b>🦙 Core Inference</b> — Ollama</summary>

| Service | Description |
|---|---|
| **Ollama** | Run large language models locally with a simple REST API. Models are pulled automatically on startup. |

</details>

<details>
<summary><b>💬 Chat Interface</b> — Open WebUI, AnythingLLM</summary>

| Service | Description |
|---|---|
| **Open WebUI** | ChatGPT-like interface for your local Ollama models |
| **AnythingLLM** | All-in-one: chat, RAG pipelines, AI agents & workspaces |

</details>

<details>
<summary><b>⚡ Workflow Automation</b> — n8n</summary>

| Service | Description |
|---|---|
| **n8n** | Automate anything with AI-powered workflows. Pre-wired to talk to Ollama directly. |

</details>

<details>
<summary><b>🧠 AI Agents & RAG</b> — Flowise, Qdrant, SearXNG</summary>

| Service | Description |
|---|---|
| **Flowise** | Build LLM apps, RAG pipelines & AI agents with a visual editor |
| **Qdrant** | High-performance vector database for semantic search & RAG |
| **SearXNG** | Private, self-hosted web search engine for AI agents — no tracking |

</details>

<details>
<summary><b>🔀 AI Gateway</b> — LiteLLM</summary>

| Service | Description |
|---|---|
| **LiteLLM** | Unified OpenAI-compatible API proxy for all your models — local and remote |

</details>

<details>
<summary><b>📊 Observability</b> — Langfuse, Komodo</summary>

| Service | Description |
|---|---|
| **Langfuse** | LLM monitoring, tracing, prompt management & analytics |
| **Komodo** | Modern container & stack management UI (Portainer alternative) |

</details>

<details>
<summary><b>🎙️ Audio & Speech</b> — faster-whisper</summary>

| Service | Description |
|---|---|
| **faster-whisper** | Local speech-to-text transcription API — meetings, voice notes, podcasts |

</details>

<details>
<summary><b>📄 Document AI</b> — Paperless-ngx</summary>

| Service | Description |
|---|---|
| **Paperless-ngx** | Document management with OCR and full-text search — wired to local AI |

</details>

---

## 🧠 Ollama Model Guide

| Model | RAM | Best for |
|---|---|---|
| Llama 3.2 3B | ~8 GB | Fast, lightweight everyday tasks |
| Mistral 7B | ~8 GB | Excellent reasoning, very efficient |
| Llama 3.2 8B | ~16 GB | Best balance of quality and speed |
| Gemma 3 9B | ~16 GB | Coding & structured tasks |
| Qwen 2.5 14B | ~16 GB | Multilingual & code generation |
| DeepSeek R1 8B | ~16 GB | Math & complex reasoning |
| Phi-4 14B | ~16 GB | Microsoft's compact powerhouse |
| Llama 3.1 70B | ~48 GB | Near-GPT-4 quality |
| Nomic Embed | ~4 GB | Text embeddings for RAG pipelines |
| LLaVA 13B | ~16 GB | Vision — describe and analyze images |

---

## 🚀 Getting Started

### Option 1 — Open directly in the browser

```bash
# Clone the repository
git clone https://github.com/bitalchemy-io/ai-stack-wizard
cd ai-stack-wizard

# Open index.html in your browser
open index.html         # macOS
xdg-open index.html     # Linux
```

### Option 2 — Local dev server

```bash
python3 -m http.server 8080
# → http://localhost:8080
```

### Option 3 — GitHub Pages (recommended)

```bash
git init
git add index.html README.md
git commit -m "initial commit"
git remote add origin https://github.com/bitalchemy-io/ai-stack-wizard
git push -u origin main
```

Then in GitHub: **Settings → Pages → Branch: `main` → Save**

The app will be available at `https://bitalchemy-io.github.io/ai-stack-wizard` — free, no server needed.

---

## ▶️ Running your stack

```bash
# Start everything
docker compose up -d

# Check status
docker compose ps

# Follow Ollama logs (model download progress)
docker compose logs -f ollama
```

### Default ports at a glance

| Service | Port | URL |
|---|---|---|
| Ollama API | 11434 | `http://localhost:11434` |
| Open WebUI | 3000 | `http://localhost:3000` |
| n8n | 5678 | `http://localhost:5678` |
| Flowise | 3001 | `http://localhost:3001` |
| LiteLLM | 4000 | `http://localhost:4000` |
| Qdrant | 6333 | `http://localhost:6333` |
| SearXNG | 8888 | `http://localhost:8888` |
| Langfuse | 3002 | `http://localhost:3002` |
| Whisper | 8000 | `http://localhost:8000` |
| Paperless-ngx | 8010 | `http://localhost:8010` |
| AnythingLLM | 3010 | `http://localhost:3010` |
| Komodo | 9120 | `http://localhost:9120` |

---

## 🔧 Adding a Custom Service

Add a new entry to the `SERVICES` object in `index.html`:

```javascript
my_service: {
  name: 'My Service',          // Display name
  icon: '🚀',                  // Emoji icon
  cat: 'AI Agents & RAG',      // Category
  desc: 'Short description',
  tag: 'image:tag',            // Docker image
  fields: [
    {
      key: 'port',
      label: 'Port',
      default: '8080',
      hint: 'Optional hint shown below the input'
    },
  ],
  yaml: (c) => `
  my-service:
    image: my-image:tag
    container_name: my_service
    restart: unless-stopped
    ports:
      - "${c.port}:8080"
    environment:
      - OLLAMA_BASE_URL=http://ollama:11434`.trim(),
  volumes: () => [],
},
```

---

## 🗺️ Roadmap

- [ ] GPU support detection (CUDA / Apple Silicon / ROCm)
- [ ] Generate `.env` file alongside the YAML
- [ ] Recommended stack presets (Minimal / RAG / Full)
- [ ] More services (Open Interpreter, Dify, PrivateGPT, LocalAI …)
- [ ] One-click `litellm_config.yaml` generation

---

## 🤝 Contributing

Pull requests are welcome! Especially looking for: new AI services, model updates, and improvements to existing YAML templates.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-service`
3. Commit your changes: `git commit -m 'feat: add Dify'`
4. Push the branch: `git push origin feature/new-service`
5. Open a Pull Request

---

## 📄 License

MIT — free to use, fork, and extend.

---

<div align="center">

Made with ❤️ for the local AI community

</div>
