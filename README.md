# Experimental Platform for Local AI Models

This project is an innovative platform designed to explore the potential of running locally hosted AI models for answering questions based on document embeddings. With support for Retrieval-Augmented Generation (RAG), it provides a hands-on environment to test various tools, frameworks, and techniques for working with document-based AI tasks.

A web-based interface built using [Streamlit](https://streamlit.io/) complements the command-line tool, offering an intuitive way to interact with the system.

---

## Features

- **Local Model Hosting:** Utilize locally hosted large language models for quick and secure processing.
- **Document Embedding:** Convert PDFs and Markdown files into vector embeddings using Ollama.
- **Customizable Models:** Supports multiple LLMs and embedding frameworks.
- **Interactive Web UI:** Streamlit-powered interface for easy interaction with the system.
- **Extensible Design:** Built to be a flexible testing ground for new ideas and tools.

---

## Prerequisites

- **Ollama**: Version 0.1.26 or higher for hosting and embedding models locally.
- **Python**: Version 3.8 or later.
- **Pip**: Installed for managing Python packages.

---

## Setup Instructions

### Step 1: Clone the Repository

Begin by cloning the project repository to your local machine:

```bash
git clone <repository_url>
cd <repository_directory>
```

### Step 2: Create a Virtual Environment

Set up an isolated environment to manage dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate   # For Unix/MacOS
.\.venv\Scripts\activate  # For Windows
```

### Step 3: Install Dependencies

Install the required Python packages:

```bash
pip install -r requirements.txt
```

---

## Running the Application

### Command-Line Interface

1. Activate the virtual environment:

   ```bash
   source .venv/bin/activate   # For Unix/MacOS
   .\.venv\Scripts\activate  # For Windows
   ```

2. Execute the main script:

   ```bash
   python app.py -m <model_name> -p <path_to_documents>
   ```

   - **Model:** Specify the LLM to use. Defaults to [Mistral](https://ollama.com/library/mistral) if not specified.
   - **Document Path:** Specify the directory containing PDFs or Markdown files. Defaults to a sample `Research` folder in the repository if not provided.
   - **Embedding Model:** Optionally specify an embedding model with `-e <embedding_model_name>`. Defaults to [nomic-embed-text](https://ollama.com/library/nomic-embed-text).

3. Once executed, the application processes documents, generates embeddings, and queries the collection to answer predefined or user-defined questions.

### Example Command

```bash
python app.py -m mistral -p ./documents -e nomic-embed-text
```

---

## Running the Web Interface

1. Activate the virtual environment:

   ```bash
   source .venv/bin/activate   # For Unix/MacOS
   .\.venv\Scripts\activate  # For Windows
   ```

2. Launch the Streamlit application:

   ```bash
   streamlit run ui.py
   ```

3. This starts a local web server and opens the Streamlit UI in your default browser. Use the interface to:
   - Select a model and embedding technique.
   - Upload or select document directories.
   - Query the system interactively.



---

## System Workflow

1. **Document Loading**:
   - PDFs and Markdown files are loaded from the specified directory.
   - The system ensures that all relevant files are processed.

2. **Embedding Creation**:
   - Embeddings are generated using the chosen embedding model.
   - These embeddings are stored temporarily for querying.

3. **Query Processing**:
   - User queries are matched against the embeddings to retrieve relevant information.
   - Responses are generated using the selected LLM.

4. **Result Presentation**:
   - Results are displayed either in the terminal (CLI) or the Streamlit interface (Web UI).

---

## Key Technologies

- **[LangChain](https://github.com/langchain/langchain):** Framework for building applications powered by LLMs.
- **[Ollama](https://ollama.ai/):** For hosting and embedding AI models locally.
- **[Chroma](https://docs.trychroma.com/):** Vector database for managing and querying embeddings.
- **[PyPDF2](https://pypi.org/project/PyPDF2/):** Library for parsing and processing PDF files.
- **[Streamlit](https://streamlit.io/):** Framework for building interactive web applications.

---

## Future Work

- **Persistent Embeddings:** Implement a mechanism to store embeddings between sessions.
- **Enhanced Model Support:** Add compatibility with more LLMs and embedding techniques.
- **Scalability Improvements:** Optimize the workflow for larger datasets and concurrent queries.
- - **Reloading Embeddings:** Embeddings are reloaded each time the application starts. This is for simplicity in testing but can be optimized.




