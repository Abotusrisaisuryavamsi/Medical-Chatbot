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

---

# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

```
#with specific access

1. EC2 access : It is virtual machine

2. ECR: Elastic Container Registry to save your docker image in AWS


#Description: About the deployment

1. Build docker image of the source code

2. Push your docker image to ECR

3. Launch your EC2 instance

4. Pull your image from ECR in EC2

5. Launch your docker image in EC2


#Policy:

1. AmazonEC2ContainerRegistryFullAccess

2. AmazonEC2FullAccess
```

## 3. Create ECR repo to store/save docker image

* Save the URI:

```text
xxxxxxxxxxxx.dkr.ecr.us-east-1.amazonaws.com/medical-chatbot
```

## 4. Create EC2 machine (Ubuntu)

## 5. Open EC2 and Install docker in EC2 Machine:

```
#optional

sudo apt-get update -y

sudo apt-get upgrade


#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

# 6. Configure EC2 as self-hosted runner:

settings > actions > runners > new self-hosted runner

choose operating system and run the commands one by one

# 7. Setup GitHub Secrets:

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_DEFAULT_REGION
* ECR_REPOSITORY
* PINECONE_API_KEY

# Project Workflow

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
* AWS Deployment Ready
