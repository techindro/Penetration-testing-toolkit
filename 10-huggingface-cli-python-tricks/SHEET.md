# 🤗 Module 10: Hugging Face CLI & Python Examples

Quick commands with practical examples for downloading models, GGUF files, datasets, and managing cache storage with Hugging Face.

---

## ⚡ 1. Hugging Face CLI Examples

```bash
# Example 1: Install Hugging Face Hub CLI tool
pip install -U "huggingface_hub[cli]"

# Example 2: Login with your user access token
huggingface-cli login

# Example 3: Fast Model Download via CLI to specific local directory
huggingface-cli download meta-llama/Meta-Llama-3-8B-Instruct --local-dir ./llama3
# Usage: Downloads Llama-3 weights into ./llama3 folder.

# Example 4: Download specific GGUF quantized model file for local execution
huggingface-cli download TheBloke/Mistral-7B-Instruct-v0.2-GGUF mistral-7b-instruct-v0.2.Q4_K_M.gguf --local-dir .
# Usage: Downloads single .gguf model file for use with llama.cpp or LM Studio.
```

---

## 🐍 2. Python Snapshot Download Example

```python
from huggingface_hub import snapshot_download

# Example: Download complete model repository programmatically
snapshot_download(
    repo_id="bert-base-uncased",
    local_dir="./bert_model"
)
# Result: Downloads config.json, model.safetensors, and tokenizer files into ./bert_model folder.
```
