# TCS Annual Report RAG Chatbot using Python, LangChain, FAISS, HuggingFace, and Ollama.

## Project Workflow / Steps
### Step 1 — Import Required Libraries

 Imported the required Python libraries for PDF loading, text splitting, embeddings, and vector storage.

#### Main libraries used:

PyPDFLoader
RecursiveCharacterTextSplitter
HuggingFaceEmbeddings
FAISS

### Step 2 — Load the PDF

Loaded the TCS Annual Report PDF using PyPDFLoader.

The PDF is converted into LangChain documents so that the content can be processed programmatically.

### Step 3 — Split the Document into Chunks

The large PDF document is divided into smaller text chunks using RecursiveCharacterTextSplitter.

chunk_size = 2500
chunk_overlap = 500

Chunking helps the system process and retrieve relevant information efficiently.

### Step 4 — Generate Embeddings
Converted the text chunks into numerical vector representations using HuggingFace Sentence Transformers.

These embeddings capture the semantic meaning of the text.

### Step 5 — Create FAISS Vector Store

Stored the document embeddings in a FAISS vector database.

FAISS is used to efficiently search for documents that are semantically similar to a user's question.

### Step 6 — Perform Similarity Search

When a user asks a question, FAISS searches the vector database and retrieves the most relevant chunks.

results = vector_store.similarity_search(question, k=3)

Here, k=3 retrieves the top three relevant chunks.

### Step 7 — Build the Context

The retrieved chunks are combined to create a context for the Large Language Model (LLM).

Only the relevant information retrieved from the PDF is passed to the prompt.

### Step 8 — Create the RAG Prompt

Created a prompt that instructs the LLM to answer the question using the retrieved context.

The model is instructed not to use outside knowledge when answering the question.

### Step 9 — Generate the Final Answer using Ollama

Connected the RAG pipeline to a local LLM using Ollama.

The retrieved context and user question are sent to the local Llama model, which generates the final answer.

#### This approach allows the project to run locally without requiring an OpenAI API key.

##### RAG Architecture

TCS Annual Report PDF
        ↓    
    PyPDFLoader
    
        ↓
   Text Chunking
   
        ↓ 
HuggingFace Embeddings

        ↓
   FAISS Vector Store
   
        ↓
  Similarity Search
  
        ↓
 Relevant Context
 
        ↓
    RAG Prompt
    
        ↓
   Ollama LLM
   
        ↓
    Final Answer

#### Technologies Used:
Python
Jupyter Notebook
LangChain
PyPDF
HuggingFace Sentence Transformers
FAISS
Ollama
Llama 3.2
Key Features
PDF document question answering
Retrieval-Augmented Generation (RAG)
Semantic similarity search
Vector database using FAISS
HuggingFace embeddings
Local LLM using Ollama

No OpenAI API key required for final response generation
Project Outcome:

The completed system can retrieve relevant information from the TCS Annual Report and generate context-based answers to user questions using a local LLM.
