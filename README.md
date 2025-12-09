# Natural-Language-SQL-Agent-with-IBM-Granite-LangChain

# Watsonx LangChain SQL Agent 🧠🗄️

This project demonstrates how to build an intelligent **Text-to-SQL** agent using **IBM Watsonx.ai**, **LangChain**, and **IBM Granite models**. It features two implementations: a basic LLM inference script and a complex agent capable of querying a MySQL database using natural language.

## 🚀 Features

* **Natural Language to SQL:** Automatically converts English questions (e.g., "How many albums are there?") into valid SQL queries.
* **Agentic Reasoning:** Uses LangChain's `ZERO_SHOT_REACT_DESCRIPTION` agent type to analyze database schemas and handle parsing errors.
* **IBM Granite Integration:** Leverages the `ibm/granite-3-2-8b-instruct` foundation model for high-performance instruction following.
* **Custom Parameters:** Demonstrates different model configurations (temperature, token limits) for creative vs. analytical tasks.

## 🛠️ Tech Stack

* **Python 3.x**
* **[LangChain](https://www.langchain.com/):** For agent orchestration and database tools.
* **[IBM Watsonx.ai](https://www.ibm.com/products/watsonx-ai):** Hosting the Foundation Model.
* **MySQL:** Using the sample "Chinook" database.

## 📂 Project Structure

* `llm_agent.py`: A basic implementation enabling direct Q&A with the Granite model. It uses a higher temperature (0.5) for more creative responses.
* `sql_agent.py`: An advanced agent that connects to a MySQL database, inspects tables, and executes queries. It uses a lower temperature (0.2) for precise, deterministic SQL generation.
