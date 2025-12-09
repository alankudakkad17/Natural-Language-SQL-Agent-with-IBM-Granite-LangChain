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

## ⚙️ Setup & Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/watsonx-sql-agent.git](https://github.com/your-username/watsonx-sql-agent.git)
    cd watsonx-sql-agent
    ```

2.  **Install dependencies:**
    *(Based on imports in the scripts)*
    ```bash
    pip install langchain langchain-community ibm-watsonx-ai ibm-watson-machine-learning mysql-connector-python
    ```

3.  **Configuration:**
    Open `sql_agent.py` and `llm_agent.py` to update your IBM Cloud and Database credentials:

    ```python
    # In both files
    credentials = {
        "url": "[https://us-south.ml.cloud.ibm.com](https://us-south.ml.cloud.ibm.com)",
        "apikey": "YOUR_IBM_CLOUD_API_KEY" # Ensure authentication is handled
    }
    project_id = "YOUR_PROJECT_ID"
    
    # In sql_agent.py
    mysql_username = 'root'
    mysql_password = 'YOUR_PASSWORD' 
    mysql_host = 'YOUR_HOST_IP'
    ```

## 💻 Usage

### 1. Run the Basic LLM
To test the connection to Watsonx and ask general knowledge questions:
```bash
python llm_agent.py
