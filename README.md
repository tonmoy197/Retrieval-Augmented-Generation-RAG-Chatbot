
# Generative Q&A

A project leveraging [Pinecone](https://docs.pinecone.io/docs/overview), [LangChain](https://langchain-langchain.vercel.app/), and [OpenAI](https://platform.openai.com/overview) to build a Generative Q&A system using [Retrieval Augmented Generation (RAG)](https://ai.facebook.com/blog/retrieval-augmented-generation-streamlining-the-creation-of-intelligent-natural-language-processing-models/).

## Overview

This project implements a Retrieval-Augmented Generation (RAG) system for answering questions by combining vector-based retrieval with generative AI. The process involves two main steps:

1. **Setup the Knowledge Base in Pinecone**
   - Chunk the content into manageable pieces.
   - Create vector embeddings from the chunks.
   - Load embeddings into a Pinecone index for efficient retrieval.

2. **Question Answering**
   - Generate a vector embedding for the input question.
   - Retrieve relevant context from the Pinecone index by finding embeddings similar to the question.
   - Use OpenAI's API to generate an answer, augmented with the retrieved context.


## Setup

### 1. Install Dependencies

Install the required Python packages using the provided requirements file:

```bash
pip install -r ./setup/requirements.txt
```

### 2. Configure API Keys

Set up environment variables for Pinecone and OpenAI API keys:

```bash
cp dotenv .env
vi .env
```

Edit the `.env` file to include your Pinecone and OpenAI API keys.

### 3. Load Data into Pinecone

Use the provided Jupyter notebooks to:
- Load data into the Pinecone index.
- Run sample queries to test the setup.


## Q&A App (Streamlit)

### Install Dependencies

Ensure all dependencies for the Streamlit app are installed.  


### Run the App

Launch the Streamlit application:

```bash
streamlit run streamlit-app.py
```



## Background

This project is inspired by the Retrieval-Augmented Generation (RAG) framework introduced in:  
Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., … Kiela, D. (2020). Retrieval-Augmented Generation for Knowledgeunion Knowledge-Intensive NLP Tasks. In H. Larochelle, M. Ranzato, R. Hadsell, M. F. Balcan, & H. Lin (Eds.), **Advances in Neural Information Processing Systems** (Vol. 33, pp. 9459–9474). Retrieved from [NeurIPS Proceedings](https://proceedings.neurips.cc/paper_files/paper/2020/file/6b493230205f780e1bc26945df7481e5-Paper.pdf).
