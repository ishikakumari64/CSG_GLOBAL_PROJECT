# CSG Global AI SQL Assistant

## Overview

CSG Global AI SQL Assistant is an AI-powered backend application that allows users to query enterprise data using natural language instead of writing SQL manually.

The system converts user questions into SQL queries using Large Language Models, validates the generated queries against Snowflake, ranks multiple valid queries, executes the best query, and converts the result into a natural language response.

## Key Features

* Natural Language to SQL generation
* LLM-based question understanding
* Snowflake database integration
* SQL query validation and execution
* Multiple query generation and ranking
* Duplicate query result detection
* Natural language response generation
* MongoDB-based chat history
* Pinecone vector search
* Feedback-based query storage
* OpenAI and Llama model support

## Workflow

```text
User Question
      |
      v
Database Schema and Sample Data
      |
      v
LLM Question Processing
      |
      v
SQL Generation
      |
      v
SQL Validation
      |
      v
Duplicate Detection
      |
      v
Query Ranking
      |
      v
Final SQL Query
      |
      v
Snowflake Execution
      |
      v
Natural Language Response
```

## Technology Stack

* Python
* Flask
* OpenAI
* Groq
* Llama
* LangChain
* Hugging Face
* Snowflake
* MongoDB
* Pinecone
* Pandas
* NumPy

## Project Structure

```text
CSG_GLOBAL_PROJECT/
|
|-- api.py
|-- test_LLM_query_endpoint.py
|-- README.md
```

`api.py` contains the main Flask backend and AI query processing logic.

`test_LLM_query_endpoint.py` contains testing-related code for the LLM query functionality.

## API Endpoints

### GET /options

Returns the available LLM model options.

### POST /chat

Accepts a natural language question and generates, validates, ranks, and executes the SQL query.

Example:

```json
{
    "key": "chat-session-001",
    "choice": "ChatGPT",
    "question": "Show the total invoice amount by supplier"
}
```

### GET /chat

Retrieves chat information.

### GET /chat-info

Retrieves available chat information.

### GET /chat/delete

Deletes chat history.

### POST /feedback

Stores feedback for generated queries.

### GET /get_feeback_status

Retrieves feedback status.

### GET /feedback/delete

Deletes stored feedback.

## Installation

Clone the repository:

```bash
git clone https://github.com/ishikakumari64/CSG_GLOBAL_PROJECT.git
cd CSG_GLOBAL_PROJECT
```

Create a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

The application requires credentials for external services such as Snowflake, OpenAI, Groq, MongoDB, and Pinecone.

Create a local `config.ini` file and add the required credentials.

Do not commit API keys, passwords, or database credentials to GitHub.

## Run the Application

```bash
python api.py
```

The application runs on:

```text
http://localhost:5001
```

## Example

User:
Which supplier has the highest invoice amount?

The system generates and validates the required SQL query, executes it on Snowflake, and returns the result in natural language.

