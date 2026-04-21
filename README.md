# SQL-Agent-with-Tool-Calling
# SQL Agent with Tool Calling

An LLM-powered intelligent SQL agent that converts natural language business questions into executable SQL queries using tool-calling and schema-aware reasoning.

---

## Overview

This project demonstrates how to build an AI-powered database assistant using a Large Language Model (LLM) with tool access.

The agent can:
- Understand user questions in natural language
- Dynamically inspect database schema
- Generate optimized SQL queries
- Execute SQL on the connected database
- Return clean business-friendly responses

---

---

## Workflow

1. User asks a business question  
   Example: *"What were total sales last month?"*

2. LLM calls **get_schema** tool  
   - Retrieves table names  
   - Retrieves column names  
   - Retrieves datatypes  

3. LLM analyzes schema  
   - Identifies relevant tables/columns  

4. LLM generates SQL query  

5. LLM calls **execute_sql** tool  
   - Executes generated SQL query  

6. Formats final response into human-readable answer  

---

## Example Use Case

### User Input:
```sql
What were total sales last month?
```

### Generated SQL:
```sql
SELECT SUM(amount)
FROM orders
WHERE order_date >= DATE_TRUNC('month', CURRENT_DATE - INTERVAL '1 month')
```

### Output:
```text
Total sales for last month were $125,430.
```

---

## Tools Implemented

### get_schema()
Returns:
- Table names
- Column names
- Datatypes

### execute_sql()
Executes generated SQL query on database.

---

## Tech Stack

- Python
- OpenAI / LLM APIs
- SQL
- Jupyter Notebook
- Tool Calling / Function Calling
- Agentic AI Design Pattern

---

## Business Applications

- BI/Analytics Assistant  
- Self-Service SQL Generation  
- Internal Data Query Automation  
- Non-Technical Stakeholder Data Access  

---

## Future Improvements

- Add ReAct Agent Framework  
- Add Query Validation Layer  
- Add SQL Guardrails / Hallucination Prevention  
- Add Streamlit Frontend UI  

