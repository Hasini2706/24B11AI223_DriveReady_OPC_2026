# Day 3: LangChain LCEL, Evaluation Harness & Agent Foundations

## 📌 Overview
Day 3 transitions to **Google Gemini** models using modern **LangChain Expression Language (LCEL)**. It covers stateful prompt templates with history placeholders, automated test harnesses for LLM quality assurance, and the initial setup of tool-calling agents.

---

## 📂 Files
- [`task.py`](task.py): Script demonstrating LCEL chains with `gemini-3.8-flash`, conversational memory, automated assertion testing, and LangChain agent scaffolding.

---

## 🎯 Key Concepts & Implementation

### 1. Google Gemini & LCEL Chains
- Integration with Google GenAI via `ChatGoogleGenerativeAI` (`model="gemini-3.8-flash"`).
- Building composable chains with the modern pipe operator (`|`):
  ```python
  chain = prompt | llm | StrOutputParser()
  ```
- Leveraging `ChatPromptTemplate` and `MessagesPlaceholder("history")` to seamlessly inject conversational state.

### 2. Conversational State Tracking
- Maintaining a memory buffer (`history`) to track conversation turns, allowing the LLM to remember entity details across questions (e.g., customer name, order specifics).

### 3. Automated LLM Testing & Quality Assurance
- **Evaluation Harness**: Custom test runner (`run_tests`) validating LLM behavior against predefined ground-truth expectations.
- Reads test cases from a CSV file (`test.csv`) and asserts whether mandatory responses (`must_include`) are present in generated answers.
- Calculates and logs pass/fail rates for prompt regression testing.

### 4. Agent Architecture Foundations
- Initializing agents with `create_agent` from `langchain.agents` combining the model, system prompt, and future tool integrations.

---

## 🚀 Setup & Execution

### Prerequisites
Install dependencies:
```bash
pip install langchain-google-genai langchain-core langchain
```

### Environment Variables
Set your Google API key:
- **Windows (PowerShell)**:
  ```powershell
  $env:GOOGLE_API_KEY="your-google-api-key"
  ```
- **Linux / macOS**:
  ```bash
  export GOOGLE_API_KEY="your-google-api-key"
  ```

### Run the Script
```bash
python task.py
```
