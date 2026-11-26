# Day 3: LangChain LCEL, Evaluation Harness & Agent Foundations (Bus Travel Assistant)

## 📌 Overview
Day 3 transitions to **Google Gemini** models using modern **LangChain Expression Language (LCEL)**. It implements a smart conversational **Bus Travel Booking Agent** (`CityExpress Bus Travels`) capable of answering user inquiries regarding bus availability across areas, route distances, ticket costs, and seat booking while maintaining conversation context and passing automated regression tests.

---

## 📂 Files
- [`task.py`](task.py): Script demonstrating LCEL chains with `gemini-3.8-flash`, conversational memory for passenger bookings, automated assertion testing for route/fare queries, and LangChain agent scaffolding.

---

## 🎯 Key Concepts & Implementation

### 1. Travel Booking Domain System Prompt
- **ROLE**: AI booking assistant for *CityExpress Bus Travels*.
- **FACTS**: Bus availability, route distances (e.g., Vijayawada to Hyderabad: 275 km, to Vizag: 350 km, to Rajahmundry: 160 km), seating categories (AC Sleeper, Non-AC Seater, Express), schedules, and ticket pricing.
- **RULES**: Grounded strictly in factual route tables; handles unknown routes by deferring to the travel desk; accurate fare computation for multi-seat bookings.

### 2. Google Gemini & LCEL Chains
- Integration with Google GenAI via `ChatGoogleGenerativeAI` (`model="gemini-3.8-flash"`).
- Composable chain architecture using the pipe operator (`|`):
  ```python
  chain = prompt | llm | StrOutputParser()
  ```
- Utilizing `ChatPromptTemplate` with `MessagesPlaceholder("history")` to track multi-turn state (e.g., passenger name, destination, preferred departure times).

### 3. Conversational State Tracking
- Maintains a conversational memory buffer (`history`) to preserve passenger details across turns (e.g., remembering passenger name and booking preferences).

### 4. Automated LLM Testing & Quality Assurance
- **Evaluation Harness**: Custom test runner (`run_tests`) that parses test cases from `test.csv`.
- Validates that mandatory facts (`must_include`) such as destinations, ticket prices, and distances appear accurately in the generated responses.

### 5. Agent Architecture Foundations
- Sets up `create_agent` from `langchain.agents` combining the model, system prompt, and future tool integrations (e.g., live bus tracking or payment gateway APIs).

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
