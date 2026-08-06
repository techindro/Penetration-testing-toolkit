# 🤖 Module 15: AI/ML & Data Science Setup & Troubleshooting Guide

Complete troubleshooting guide for CUDA installation, PyTorch/TensorFlow GPU acceleration, Python virtual environments, Jupyter kernels, and Data Science library bugs.

---

## ⚡ 1. PyTorch / TensorFlow CUDA GPU Verification

### Symptom:
`torch.cuda.is_available()` returns `False` despite having an NVIDIA GPU.

### Fix & Verification:
```python
# Save as check_gpu.py and run
import torch
print("PyTorch Version:", torch.__version__)
print("CUDA Available:", torch.cuda.is_available())
if torch.cuda.is_available():
    print("Device Name:", torch.cuda.get_device_name(0))
    print("CUDA Version:", torch.version.cuda)
```

### Installation Fix (Match CUDA Version):
```bash
# For CUDA 12.1:
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

# Verify NVIDIA Driver Installation:
nvidia-smi
```

---

## 🐍 2. Python Virtual Environments & Jupyter Kernels

### Create and Activate Virtual Environment:
```bash
# Using venv
python3 -m venv venv_aiml
source venv_aiml/bin/activate  # Linux/macOS
# venv_aiml\Scripts\activate   # Windows

# Register Virtual Environment with Jupyter Notebook
pip install ipykernel
python -m ipykernel install --user --name=venv_aiml --display-name "Python (AIML Env)"
```

---

## 📊 3. Pandas & NumPy Memory / Performance Fixes

```python
import pandas as pd

# Downcast numerical columns to reduce memory footprint
def optimize_memory(df):
    for col in df.select_dtypes(include=['int64']).columns:
        df[col] = pd.to_numeric(df[col], downcast='integer')
    for col in df.select_dtypes(include=['float64']).columns:
        df[col] = pd.to_numeric(df[col], downcast='float')
    return df
```
