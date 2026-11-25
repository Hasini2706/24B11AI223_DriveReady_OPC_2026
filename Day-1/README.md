# Day 1: LLM Foundations, System Prompting & Prompt Guard

## 📌 Overview
Day 1 covers the fundamentals of building conversational AI applications using **LangChain** and **Groq Cloud**. It introduces system prompt engineering, persona and rule enforcement for an AI assistant, and AI safety mechanisms with prompt guard models.

---

## 📂 Files
- [`task.py`](task.py): Python script demonstrating model initialization, prompt steering, and safety checks.

---

## 🎯 Key Concepts & Implementation

### 1. Model Initialization with Groq
- Utilizes `ChatGroq` from `langchain_groq` powered by high-speed inference.
- Configured with `openai/gpt-oss-120b` (or other Groq-hosted open weights) at temperature `0` for deterministic outputs.

### 2. System Prompt Design
- **Role & Persona Definition**: Establishing a customer support assistant for *"Sweet Crumbs Home Bakery"*.
- **Facts & Constraints**: Strict operational constraints (24 hours notice required, eggless availability, no delivery guarantees).
- **Output Shaping**: Bounding responses under 60 words and maintaining a polite tone.

### 3. Safety & Prompt Injection Detection
- Employs **Meta's Llama Prompt Guard** (`meta-llama/llama-prompt-guard-2-22m`) via the native `groq` SDK.
- Scans input prompts to classify and score injection attempts or jailbreaks before passing them to the main LLM pipeline.

---

## 🚀 Setup & Execution

### Prerequisites
Install the required dependencies:
```bash
pip install langchain_groq groq
```

### Environment Variables
Set your Groq API key:
- **Windows (PowerShell)**:
  ```powershell
  $env:GROQ_API_KEY="your-groq-api-key"
  ```
- **Linux / macOS**:
  ```bash
  export GROQ_API_KEY="your-groq-api-key"
  ```

### Run the Script
```bash
python task.py
```
