# Crops_AI: AI-Powered Agricultural Optimization

🌾🌾🌾

## Objective

This project features an AI assistant designed to help farmers make informed decisions about crop selection. By analyzing farmer profile data and market research data stored in a database, the AI utilizes generative models and database tools to recommend optimal crops based on various factors like soil conditions, farmer preferences, and market trends.

This notebook was developed as part of the Gen AI Intensive Course Capstone 2025Q1.

## Problem Statement

Farmers often face challenges in selecting the most suitable crops due to numerous influencing factors. This project demonstrates how Generative AI, specifically a large language model equipped with database interaction capabilities, can process relevant data to provide tailored recommendations, aiming to optimize agricultural outcomes.

## Features & Capabilities

* **Generative AI Model:** Leverages a large language model for analysis and recommendation generation.
* **Database Interaction:** Uses custom tools (`list_tables`, `describe_table`, `execute_query`) to interact with an SQLite database containing farmer and market data.
* **Function Calling:** The AI model intelligently calls predefined Python functions to fetch and process data from the database.
* **Context Awareness:** Maintains conversation history to provide relevant responses across multiple turns.
* **Agent Behavior:** Acts as an intelligent agent, interpreting user needs, deciding which tools to use, and synthesizing information to provide crop recommendations.

## How it Works

The AI assistant follows these steps:

1.  **Inspect Tables:** Uses `list_tables()` and `describe_table()` to understand the database schema (`farmer_profiles` and `market_data` tables).
2.  **Ask Clarifying Questions:** Gathers necessary information from the user based on the available data columns (e.g., Soil_pH, Soil_Moisture, Temperature_C, Rainfall_mm).
3.  **Formulate Queries:** Constructs SQL SELECT queries using `execute_query()` based on user input and schema knowledge to filter relevant market and farmer data.
4.  **Synthesize Recommendation:** Analyzes query results and presents the top crop choices, explaining the rationale based on the data (e.g., market demand, suitability to farm conditions).

## Implementation Details

The core implementation involves:

* Setting up the environment and installing necessary libraries (`google-genai`, `pandas`, `sqlite3`).
* Initializing an SQLite database (`agriculture_optimization.db`) from CSV files (`farmer_advisor_dataset.csv`, `market_researcher_dataset.csv`).
* Defining Python functions (`list_tables`, `describe_table`, `execute_query`) as tools for database interaction.
* Configuring the Generative AI model (`gemini-2.0-flash`) with system instructions and the defined tools.
* Simulating a chat interaction where the AI uses the tools to guide the user and provide recommendations.

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd Crops_AI
    ```
2.  **Install dependencies:**
    ```bash
    pip install -U google-genai pandas
    ```
3.  **Obtain Datasets:** Download `farmer_advisor_dataset.csv` and `market_researcher_dataset.csv`. Place them in an accessible path (e.g., an `input/` directory). Update the paths in the notebook if necessary.
4.  **Set up Google API Key:** Obtain a Google API key and configure it for the `google-genai` library. The notebook demonstrates using Kaggle Secrets, but you can adapt it for your environment.

## Usage

Run the Jupyter Notebook `ai-powered-agricultural-optimization.ipynb`. The notebook guides through:

1.  Environment setup and data loading.
2.  Database tool definition and testing.
3.  AI assistant configuration.
4.  A simulated conversation demonstrating the AI's process of asking questions, querying the database, and providing crop recommendations based on user input and data analysis.

## Resources

* **Video Explanation:** [YouTube Link](https://www.youtube.com/watch?v=ruBfTk3kz8E)
* **Blog Post:** [Medium Article](https://medium.com/@diwakarsehgal02/gen-ai-intensive-course-capstone-2025q1-c2cff0e65736)
* **Kaggle Notebook:** [AI-Powered Agricultural Optimization](https://www.kaggle.com/code/diwakarsehgal/ai-powered-agricultural-optimization/notebook#Tool-Definition-and-Testing)

## Author

* **Team:** Solis
* **Developer:** Diwakar Sehgal

## References

References for concepts and tools used in this project are detailed within the Jupyter Notebook.
