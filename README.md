# 🤖 Natural Language to SQL Query Agent  
🔗 👉 Workflow: Ask Questions in Plain English → Get Answers Directly from PostgreSQL

---

## 🎯 Objective  
To build an AI-powered SQL Agent in n8n that allows users to ask questions in plain English (e.g., “Show me sales from Mumbai last month”) and automatically converts them into SQL queries, executes them on a PostgreSQL database, and returns meaningful answers — without requiring any SQL knowledge.

---

## 🧩 What This Automation Does  

This workflow enables intelligent, conversational database querying:

- Understands user questions in plain English  
- Converts natural language → SQL query using AI  
- Checks table structure & schema automatically  
- Executes queries safely on PostgreSQL  
- Returns clean, readable answers  
- Asks follow-up questions if the query is unclear  
- Handles “no data found” scenarios gracefully  

✨ Your AI becomes a **smart junior data analyst** inside n8n.

---

## 🧠 Mindset / Thought Process  
1. Build an experience where users chat naturally with the system.  
2. Use AI to convert natural language into SQL queries.  
3. Provide the agent with tools to run queries directly on PostgreSQL.  
4. Test with simple → complex queries to ensure reliability.

---

## 🏗️ Solution Design  

- Trigger that listens to messages (chat-based workflow)  
- AI Agent that understands questions and plans the response  
- Tools to inspect database schema and execute SQL queries  
- Gemini model for natural language → SQL generation  
- Memory node to maintain context across the conversation  

---

## 🛠️ Step-by-Step Execution  

### **1️⃣ Set up n8n**
Create a cloud account or self-host locally.  
🔗 https://app.n8n.cloud/register  

---

### **2️⃣ Use AI Tools to Draft the Flow**
Use ChatGPT/Perplexity for designing the automation.  
Prompt example:  
> I want to create an AI Agent in n8n that converts natural language to SQL, executes it on Postgres, checks data availability, and handles follow-up questions.

---

### **3️⃣ Trigger (Chat Listener)**  
Starts the workflow whenever a user sends a chat message.

---

### **4️⃣ Add the AI Agent Node**  
This is your “smart junior SQL analyst.”

Use this system message (or generate a custom one):

> Act as a SQL Agent. Convert natural language questions into SQL queries. Understand available tables/columns. Ask follow-up questions when unclear. If no data exists, respond: “There is no available data to answer the question, but I can help with the following details.”

---

### **5️⃣ Give Intelligence to the Agent**

Attach essential tools:

#### ✔ Schema Inspector Tool  
Agent checks table structure using SQL like:  
```sql
SELECT table_name, column_name, data_type, is_nullable
FROM information_schema.columns
WHERE table_schema = 'public'
ORDER BY table_name, ordinal_position;
