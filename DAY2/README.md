Day 2 – LLM Models, Privacy, Tokenization & Prompting (Simple Notes)
✅ What I Learned Today
1. Types of LLMs

Closed-Source Models → GPT-4, Gemini

Very powerful

Cost per token

Data privacy risk

Open-Source Models → Llama 3, Mistral, Gamma

Free to run locally

Good for projects with sensitive data

2. PII (Personal Identifiable Information)

Anything that identifies a person
Examples: Aadhaar, biometrics, phone number, address

If data has PII → use local models OR remove PII before sending to API

3. Batch vs Real-Time Processing

Batch → No urgent output
Example: summarizing yesterday’s 10,000 news articles

Real-Time → Immediate response
Example: travel chatbot answering user questions instantly

4. Cost & Latency

Closed-source models charge based on tokens

Open-source models only need laptop/PC power

Bigger model = slower and needs more hardware

5. Prompt Engineering (ROLES Method)

A simple way to write better prompts:

R – Role → What role should AI take? (teacher, developer, etc.)

O – Objective → What do you want? (write, explain, summarize)

L – Limitations → Word limit / rules

E – Examples → Give sample input-output

S – Style → Format (JSON, table, bullet points)

6. Advanced Prompt Techniques

Chain of Thought → “Think step by step”

Self-Consistency → AI gives multiple answers → best one chosen

7. Hands-On Setup

Created PyCharm project with Python 3.12

Added .env file for API key

Installed packages from requirements.txt

Used Ollama to download and test local models (Gamma 3 / Llama 3)

8. Use-Case Examples

Legal Contracts (Sensitive) → Use local models

Travel Chatbot (Public) → Use API models

Large Batch Summaries → Use lightweight open-source models

📂 Tools Used Today

PyCharm

Google Colab

Hugging Face (model details)

Ollama (run local models)
