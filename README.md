# Medical-Chatbot

## How to Run the Project

### STEP 01: Clone the Repository

```bash
git clone https://github.com/entbappy/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS.git
```

---

### STEP 02: Create a Conda Environment

```bash
conda create -n medibot python=3.10 -y
```

---

### STEP 03: Activate the Conda Environment

```bash
conda activate medibot
```

---

### STEP 04: Install the Required Packages

```bash
pip install -r requirements.txt
```


### Create a `.env` file in the root directory and add your Pinecone credentials as follows:

```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

```bash
# run the following command to store embeddings to pinecone
python -m src.store_index
```

```bash
# Start Ollama Llama3 model
ollama run llama3
```

Keep the Ollama terminal running.

```bash
# Finally run the following command
python app.py
```

Now,

```bash
open up localhost:
http://127.0.0.1:8080
```

---

### Techstack Used:

* Python
* LangChain
* Flask
* Ollama
* Llama3
* Pinecone
* HuggingFace Embeddings


```text
PDF Documents
      ↓
Text Chunking
      ↓
HuggingFace Embeddings
      ↓
Pinecone Vector Database
      ↓
Retriever
      ↓
Ollama (Llama3)
      ↓
Medical AI Response
```

# Features

* Medical Question Answering
* Retrieval-Augmented Generation (RAG)
* Pinecone Vector Search
* Local LLM Inference using Llama3
* PDF-based Knowledge Retrieval
* Flask Web Interface
