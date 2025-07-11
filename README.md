### Docker Compose

Run docker compose up -d to spin up jupyter+marimo and ollama services

### Ollama Service
Go to http://localhost:8080 to add a coder model to ollama (e.g. Qwen2.5-Coder)
- Go to admin panel > models > manage models


### Jupyter

Go to jupyter UI (port mapped to 9999 by default in docker compose) http://127.0.0.1:9999. Get token from container logs.

- Select Marimo launcher icon

### Marimo

- Go to Marimo settings (top right)

Select AI tab and add AI credentials for AI completion settings to LLM service or the local ollama server:

e.g.
Model: Qwen2.5-Coder
Base URL: http://localhost:7869
API Key: (blank)

For AI Assist config to a remote LLM API e.g. OpenAI / Anthropic. 
