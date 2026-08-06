# 🦙 Module 09: Ollama Local AI & Model Management Commands

Quick-reference commands for running, pulling, listing, and managing local LLM models with Ollama.

---

## ⚡ 1. Core Ollama CLI Commands

```bash
# Run local model (Downloads automatically if missing)
ollama run llama3

# List all downloaded local AI models
ollama list

# Check currently loaded models running in VRAM
ollama ps

# Stop running model and free GPU VRAM
ollama stop llama3

# Delete local model from disk
ollama rm llama3
```

---

## 🛠️ 2. Custom Modelfile Setup

Create a `Modelfile` to customize model system prompts and temperature:

```dockerfile
FROM llama3
PARAMETER temperature 0.7
SYSTEM """You are a professional coding and analytics assistant explaining concepts clearly."""
```

Create custom model from Modelfile:
```bash
ollama create my-custom-ai -f ./Modelfile
ollama run my-custom-ai
```
