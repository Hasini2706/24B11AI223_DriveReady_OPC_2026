# 24B11AI223_DriveReady_OPC_2026

Repository for the **DriveReady OPC 2026 — Agentic AI** track, featuring hands-on implementations of Large Language Model (LLM) pipelines, prompt engineering, safe evaluation harnesses, and autonomous agent architectures.

---

## 📁 Repository Structure

```text
24B11AI223_DriveReady_OPC_2026/
├── Day-1/
│   ├── task.py
│   └── README.md
├── Day-2/
│   ├── task.py
│   └── README.md
└── Day-3/
    ├── task.py
    └── README.md
```

---

## 🚀 Daily Breakdown & Milestones

| Day | Module / Focus | Key Concepts & Tools | Documentation |
| :---: | :--- | :--- | :---: |
| **Day 1** | **LLM Foundations & Prompt Guard** | • Inference with `ChatGroq` (`openai/gpt-oss-120b`)<br>• System persona and operational constraints<br>• Prompt injection detection via `meta-llama/llama-prompt-guard-2-22m` | [Day-1 README](Day-1/README.md) |
| **Day 2** | **Dynamic Prompts & Structured Chat** | • Dynamic context injection (catalog & pricing via JSON)<br>• Tool logging decorators (`@log_call`)<br>• Sliding window multi-turn memory (`MAX_TURNS`)<br>• Few-shot intent classification (`order`, `question`, `complaint`)<br>• Strict structured JSON order extraction | [Day-2 README](Day-2/README.md) |
| **Day 3** | **LCEL, Evaluation Harness & Travel Agent** | • Google GenAI (`ChatGoogleGenerativeAI` with `gemini-3.8-flash`)<br>• CityExpress Bus Travels assistant (bus availability, distance, fares & seat booking)<br>• Modern LCEL (`prompt \| llm \| parser`) & memory via `MessagesPlaceholder("history")`<br>• Automated regression test suite (`run_tests` with assertion CSV)<br>• Agent foundations with `create_agent` | [Day-3 README](Day-3/README.md) |

---

## 🛠️ Prerequisites & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Hasini2706/24B11AI223_DriveReady_OPC_2026.git
cd 24B11AI223_DriveReady_OPC_2026
```

### 2. Install Dependencies
```bash
pip install langchain langchain-core langchain_groq groq langchain-google-genai openai
```

### 3. Configure API Keys
Set up your environment variables for Groq and Google GenAI:

- **Windows (PowerShell)**:
  ```powershell
  $env:GROQ_API_KEY="your-groq-api-key"
  $env:GOOGLE_API_KEY="your-google-api-key"
  ```
- **Linux / macOS**:
  ```bash
  export GROQ_API_KEY="your-groq-api-key"
  export GOOGLE_API_KEY="your-google-api-key"
  ```

---

## 🏃 Running the Tasks

- **Day 1**:
  ```bash
  python Day-1/task.py
  ```
- **Day 2**:
  ```bash
  python Day-2/task.py
  ```
- **Day 3**:
  ```bash
  python Day-3/task.py
  ```

---

## 👤 Author
- **Roll Number**: 24B11AI223
- **Track**: DriveReady OPC 2026 (Agentic AI)
