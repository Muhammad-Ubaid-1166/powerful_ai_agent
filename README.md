# 🤖 My First Powerful AI Agent — Deep Research Mode

This is my **first real-life AI agent** built for deep research and intelligent information retrieval.  
It accepts a user prompt, searches the web or relevant sources, and returns **structured, reliable results** using:

- 🔄 Context Management  
- 🔐 Guardrails for Output Safety  
- 🛠️ Function Tool Calling  
- 🧠 Agent Reasoning Capabilities  
- 📦 `pydantic` Schema Validation

---

## 🧠 What This Agent Can Do

✅ Accepts natural language prompts like:
- “Tell me the latest news on quantum computing.”
- “What are the top 5 health benefits of ginger?”
- “Summarize current updates in AI law from trusted sources.”
- “Compare Tesla and BYD based on latest market reports.”

✅ Then it:
- Automatically selects the right tool to search
- Pulls and formats real-time or pre-stored data
- Wraps results into a structured response
- Maintains **short-term memory** through context
- Uses **guardrails** to prevent untrusted, hallucinated, or unsafe replies
- Returns structured output like:

```json
{
  "title": "AI in Healthcare: June 2025 Report",
  "url": "https://example.com/ai-healthcare-2025",
  "summary": "This report outlines recent breakthroughs in AI-assisted diagnostics, patient monitoring, and data analytics."
}
```

---

## 🧱 Core Component

### `models.py`

Defines structured schema using `pydantic`:

```python
from pydantic import BaseModel

class SearchResult(BaseModel):
    title: str
    url: str
    summary: str
```

This schema ensures consistent, safe, and clean output for LLM responses.

---

## 🔄 Architecture Overview

```mermaid
graph TD
    A[User Prompt] --> B[Agent]
    B --> C{Tool Needed?}
    C -- Yes --> D[Call Tool (Search/Web/DB)]
    C -- No --> E[Use LLM Response]
    D --> F[Wrap in SearchResult Model]
    E --> F
    F --> G[Apply Guardrails]
    G --> H[Return Final Output]
```

---

## 💼 Real-Life Use Cases

This AI agent can serve as:
- 🧑‍🎓 A research assistant for students and researchers  
- 🧠 A summarizer for news articles and scientific reports  
- 🧾 A browser assistant to extract reliable data from live sources  
- 🗣️ A context-aware chatbot for multi-turn conversations  

---

## 🧩 Technologies Used

| Tool                     | Purpose                                      |
|--------------------------|----------------------------------------------|
| 🧠 Gemini (via LiteLLM)  | Large Language Model for intelligent replies |
| 🛠️ `@function_tool`     | Makes external tools callable by agent       |
| 📦 `pydantic`            | Validates and structures outputs             |
| 🔐 Guardrails            | Ensures output safety and formatting         |
| 🧠 RunContextWrapper     | Maintains short-term memory (context)        |

---

## 🚀 How to Run the Agent

### 1. Clone the Repository
```bash
git clone https://github.com/Muhammad-Ubaid-1166/initial-project.git
cd my_first_powerful_ai_agent/deep_research
```

### 2. Set Up a Virtual Environment
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Add Your Gemini API Key
Create a `.env` file:
```
GEMINI_API_KEY=your_gemini_key_here
```

### 5. Run the Agent
```bash
python your_script_name.py
```

---

## 💬 How to Use This Agent

Once the agent is running, it enters interactive mode in your terminal or notebook.  
You can now start chatting with the agent and asking questions like:

### 🧪 Example Prompts:
```text
> What are the benefits of green tea?
> Show me latest news on space exploration.
> Summarize top 3 AI breakthroughs in 2025.
```

### 🧠 What the Agent Does:
1. Understands your question using Gemini
2. Selects tools like `search_tool`, `summarizer`, etc.
3. Retrieves relevant info
4. Formats the result in a structured way
5. Applies safety guardrails
6. Returns the final clean output

---

## 📈 What I Learned

This project helped me understand:

- How to wrap user data using `@dataclass` and `RunContextWrapper`
- How to build real AI tools using `@function_tool`
- How to manage structured output using `pydantic`
- How to implement safe logic using guardrails

---

## 👨‍💻 Author

**Muhammad Ubaid**  
16-year-old AI Developer from Pakistan 🇵🇰  
Building the future — one agent at a time.  
[GitHub Profile](https://github.com/Muhammad-Ubaid-1166)

---

> ✨ "This is not a demo — this is the beginning of something powerful."
