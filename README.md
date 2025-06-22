# Capstone Project: LLM Applications with Langchain and Data Analysis

## Project Overview
This project demonstrates the application of Large Language Models (LLMs) for natural language processing tasks and their integration with data analysis tools. The core of the project involves using the `langchain` library to interact with an LLM hosted on Replicate, performing tasks such as text classification, information extraction, and natural language querying of Pandas DataFrames.

## Raw Dataset
The project utilizes a dataset loaded from `Archive1.zip`. This CSV file contains various movie-related information including Title, Year, Director, Duration, Rating, Votes, Description, Language, Country, Budget_USD, BoxOffice_USD, Genre, Production_Company, Content_Rating, Lead_Actor, Num_Awards, and Critic_Reviews.

## Insights & Findings
The notebook demonstrates several key insights into the capabilities of LLMs and their integration with data analysis:

* **Text Classification**: The LLM can effectively classify customer reviews into sentiment categories (Positive, Negative, Mixed) based on the provided text. For instance, "Kamera ponsel ini luar biasa, fotonya sangat jernih bahkan dalam kondisi kurang cahaya." is classified as "Positive".
* **Information Extraction**: The LLM is capable of extracting specific entities like name, age, and job from unstructured biographical text and formatting them into structured JSON objects. Examples include extracting details for "JessNoLimit", "Windah Basudara", and "MiawAug".
* **Natural Language Interaction with DataFrames**: The `create_pandas_dataframe_agent` allows users to query and visualize data within a Pandas DataFrame using natural language prompts. This significantly lowers the barrier for non-programmers to interact with data.
* **LLM Debugging and Self-Correction**: The Pandas agent demonstrates the ability to identify missing imports (like `matplotlib.pyplot`) and correct its own code to successfully execute a plotting command.
* **Handling Empty Data**: When attempting to plot ratings for a year like 2015, for which no data exists in the provided snippet, the agent correctly identifies that the plot will show no bars, indicating zero ratings for that year.

## AI Support Explanation
The core AI support in this project is provided by the `ibm-granite/granite-3.3-8b-instruct` Large Language Model, accessed via the Replicate platform. This LLM is utilized through the `langchain_community.llms.Replicate` class.

The AI assists in the following ways:

* **Natural Language Understanding (NLU)**: The LLM processes human-like text inputs (e.g., customer reviews, biographical descriptions, data analysis queries).
* **Natural Language Generation (NLG)**: The LLM generates human-readable responses, including classification labels, structured JSON data, and explanations of its actions or findings.
* **Problem-Solving (Agentic Behavior)**: The `pandas_dataframe_agent` exemplifies agentic behavior where the LLM, in conjunction with tools (Python REPL), plans and executes steps to achieve a user's goal, such as generating a plot from a DataFrame. It can also perform self-correction by identifying and fixing errors in its generated code.
