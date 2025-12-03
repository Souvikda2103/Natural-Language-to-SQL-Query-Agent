# 🤖 Natural Language to SQL Query Agent  
Ask questions in plain English → Get answers directly from PostgreSQL.

---

## 🎯 Objective  
Build an AI system in n8n that lets users ask normal questions like  
“Show me sales from Mumbai last month”  
and automatically converts them into SQL, runs the query, and shows the result — without the user writing SQL.

---

## 🧾 What This Automation Does  
- Understands your question (plain English)  
- Converts it into a correct SQL query  
- Checks database tables and columns  
- Runs the SQL on PostgreSQL  
- Shows the results in chat  
- Asks follow-up questions if your query is unclear  
- Tells you clearly when no data exists for your question  

---

## 🧠 How It Works  
1. You send a message → workflow starts  
2. AI Agent reads your question  
3. AI understands table structure  
4. AI creates the right SQL query  
5. Query is executed in PostgreSQL  
6. Result is shown back to you in simple text  

---

## 🛠️ Steps to Build  
### 1️⃣ Create or open your n8n account  
https://app.n8n.cloud/register

### 2️⃣ Use ChatGPT/Perplexity to draft the automation steps  
Prompt example:  
“Help me create an AI agent that converts English to SQL and runs the query in Postgres.”

### 3️⃣ Add the Chat Trigger  
Starts the workflow when you send a message.

### 4️⃣ Add the AI Agent Node  
This is your “SQL Analyst.”  
Use a system message like:  
“Convert natural language to SQL. If unclear, ask questions. If no data exists, say so clearly.”

### 5️⃣ Attach the Tools  
- Tool 1: Check table schema  
- Tool 2: Run SQL query  
- Add Gemini model and memory  

### 6️⃣ Test  
Try questions like:  
- “Show me last month’s sales.”  
- “Top 5 customers by revenue.”  
- “Orders from Mumbai in 2024.”

---

## 🏁 Final Result  
- Users chat with the database  
- No SQL skills needed  
- AI handles the thinking  
- Accurate answers in seconds  
- Perfect for teams who want instant insights

---

## 🧰 Tools Used  
- n8n  
- Google Gemini  
- PostgreSQL  
- AI Agent + Memory  

---

## 🔗 n8n Workflow Link  
Here is the live workflow link for this project:  
👉 **https://sd210228.app.n8n.cloud/workflow/fVSX47s7vZcuio9e**

---
