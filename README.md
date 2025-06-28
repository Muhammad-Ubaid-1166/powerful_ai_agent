# 🤖 My First Powerful AI Agent — Deep Research Mode

This is my first real-life AI agent built for **deep research**. It accepts a user prompt and intelligently searches the web or knowledge sources — then returns structured, reliable results using context management, guardrails, and tool-based reasoning.

---

## 🧠 What This Agent Can Do

✅ Accept user questions like:
> "Tell me the latest news on quantum computing"  
> "What are the top 5 health benefits of ginger?"  
> "Summarize current updates in AI law from trusted sources"

✅ Then it:
- Searches through tools (web search / RAG / browser)
- Structures results into title, summary, and link
- Applies context memory (e.g., topic focus, prior turns)
- Uses **guardrails** to prevent hallucination or wrong formats
- Returns safe, valid answers using `pydantic` schema

---

## 🧱 Core Components

### `models.py`
Defines structured result using `pydantic`:

```python
class SearchResult(BaseModel):
    title: str
    url: str
    summary: str

This guarantees the agent only outputs clean, formatted info.
💼 Real-World Use Case

This agent can act as:

    A research assistant for students

    A news summarizer

    A topic explainer

    A context-aware Q&A bot with memory

All inside a powerful, safe wrapper.
🧩 Technologies Used
Tool	Purpose
🧠 Gemini (LiteLLM)	Powerful LLM to generate smart responses
🛠️ @function_tool	Tool-calling support (search, filter)
🧱 pydantic	Validate and format output
🔐 Guardrails	Ensure structured + safe outputs
🧠 ContextWrapper	Manage persistent user memory
🛠️ How to Run

    Clone the repo

git clone https://github.com/Muhammad-Ubaid-1166/initial-project.git
cd my_first_powerful_ai_agent/deep_research

    Set up virtual environment

python3 -m venv .venv
source .venv/bin/activate

    Install requirements

pip install -r requirements.txt

    Add .env file with:

GEMINI_API_KEY=your_gemini_key_here

    Run your script:

python your_script_name.py

👨‍💻 Author

Muhammad Ubaid
16-year-old AI Developer from Pakistan
Building the future, one agent at a time 🧠
