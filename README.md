## LLM_API
![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-green.svg)
![Ollama](https://img.shields.io/badge/Ollama-LocalLLM-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

[中文版本](README_zh-CN.md) | [English Version](README.md)

A lightweight Python API service that connects to the Ollama local large language model (LLM) and supports API key verification and credit management.
Overview

This project provides a FastAPI-based interface to interact with the Ollama local LLM. It implements core features such as API key authentication, call credit limits, and direct LLM response generation, enabling secure and controlled access to local LLM capabilities.

### 🚀 Features
- **API Key Verification**: Ensures only authorized users can access the LLM service via valid API keys.
- **Credit Management**: Each API key has an initial call credit limit to control service usage.
- **Simple Integration**: Easy-to-use HTTP POST interface for sending prompts and receiving LLM responses.
- **Local Deployment**: Works with locally deployed Ollama models (e.g., Mistral) to avoid external API dependencies.


### 📌 Prerequisites
- Python Environment: Python 3.8 or higher.
- Ollama Installation:
Install Ollama from the official website or using the command.
```bash
brew install ollama
```
Pull the required LLM model locally (default: Mistral) using the command:
```bash
ollama run mistral
```

### 📝 Installation Steps

**1. Clone the Repository**
```bash
git clone https://github.com/Richard110206/API-For-LLM.git
cd API-For-LLM
```

**2. Install Dependencies**
Install all required Python packages using requirements.txt:
```bash
pip install -r requirements.txt
```

### 🔧 Quick Start
**1. Start the API Service**
Run the FastAPI service using Uvicorn:
```bash
uvicorn main:app --reload
```
The service will start at `http://127.0.0.1:8000`.
Use --reload for auto-reloading during development (remove this flag in production).

**2. Test the API**

- **Option 1**: Use the Built-in Test Script
Execute the pre-written test script to quickly verify the API:
```bash
python test_api.py
```
The script sends a prompt (tell me what's LLM?)(of course,change by your mind) to the API and prints the LLM response.

- **Option 2**: Use Tools Like [Postman](https://www.postman.com/downloads/)/Curl

  - Method: POST
  - URL: http://127.0.0.1:8000/generate?prompt=your_prompt_here
  - Headers: x-api-key: Your API key (from the .env file)
  - Content-Type: application/json
<img width="564" height="711" alt="image" src="https://github.com/user-attachments/assets/096b2cf8-d7c1-4a2b-930c-13802a90a22a" />



**3. Check API Documentation**
FastAPI provides automatic interactive documentation:
Swagger UI: Visit `http://127.0.0.1:8000/docs` in your browser to test the API visually.


### Reference:

[Learn Ollama in 15 Minutes - Run LLM Models Locally for FREE](https://www.youtube.com/watch?v=UtSSMs6ObqY&t=600s)

[How To Build an API with Python (LLM Integration, FastAPI, Ollama & More)](https://www.youtube.com/watch?v=cy6EAp4iNN4)
