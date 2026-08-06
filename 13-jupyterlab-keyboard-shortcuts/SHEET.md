# 📓 Module 13: JupyterLab & Notebook Shortcuts & Magic Commands

Master list of keyboard shortcuts for Command and Edit modes in JupyterLab, along with essential IPython Magic Commands (`%timeit`, `%pip`, `%env`, `%debug`) with clear practical examples.

---

## ⚡ 1. Command Mode Shortcuts (Press `Esc` first)

| Key Combination | Action (What it does) | Practical Usage Example |
| :--- | :--- | :--- |
| `A` | Insert new cell **Above**. | Press `Esc` then `A` to quickly add a code cell above current cell. |
| `B` | Insert new cell **Below**. | Press `Esc` then `B` to add a new cell underneath. |
| `D + D` (Press D twice) | **Delete** current cell. | Press `Esc` then `D, D` to delete an unwanted cell instantly. |
| `M` | Change cell type to **Markdown**. | Press `Esc` then `M` to turn code cell into text documentation. |
| `Y` | Change cell type to **Code**. | Press `Esc` then `Y` to convert Markdown cell back to Python code execution. |
| `Z` | **Undo** cell deletion. | Accidental cell delete? Press `Esc` then `Z` to recover deleted cell. |

---

## ✏️ 2. Edit & Execution Shortcuts (Inside cell)

| Key Combination | Action (What it does) | Practical Usage Example |
| :--- | :--- | :--- |
| `Shift + Enter` | Run cell and select cell below. | Press `Shift+Enter` to execute Python code and jump to next cell. |
| `Ctrl + Enter` | Run cell in-place. | Press `Ctrl+Enter` to execute current cell without moving cursor. |
| `Alt + Enter` | Run cell and insert new cell below. | Press `Alt+Enter` to execute code and immediately create fresh blank cell. |
| `Tab` | Code completion / Suggestions. | Type `import pan` and hit `Tab` to complete to `import pandas`. |
| `Shift + Tab` | View Function Docstring & Arguments. | Type `pd.read_csv(` and press `Shift+Tab` to view function parameters popup. |

---

## 🪄 3. Essential IPyton Magic Commands (`%` & `%%`)

```python
# Example 1: Install Python packages directly inside Notebook cell
%pip install pandas matplotlib scikit-learn

# Example 2: Measure exact execution speed of code (%timeit)
%timeit sum([i for i in range(1000000)])
# Output: 34.2 ms ± 1.1 ms per loop (mean ± std. dev. of 7 runs)

# Example 3: View current environment variables (%env)
%env PATH

# Example 4: Run external python script file inside notebook cell (%run)
%run ./scripts/data_processing.py

# Example 5: Interactive post-mortem debugger after error exception (%debug)
%debug
```
