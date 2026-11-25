# Day 2: Structured Prompts, Dynamic Context & Multi-Turn Chatbots

## 📌 Overview
Day 2 deepens conversational AI development with advanced prompt engineering techniques, state management, structured JSON outputs, intent classification, and tool-augmented business logic for home bakery and farm order management.

---

## 📂 Files
- [`task.py`](task.py): Complete multi-turn chatbot script covering dynamic menu injection, few-shot classification, structured extraction, and sliding window conversation history.

---

## 🎯 Key Concepts & Implementation

### 1. Dynamic Context & Function Logging
- **Dynamic System Prompts**: Injecting external data (menu catalogs and prices) into the system prompt dynamically using `json.dumps`.
- **Python Decorators**: Implementing a `@log_call` wrapper to trace and log tool/function invocations with arguments and return values.
- **Deterministic Helpers**: `get_price(item, qty)` helper ensuring mathematical accuracy rather than relying on LLM hallucination.

### 2. Multi-Turn Conversation & Sliding Memory Window
- Implements a conversational history loop with role-based messages (`system`, `user`, `assistant`).
- **Context Window Management**: Restricting context to `MAX_TURNS` to prevent context bloat and manage token budgets.
- **Resilience & Error Handling**: Gracefully handling `RateLimitError` and `APIConnectionError`.

### 3. Few-Shot Intent Classification
- Classifying incoming user messages into distinct categories (`order`, `question`, `complaint`) using in-context few-shot examples.

### 4. Structured Data Extraction (JSON Mode)
- Instructing the LLM to extract structured customer orders (`name`, `item`, `qty`, `date`, `eggless`) strictly in valid JSON format.
- Parsing and validating the output with `json.loads` and exception handling for downstream database or order processing.

### 5. Interactive Chat Loop
- Command-line interactive chat supporting real-time user input and clean exit commands (`bye`, `exit`, `quit`).

---

## 🚀 Setup & Execution

### Prerequisites
Install required dependencies:
```bash
pip install langchain_groq groq openai
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
