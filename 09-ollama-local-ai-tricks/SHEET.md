# 🦙 Module 09: Ollama Local AI Commands & Examples

Quick-reference commands with practical examples for running, pulling, listing, and managing local LLM models with Ollama.

---

## ⚡ 1. Core Ollama CLI Examples

```bash
# Example 1: Run local AI model (Downloads automatically if missing)
ollama run llama3
# Usage: Opens interactive chat prompt with Llama-3 model directly in terminal!

# Example 2: List all downloaded local AI models
ollama list
# Output:
# NAME            ID           SIZE    MODIFIED
# llama3:latest   a6990ed6be50 4.7 GB  2 days ago
# mistral:latest  f0861009139f 4.1 GB  1 week ago

# Example 3: Check currently loaded models running in GPU VRAM
ollama ps
# Output: Shows active running models and allocated VRAM size.

# Example 4: Stop running model to instantly free up GPU VRAM
ollama stop llama3

# Example 5: Delete local model file from disk to save storage
ollama rm llama3
```

---

## 🛠️ 2. Custom Modelfile Example

Create a file named `Modelfile` to build a custom AI persona:

```dockerfile
FROM llama3
PARAMETER temperature 0.7
SYSTEM """You are a professional coding and analytics assistant explaining concepts clearly."""
```

Create custom model from Modelfile:
```bash
# Command:
ollama create my-custom-ai -f ./Modelfile
ollama run my-custom-ai
# Result: Starts chat session with your custom system prompt rules!
```
