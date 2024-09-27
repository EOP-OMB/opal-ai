# Policy Document Analysis for NIST 800-53 Compliance (Local Vector Database Version)

This repository contains a series of Jupyter Notebooks designed to analyze IT system environments and policy documentation for compliance with NIST 800-53 security controls. The notebooks the Python `vectordb` library to create and manage a local vector database from policy documents. The notebooks also utilize OpenAI embeddings for document evaluation and CrewAI workflows to assess compliance.

## Overview of Notebooks

1. **Policy_Document_Database_Creation_VectorDB.ipynb**
   - This notebook demonstrates how to initialize a local vector database using the `vectordb` Python library. The documents are segmented into logical sections, embedded using OpenAI's API (or Ollama), and indexed locally for future retrieval.

2. **Evaluate_Controls_With_a_CrewAI_Workflow.ipynb**
   - This notebook introduces a CrewAI workflow to assess a single NIST 800-53 control against policy documents retrieved from the vector database. The AI agent searches for evidence of the control within the documents and generates a structured report based on the findings.

3. **Evaluate_Controls_With_a_CrewAI_Workflow_and_VectorDB.ipynb**
   - This notebook expands on the previous one by evaluating multiple NIST 800-53 security controls across a larger collection of documents. The workflow automates the process of retrieving and analyzing relevant policy sections from the local vector database and outputs an XML report summarizing the findings.

## Prerequisites

Before running the notebooks, ensure the following prerequisites are met:

1. **Python VectorDB Library**
   - Install the Python `vectordb` library, which enables the use of a local vector database to store and manage document embeddings.

   ```bash
   pip install vectordb
   ```

2. **OpenAI API Key or Local Ollama Installation**
   - Obtain an OpenAI API key from [https://platform.openai.com/](https://platform.openai.com/), or install **Ollama** to run OpenAI-compatible embeddings locally. Setup guides are available at [https://ollama.com/](https://ollama.com/).
   - Set the **OPENAI_API_KEY** environment variable if using OpenAI.

3. **Python Environment**
   - Install Jupyter and all required Python libraries by running the following command, which installs the packages listed in `requirements.txt`:

     ```bash
     pip install -r requirements.txt
     ```

## Setting Up Environment Variables

Ensure the following environment variables are set before running the notebooks:

- **OPENAI_API_KEY**: Your OpenAI API key (or use Ollama's setup if applicable).

To set the environment variables, use the following commands in your terminal:

### On Linux/MacOS

```bash
export OPENAI_API_KEY="your-openai-api-key"
```

### On Windows

```bash
set OPENAI_API_KEY="your-openai-api-key"
```

## How to Run

Once all prerequisites are satisfied and environment variables are set, open the Jupyter Notebooks and run the cells in order:

1. **Policy_Document_Database_Creation_VectorDB.ipynb**: Initialize the policy document local vector database.
2. **Evaluate_Controls_With_a_CrewAI_Workflow.ipynb**: Evaluate a single security control using the CrewAI workflow.
3. **Evaluate_Controls_With_a_CrewAI_Workflow_and_VectorDB.ipynb**: Perform analysis on multiple security controls and generate a structured report for each.

## Summary

These notebooks automate the process of analyzing IT policy documents for NIST 800-53 security control compliance. By using a local vector database with the `vectordb` library, the solution offers flexibility for environments where cloud services like Pinecone are not feasible. The combination of OpenAI embeddings and CrewAI workflows provides an efficient, scalable approach to continuously assess compliance with NIST standards.

