# Cold_email_GENERATOR
Cold Email Generator

This project generates personalized cold emails for companies based on job postings. It combines job description analysis, portfolio retrieval, and AI-driven text generation to produce tailored outreach emails.

Project Purpose

Manually creating customized cold emails can be repetitive and time-consuming. This tool automates the process by:

Scraping a job posting from a provided URL.

Extracting structured details such as role, skills, and job description.

Retrieving matching projects from your portfolio.

Using an AI model to generate a personalized email that highlights your relevant experience.

System Workflow
1. Input

The user provides a careers or job posting URL through a Streamlit-based web interface.

2. Job Posting Processing

The application scrapes the content of the page and processes it into structured data such as:

Job title or role

Required skills

Short description of responsibilities

3. Portfolio Matching

The portfolio data (stored in a CSV file) is embedded into a vector database using ChromaDB. When the job posting is processed, relevant portfolio entries are retrieved by comparing the required skills with the stored embeddings.

4. Email Generation

The extracted job details and the retrieved portfolio projects are combined and passed to an AI model. The AI generates a customized cold email draft, which references the portfolio projects and aligns with the job description.

5. Output

The generated email is displayed in the Streamlit app, ready for the user to review, edit if needed, and use.

Key Components

Streamlit Application (main.py)
Provides the user interface where a job posting URL can be entered and results are displayed.

Chains (chains.py)
Defines the logic that connects scraping, extraction, portfolio retrieval, and AI generation into a smooth workflow.

Portfolio Handler (portfolio.py)
Manages portfolio data, stores it in ChromaDB, and retrieves the most relevant projects.

Utilities (utils.py)
Contains supporting functions such as loading environment settings and formatting outputs.

Portfolio Data (my_portfolio.csv)
A simple dataset that includes your past projects. Each entry is described with project details and links.

Application Flow (Step by Step)

User submits a job posting link.

The app loads and cleans the webpage text.

The text is passed through an extraction chain to identify the role, required skills, and a description.

The required skills are used to query ChromaDB for matching portfolio items.

The AI model receives both the job posting details and the retrieved portfolio projects.

A personalized cold email draft is generated.

The email is displayed for user review.
