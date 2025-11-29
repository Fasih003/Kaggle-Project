````markdown
# Weekend Trip Planner Agent  
**Concierge Track Submission — Kaggle Agents Intensive Capstone**

The Weekend Trip Planner Agent is a multi-agent LLM system that automates the end-to-end process of planning a personalized weekend getaway. It provides a single conversational interface to analyze preferences, retrieve real-time-style data, and return a structured, actionable travel plan.

---

## 🚀 Overview

Planning a short trip usually involves scattered research across multiple sources and repeated decision-making. This agent centralizes that workflow by:

- Understanding user intent and preferences  
- Fetching external travel context (via a mocked web search tool)  
- Formatting results into a polished recommendation  
- Maintaining conversation memory across turns  

The result is a fast, context-aware trip planning experience delivered in one conversation.

---

## 🎯 Project Goal

**Problem**  
Trip planning requires juggling destinations, activities, and logistics, making it time-consuming and mentally taxing.

**Solution**  
A Concierge Agent that manages ideation, discovery, and recommendation in a structured, multi-agent workflow.

**Value**  
- Reduces decision fatigue  
- Saves research time  
- Delivers personalized recommendations  
- Supports conversational planning with memory  

---

## 🧠 Architecture & Key Concepts

This project demonstrates **three core concepts** from the Agents Intensive course:

---

### 1. Multi-Agent System (Sequential Agents)

The system is built as a pipeline of LLM-powered agents, each responsible for a single, well-defined stage of reasoning.

| Agent | Responsibility | Technology |
|--------|---------------|------------|
| **Planner Agent (Orchestrator)** | Determines next action and controls flow using structured outputs | Gemini (JSON-based control) |
| **Search Tool** | Retrieves external data for destinations and activities | Mocked `WebSearchTool` |
| **Formatter Agent** | Converts raw results into a user-friendly response | Gemini |

Each agent receives structured input from the previous step, ensuring deterministic and debuggable execution.

---

### 2. Tools: Mocked Web Search

The agent uses a simulated web search tool to demonstrate external data integration.

#### Implementation
```python
class WebSearchTool:
    def search(self, query: str):
        ...
````

#### Purpose

* Demonstrates architecture for live data retrieval
* Enables simulated access to:

  * destination ideas
  * weather summaries
  * activities

The Planner Agent calls this tool using a structured action format.

---

### 3. Sessions & State Management

The agent maintains conversation memory across multiple turns using a session object.

#### Session Object

```python
class TripPlanningSession:
    session_id: str
    conversation_history: List[Dict]
    user_preferences: Dict
    current_plan_stage: str
```

#### Stored Data

* Conversation history
* User interests (e.g., "coastal", "hiking")
* Planning phase (e.g., `initial`, `presenting_ideas`, `finalizing`)

This prevents redundant questions and enables continuity.

---

## ⚙️ Setup & Installation

### Prerequisites

* Python 3.8+
* `google-genai` (or similar Gemini SDK)
* Gemini API Key

---

### Local Setup

#### 1. Clone Repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME
cd YOUR-REPO-NAME
```

#### 2. Set Environment Variable

```bash
export GEMINI_API_KEY="YOUR_API_KEY_HERE"
```

> Do not hardcode your API key in the source code.

#### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

#### 4. Run the Agent

```bash
python agent_main.py
```

---

## ▶️ Example Execution

The `if __name__ == "__main__"` block runs a **three-turn test conversation** demonstrating:

* Sequential agent orchestration
* Decision routing by the Planner Agent
* Tool invocation
* Session-based state updates

Sample flow:

1. User expresses travel intent
2. Planner Agent requests external data
3. Formatter Agent returns final itinerary

---

## 📁 Project Structure

```
.
├── agent_main.py           # Application entry point
├── agents/
│   ├── planner_agent.py    # Orchestration logic
│   ├── formatter_agent.py  # Response generation
├── tools/
│   ├── web_search_tool.py  # Mocked external search
├── session/
│   └── trip_session.py     # State management
├── requirements.txt
└── README.md
```

---

## ✅ Features

* Modular, multi-agent pipeline
* Deterministic routing via structured JSON outputs
* Tool integration
* User preference memory
* Session-level context persistence
* Clean separation of responsibilities

---

## 🧪 Testing

The built-in script demonstrates:

* Multi-turn reasoning
* Tool calls
* State persistence
* Controlled agent handoff

Additional tests can be added by including new conversations in `agent_main.py`.

---

## 📌 Notes

* Web search is mocked for demonstration purposes.
* The system design supports replacement with:

  * Google Custom Search API
  * SerpAPI
  * Other real-time data providers

---

## 🧩 Future Improvements

* Real live web integration
* Calendar integration
* Budget-based constraints
* Hotel and transport booking APIs
* User profiles
* Web UI interface

---

## 📄 License

Specify your licensing here (e.g.):

```
MIT License
```

---

## 👤 Author

**Your Name**
Kaggle Agents Intensive Capstone
Concierge Track

---

## 🌟 Acknowledgements

* Kaggle Agents Intensive
* Google Gemini API
* Open-source community

```

---

If you want, provide your **GitHub repo name, username, and author name** and this README can be customized for direct copying.
```
