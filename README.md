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
