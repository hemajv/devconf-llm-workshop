---
title: Exercises
nav: true
---

# Exercises

Here are some exercises you can now try and explore by yourself!


1. **Try uploading other types of documentation** - Upload other documentation to the RAG application you just deployed and try asking questions specific to its content to see if the model was able to generate answers from it
2. **Experimenting with input prompts** - Try different types of prompt that you provide as an input to your LLM application
3. **Try different vector databases** - We have used Chromadb as the vector database in this workshop for the RAG recipe/application, but you can also explore other vector databases such as Milvus
4. **Try different embedding models** - In this workshop, we are using the `BAAI/bge-base-en-v1.5` as the embedding model for the RAG recipe/application, but you can experiment with other embedding models and try updating it [here](https://github.com/containers/ai-lab-recipes/blob/main/recipes/natural_language_processing/rag/app/rag_app.py#L17C48-L17C69)
5. **Try different LLM** - In this workshop, we are using the `granite-7b-lab` model as our choice of LLM: [https://huggingface.co/instructlab/granite-7b-lab-GGUF](https://huggingface.co/instructlab/granite-7b-lab-GGUF), but you can try other smaller models from HuggingFace instead such as `mistral-7b-instruct`: [https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF) or any other model of your choice and compare the results you get.
6. **Try other AI Labs recipes** - In this workshop, we tried a RAG recipe, but you can try other recipes that are available here: [https://github.com/containers/ai-lab-recipes/tree/main/recipes](https://github.com/containers/ai-lab-recipes/tree/main/recipes)
