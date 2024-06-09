# Locally talk to markdown documents

Easily chat with your markdown files using a local AI model such as `llama3,
mistral` or others. System will generate embeddings and use `surrealDB` to store
them. 

FastAPI exposes and endpoint to query the model and _chat with your own docs_
without needing to use paid models.

## Prerequisites

| Project/Tool                                     | Description                                                             |
|--------------------------------------------------|-------------------------------------------------------------------------|
| [Ollama](https://ollama.com/)                    | A platform for creating, sharing, and running machine learning models.  |
| [Langchain](https://www.langchain.com/)          | A framework for developing applications powered by language models.     |
| [SurrealDB](https://surrealdb.com/)              | A scalable, distributed, document-graph database.                       |
| [FastAPI](https://fastapi.tiangolo.com/)         | A modern, fast web framework for building APIs with Python 3.6+.        |
| [Just](https://github.com/casey/just)        | A handy way to save and run project-specific commands.                 |

## Run locally

Once all the prerequisites are installed, use the `just` commands to:
- `just setup` will create a python virtual environment, install required
packages and check if all the prerequisites are correctly installed
- `just embed [./path/to/docs]` will create embeddings from the docs
- `just run [model]` will start SurrealDB, expose the API on the `8282` port and
run the server. Default model is `llama3` but you can change it to any locally
installed `ollama` model 
- `just chat [question]` will send the query to model and generate a response

