---
title: Guide
nav: true
---

# Workshop Guide

You can now follow these steps as we walk through the workshop. As mentioned in the `Intro` section, we will be setting up and experimenting with a RAG application using the ai-lab-recipe repository.

## Step 1: Clone the repository

Start by cloning the repository that contains the RAG application code. This repository hosts a variety of AI-related recipes, including the one for RAG.

`git clone https://github.com/containers/ai-lab-recipes.git`


## Step 2: Navigate to the RAG Application Directory

Once cloned, navigate to the specific directory for the RAG application. This directory contains all the necessary code and resources for setting up the RAG system.

`cd ai-lab-recipes/recipes/natural_language_processing/rag/app`

## Step 3: Install Requirements

We will need to install all the packages, libraries and dependencies required to run the RAG application. These are defined in the `requirements.txt` file.

Let's first start a Python virtual env and install the dependencies within this virtual env.

```python
python3 -m venv venv
source ./venv/bin/activate
```

Now, lets install all the packages:

`pip install -r requirements.txt`

## Step 4: Download Model

For this workshop, we recommend using the `granite-7b` lab model. It’s a well performing open sourced mid-sized model licensed under Apache-2.0 and served in the GGUF format.

Navigate to the models directory and download the recommended model as follows:

```python
cd ../../../../models 
curl -sLO https://huggingface.co/instructlab/granite-7b-lab-GGUF/resolve/main/granite-7b-lab-Q4_K_M.gguf
```

This step will take a couple of minutes. After downloading, you will see the model in your directory, ready to be used in the RAG setup.

## Step 5:  Deploy the Vector Database

A vector database is essential for the retrieval part of the RAG application. It stores vector representations of documents that can be quickly searched.

We will use Chromadb for this workshop. To deploy the Vector database service locally, simply use the Chromadb image. The vector database is ephemeral and will need to be re-populated each time the container restarts.

In order to deploy, you can run the following:

```python
cd ../recipes/natural_language_processing/rag/app
podman pull chromadb/chroma 
podman run --rm -it -p 8000:8000 chroma 
```

Ensure the vector database is running and note the live endpoint. This will be used to store and retrieve document vectors.

## Step 6: Start the Model Service

In order to deploy the model service, first, open a new terminal (make sure the chromadb is still running) and navigate to the ai-labs-recipe repository that you have cloned.
The model service is responsible for processing and generating text based on inputs and retrieved documents. We will use the llamacpp_python model service for this. Navigate to the model service directory:

`cd ai-lab-recipes/model_servers/llamacpp_python`

Build the model service

```python
podman build -t llamacppserver -f ./base/Containerfile .
```

Deploy the model service

```python
podman run --rm -it \
        -p 8001:8001 \
        -v /<your path>/ai-lab-recipes/models:/ai-lab-recipes/models:ro,Z \
        -e MODEL_PATH=/ai-lab-recipes/models/granite-7b-lab-Q4_K_M.gguf \
        -e HOST=0.0.0.0 \
        -e PORT=8001 \
        llamacppserver

```

**OR**

If you are unable to download the model GGUF file due to **SLOW INTERNET**, we have some services running which you can interact with instead. To do this, replace the `rag_app.py` line [here](https://github.com/containers/ai-lab-recipes/blob/main/recipes/natural_language_processing/rag/app/rag_app.py#L13) as follows:

```python
model_service = os.getenv("MODEL_ENDPOINT","https://tinyurl.com/devconf-model")
```

```python
model_service = os.getenv("MODEL_ENDPOINT","https://tinyurl.com/devconf-model2")
```

## Step 7: Start the Streamlit app

Now, open a new terminal window to run the Streamlit UI application. Here we will run the Streamlit application that ties everything together. This app provides the user interface to interact with the RAG system.

In a new terminal, navigate back to RAG app directory:

`cd ai-lab-recipes/recipes/natural_language_processing/rag/app`

Run the Streamlit app:

`streamlit run rag_app.py`

**_Note_**: If you run into `AxiosError: Request failed with status code 403`, try doing the following:

- Create a new folder `.streamlit` inside the `/app` directory
- Create a `config.toml` file and add the following lines to it:
  ```python
  [server]
  enableXsrfProtection = false
  enableCORS = false
  ```

Once the application is running, you can upload your choice of documents and start asking questions related to them. The RAG system will use the uploaded documents to provide more accurate and contextually relevant answers.

#### Congrats!! You have now successfully setup a LLM RAG application locally on your laptop using containerization techniques 🥳
#### Give yourself a pat on the back!! 👏












