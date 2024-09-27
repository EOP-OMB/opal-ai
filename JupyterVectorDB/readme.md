
# Policy Document Analysis for NIST 800-53 Compliance

This repository contains a series of Jupyter Notebooks designed to analyze IT system environments and policy documentation for compliance with NIST 800-53 security controls. The notebooks leverage Pinecone for vector storage and OpenAI's embeddings to evaluate policy documents against specific security controls using AI-powered workflows.

## Overview of Notebooks

1. **Policy_Document_Database_Creation.ipynb**
   - This notebook demonstrates how to initialize a vector database (Pinecone) for storing and organizing a collection of policy documents. The documents are segmented into logical sections, embedded using OpenAI's API, and indexed in Pinecone for future retrieval.
  
2. **Evaluate_Controls_With_a_CrewAI_Workflow.ipynb**
   - This notebook introduces a CrewAI workflow to assess a single NIST 800-53 control against policy documents retrieved from the vector database. The AI agent searches for evidence of the control within the documents and generates a structured report based on the findings.
  
3. **Evaluate_Controls_With_a_CrewAI_Workflow_and_Pinecone.ipynb**
   - This notebook expands on the previous one by evaluating multiple NIST 800-53 security controls across a larger collection of documents. The workflow automates the process of retrieving and analyzing policy sections relevant to each control and outputs an XML report summarizing the findings.

## Prerequisites

Before running the notebooks, make sure the following prerequisites are met:

1. **Pinecone Account**
   - Create a free Pinecone account at [https://www.pinecone.io/](https://www.pinecone.io/).
   - Set up the **PINECONE_API_KEY** for use in the notebooks.

2. **OpenAI API Key or Local Ollama Installation**
   - Obtain an OpenAI API key from [https://platform.openai.com/](https://platform.openai.com/).
   - Alternatively, you can use **Ollama**, a local installation that is OpenAI-compatible. Follow the setup guide available at [https://ollama.com/](https://ollama.com/).
   - Set the **OPENAI_API_KEY** environment variable if using OpenAI.

3. **Python Environment**
   - Install Jupyter and all required Python libraries by running the command below, which installs the packages listed in `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

## Setting Up Environment Variables

Ensure the following environment variables are set before running the notebooks:

- **PINECONE_API_KEY**: Your Pinecone API key.
- **OPENAI_API_KEY**: Your OpenAI API key (or use Ollama's setup if applicable).

To set the environment variables, use the following commands in your terminal:

### On Linux/MacOS

```bash
export PINECONE_API_KEY="your-pinecone-api-key"
export OPENAI_API_KEY="your-openai-api-key"
```

### On Windows

```bash
set PINECONE_API_KEY="your-pinecone-api-key"
set OPENAI_API_KEY="your-openai-api-key"
```

## How to Run

Once all prerequisites are satisfied and environment variables are set, open the Jupyter Notebooks and run the cells in order:

1. **Policy_Document_Database_Creation.ipynb**: Initialize the policy document vector database.
2. **Evaluate_Controls_With_a_CrewAI_Workflow.ipynb**: Evaluate a single security control using the CrewAI workflow.
3. **Evaluate_Controls_With_a_CrewAI_Workflow_and_Pinecone.ipynb**: Perform analysis on multiple security controls and generate a structured report for each.

## Summary

These notebooks automate the process of analyzing IT policy documents for NIST 800-53 security control compliance. The combination of Pinecone and OpenAI embeddings allows for efficient retrieval and evaluation of relevant document sections, while CrewAI's multi-agent workflow handles the assessment of security controls. This project provides a scalable solution for organizations needing to continuously assess their compliance with NIST standards.

