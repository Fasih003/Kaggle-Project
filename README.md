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
| **Search Tool** |
