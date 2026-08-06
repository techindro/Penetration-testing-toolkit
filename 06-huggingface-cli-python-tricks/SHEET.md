# 🤗 Module 06: Hugging Face CLI & Python Shortcuts

Quick commands for downloading models, GGUF files, datasets, and managing cache storage with Hugging Face.

---

## ⚡ 1. Hugging Face CLI Commands

```bash
# Install Hugging Face Hub CLI
pip install -U "huggingface_hub[cli]"

# Login with user token
huggingface-cli login

# Fast Model Download via CLI
huggingface-cli download meta-llama/Meta-Llama-3-8B-Instruct --local-dir ./llama3

# Download specific GGUF model file
huggingface-cli download TheBloke/Mistral-7B-Instruct-v0.2-GGUF mistral-7b-instruct-v0.2.Q4_K_M.gguf --local-dir .
```

---

## 🐍 2. Python Snapshot & Pipeline Download

```python
from huggingface_hub import snapshot_download

# Download entire repo locally
snapshot_download(repo_id="bert-base-uncased", local_dir="./bert_model")
```
