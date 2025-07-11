Go to http://localhost:8080 to add a coder model to ollama (e.g. Qwen2.5-Coder)
- Go to admin panel > models > manage models

Go to jupyter UI (get URL with token from log output) jupyter is mapped to port 9999 so ensure URL starts with http://127.0.0.1:9999

Select Marimo launcher icon

Go to Marimo settings top right

Select AI tab and AI completion settings to a remote LLM or the local ollama server:

e.g.
Model: Qwen2.5-Coder
Base URL: http://localhost:7869
API Key: (blank)

For AI Assist config to a remote LLM API e.g. OpenAI / Anthropic. 
