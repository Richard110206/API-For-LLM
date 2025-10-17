### How to build an API with Python?

### API-For-LLM
A lightweight Python API service that connects to the Ollama local large language model (LLM) and supports API key verification and credit management.
Overview

This project provides a FastAPI-based interface to interact with the Ollama local LLM. It implements core features such as API key authentication, call credit limits, and direct LLM response generation, enabling secure and controlled access to local LLM capabilities.

#### Features
- **API Key Verification**: Ensures only authorized users can access the LLM service via valid API keys.
- **Credit Management**: Each API key has an initial call credit limit to control service usage.
- **Simple Integration**: Easy-to-use HTTP POST interface for sending prompts and receiving LLM responses.
- **Local Deployment**: Works with locally deployed Ollama models (e.g., Mistral) to avoid external API dependencies.

#### Prerequisites
- Python Environment: Python 3.8 or higher.
- Ollama Installation:
Install Ollama from the official website.
Pull the required LLM model locally (default: Mistral) using the command:
```bash
ollama pull mistral
```
API Key Preparation: Prepare a custom API key for authentication (to be configured in the .env file).
Installation Steps
1. Clone the Repository
```bash
git clone https://github.com/Richard110206/API-For-LLM.git
cd API-For-LLM
```
2. Install Dependencies
Install all required Python packages using requirements.txt:
```bash
pip install -r requirements.txt
```
#### Usage Guide
**1. Start the API Service**
Run the FastAPI service using Uvicorn:
```bash
uvicorn main:app --reload
```
The service will start at `http://127.0.0.1:8000`.
Use --reload for auto-reloading during development (remove this flag in production).

**2. Test the API**
- Option 1: Use the Built-in Test Script
Execute the pre-written test script to quickly verify the API:
```bash
python test_api.py
```
The script sends a prompt (tell me what's LLM?)(of course,change by your mind) to the API and prints the LLM response.

- Option 2: Use Tools Like Postman/Curl
Request Details:
Method: POST
URL: http://127.0.0.1:8000/generate?prompt=your_prompt_here
Headers:
x-api-key: Your API key (from the .env file)
Content-Type: application/json
