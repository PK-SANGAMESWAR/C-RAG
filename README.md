# C-RAG: Corrective Retrieval Augmented Generation

This project implements a Corrective Retrieval Augmented Generation (CRAG) system using LangChain, LangGraph, and Ollama. It demonstrates how to enhance RAG systems by evaluating retrieved documents and falling back to web search when necessary.

## Project Structure

- **`basic_rag.ipynb`**: A standard RAG implementation using local documents and vector search.
- **`knowledge_refinement.ipynb`**: Demonstrates how to refine retrieved context by filtering irrelevant sentences.
- **`FullCRAG.ipynb`**: The complete Corrective RAG system that integrates document evaluation, query rewriting, web search fallback, and answer generation.
- **`documents/`**: Directory containing source PDF documents for RAG.

## Features

- **Document Loading**: Loads PDF documents from the `documents/` directory.
- **Vector Search**: Uses FAISS and Ollama embeddings for efficient similarity search.
- **Self-Reflective RAG**: Evaluates the relevance of retrieved documents.
- **Web Search Fallback**: Automatically rewrites queries and searches the web using Tavily if retrieved documents are insufficient.
- **Knowledge Refinement**: Filters context to keep only relevant information before generating an answer.
- **Graph-Based Workflow**: Uses LangGraph to manage the control flow of the RAG pipeline.

## Prerequisites

1.  **Python 3.12+**: Ensure you have a compatible Python version installed.
2.  **Ollama**: You need to have Ollama installed and running.
    - Pull the necessary models:
      ```bash
      ollama pull qwen2.5:7b-instruct
      ollama pull mxbai-embed-large
      ```
3.  **Tavily API Key**: Get an API key from [Tavily](https://tavily.com/) for web search capabilities.

## Installation

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd C-RAG
    ```

2.  **Create a virtual environment**:
    ```bash
    python -m venv .venv
    # Windows
    .venv\Scripts\activate
    # macOS/Linux
    source .venv/bin/activate
    ```

3.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set up environment variables**:
    - Create a `.env` file in the root directory.
    - Add your Tavily API key:
      ```env
      TAVILY_API_KEY=your_tavily_api_key_here
      ```

## Usage

1.  **Prepare Documents**: Place your PDF documents in the `documents/` folder.
2.  **Run Notebooks**: Open the Jupyter notebooks to explore the different RAG implementations.
    - Start with `basic_rag.ipynb` to understand the basics.
    - Move to `knowledge_refinement.ipynb` to see how context is cleaned.
    - Finally, run `FullCRAG.ipynb` for the complete corrective RAG workflow.

## License

[Add License Information Here]
