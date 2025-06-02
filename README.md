# Gemini AI Agent Example (Async & Sync)

This repository contains two example scripts demonstrating how to interact with the Gemini AI language model using Python agents:  
1. **Asynchronous (async) agent** — uses asyncio for non-blocking calls  
2. **Synchronous (sync) agent** — blocking calls, runs sequentially

---

## Requirements

- Python 3.8+  
- Install dependencies (example):  
  ```bash
  pip install python-dotenv agents asyncio

A .env file with your Gemini API key:

ini
Copy
GEMINI_API_KEY=your_actual_api_key_here
Common Setup
Both scripts share these core components:

Load environment variables using dotenv

Initialize an async OpenAI client with Gemini API key

Create a chat completions model for the Gemini "gemini-2.0-flash" model

Setup run configuration with tracing disabled

Async Agent (async_agent.py)
Description
Runs the agent asynchronously using Python’s asyncio event loop and await syntax. This allows the program to perform other operations while waiting for the agent’s response, making it suitable for I/O bound or concurrent workloads.

How to run
bash
Copy
python async_agent.py
Code highlights
Defines an async main() coroutine

Uses await Runner.run(...) to invoke the agent asynchronously

Calls asyncio.run(main()) to start the async event loop

Sync Agent (sync_agent.py)
Description
Runs the agent synchronously and blocks the program execution until the response is received. Simpler flow but not suitable for concurrent or high-performance scenarios.

How to run
bash
Copy
python sync_agent.py
Code highlights
Directly calls Runner.run_sync(...) to execute the agent

Blocks until the final output is ready

Example Output
text
Copy
CALLING AGENT

Assistant: Sukkur is a city in Pakistan located on the west bank of the Indus River...
Notes
Make sure your .env file has the correct Gemini API key

Async code requires Python 3.7+ for asyncio support

Sync code is easier for quick testing or scripts that do not require concurrency

