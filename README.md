# 🚀 GoogleColab2Local-LLM-Free

A self-hosted LLM API bridge that turns **Google Colab GPU + Google Drive storage** into your personal LLM server.

Run powerful open-source LLM models on Google Colab and access them remotely from your local machine through an API endpoint.

---

## 👨‍💻 Author

**Vikas Vaishnav**

Instagram:
https://www.instagram.com/_cyberwizard_/

LinkedIn:
https://www.linkedin.com/in/vikas-vaishnav-0719262b/

---

# ✨ Features

- ✅ Use Google Colab GPU for LLM inference
- ✅ Persistent model storage using Google Drive
- ✅ Ollama based model management
- ✅ FastAPI powered API gateway
- ✅ Access LLM from your local machine
- ✅ No expensive GPU hardware required
- ✅ One-click startup workflow
- ✅ Supports multiple Ollama models

---

# 🏗️ Architecture

```
                 Local Machine

                      |
                      |
                 API Request

                      |
                      v

              Tunnel Endpoint

                      |
                      |
              Google Colab Runtime

                      |
                      v

              FastAPI Gateway

                      |
                      v

                 Ollama Server

                      |
                      v

              LLM Model Storage

              Google Drive
```

---

# 📦 Requirements

- Google Account
- Google Colab
- Google Drive
- Local machine (Linux / Windows / Mac)
- Basic terminal knowledge

---

# 🚀 Setup

## 1. Open Google Colab

Upload the provided notebook:

```
ColabLLM-Bridge.ipynb
```

---

## 2. Mount Google Drive

The notebook creates:

```
Google Drive

LLM_Server/
│
├── models/
│
├── scripts/
│
├── config/
│
└── server.py
```

---

## 3. Install Ollama

The notebook automatically installs Ollama.

Check:

```bash
ollama --version
```

---

## 4. Download LLM Model

Example:

```bash
ollama pull qwen2.5:7b
```

Supported models:

- qwen2.5
- llama3.1
- mistral
- phi
- gemma

---

# 🌐 API Usage

After starting the server you will receive:

```
API Endpoint:

https://your-endpoint-url
```

---

## Health Check

```bash
curl https://your-endpoint-url/health
```

Response:

```json
{
 "status":"running"
}
```

---

## List Models

```bash
curl https://your-endpoint-url/models
```

Example response:

```json
{
 "models":[
  {
   "name":"qwen2.5:7b"
  }
 ]
}
```

---

## Chat Completion

Example:

```bash
curl https://your-endpoint-url/chat \
-H "Content-Type: application/json" \
-d '{
"prompt":"Explain quantum computing"
}'
```

---

# 🔥 Supported Models

Recommended:

| Model | Size | Use Case |
|---|---|---|
| qwen2.5:7b | ~5GB | Coding + General AI |
| llama3.1:8b | ~5GB | General purpose |
| mistral:7b | ~4GB | Fast responses |

---

# ⚡ Why Google Colab?

Google Colab provides:

- Free GPU access
- Easy experimentation
- No local GPU requirement

This project uses:

```
Google Drive → Persistent Storage

Google Colab → Compute

Ollama → Model Runtime

FastAPI → API Layer
```

---

# ⚠️ Limitations

- Colab runtime is temporary
- GPU availability depends on Colab
- Session disconnects require restart
- Not designed for production hosting

---

# 🛣️ Roadmap

- [ ] OpenAI compatible API
- [ ] Streaming token responses
- [ ] Authentication system
- [ ] Web UI
- [ ] Multiple model switching
- [ ] Automatic startup script
- [ ] Docker support

---

# 🤝 Contributions

Pull requests and improvements are welcome.

If you find this useful, consider giving the repository a ⭐

---

## License

MIT License
