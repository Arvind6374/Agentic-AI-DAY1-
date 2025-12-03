
# Agentic AI – Day 3
Building intelligent agents using LangChain.  
This module focuses on tool usage, intent routing, building weather and currency agents, and creating a master agent capable of choosing the correct tool automatically.

---

## 🚀 Day 3 Overview

### ✔ Installing Required Libraries
```python
!pip install langchain==0.3.7 langchain-core==0.3.15 langchain-google-genai==2.0.4 google-generativeai==0.8.3 protobuf==5.27.0
````

Installed libraries for:

* LangChain core
* Google Gemini integration
* Output parsers
* Weather & currency API usage

---

## 🌦 Weather Agent

### 🔧 What You Built

* A **weather agent** that:

  * Detects when the user asks about weather
  * Extracts the city name
  * Calls **Open-Meteo API** for live weather
  * Responds in a friendly natural language

### 🌍 Weather API Flow

1. Convert city → latitude/longitude
2. Fetch real-time weather info
3. Format final answer using Gemini

### 🧪 Example

```python
print(gpt4o_mini_agent("What is the weather in TamilNadu"))
```

---

## 💱 Currency Converter Agent

### 🔧 What You Built

* A **currency exchange agent** that:

  * Detects questions like “USD to INR?”
  * Calls a live currency API
  * Returns exchange rate with a formatted response

### 💵 API Used

* Exchange Rate API: [https://open.er-api.com](https://open.er-api.com)

### 🧪 Example

```python
answer = gpt4o_mini_currency_agent("How much is USD to INR?")
print(answer)
```

---

## 🤖 Creating a Master Agent (Router + Tool Executor)

### ✔ Purpose

You created a **tool-routing agent** that decides which API to call:

* If user asks about **weather** → weather.lookup
* If user asks about **currency** → fx.convert
* Otherwise → no tool

### 🧠 How It Works

#### 1️⃣ Intent Routing

Gemini decides:

```json
{"tool_name": "...", "args": {...}}
```

#### 2️⃣ Execute Tool

* Weather tool
* Currency tool

#### 3️⃣ Final Response

Gemini formats a friendly final answer based on tool result.

### 🧪 Example

```python
master_agent("Why is the sky blue?")
```

The agent correctly identifies **no tool needed** and answers normally.

---

## 🛠 Concepts Learned Today

### ✔ Tool Calling

Building functions that agents can call automatically.

### ✔ Intent Detection

Using LLMs to understand what the user is asking.

### ✔ API Integration

Weather API + Currency API inside LangChain agent workflows.

### ✔ Output Parsing

Cleaning Gemini’s JSON output before execution.

### ✔ Master Agent Design

A single agent that:

* Detects user intent
* Chooses correct tool
* Executes tool
* Generates final response

---

## 🧰 Tools Used Today

* LangChain
* Google Gemini
* Open-Meteo Weather API
* Exchange Rate API
* Python (requests, JSON handling)

```

