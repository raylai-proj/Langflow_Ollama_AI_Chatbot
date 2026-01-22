# Langflow_Ollama_AI_Chatbot
This is a self implementation to understand frame of AI chatbot using Langflow and Ollama<br >
## Ollama
In this repo, I utilized Ollama, which is an open source tool, to allowed me run LLM (Large Language Model) locally.<sub>[1]</sub> Ollama provides multiple models in library for the user to easily download for direct use and can fine tune to certain field specialized models.<sub>[2]</sub><br >
### Models
In this repo, I used following LLMs to build the AI chatbot.<br >
- llama3.2:1b: <br >
llama 3.2:1b is a lightweight version of the Llama 3.2 family, designed to help users build customized agentic applications locally. By running applications locally, it ensures superior privacy since data remains on the device and is never shared with the cloud. Additionally, as a text-only model specializing in multilingual text generation, it allows for easy personalization without language barriers.<sub>[3]</sub><br >
- nomic-embed-text:latest: <br >
nomic-embed-text model is a popular open-source model featuring an 8192-token context length. It outperforms OpenAI’s text-embedding-ada-002 and text-embedding-3-small in both short and long-context tasks. As a vital component for NLP applications, it enables LLMs to perform Retrieval-Augmented Generation (RAG). In our implementation, we used the model to convert uploaded files into numerical vectors, allowing the database to perform high-speed semantic searches. This ensures the system can quickly retrieve the most relevant context to answer a user's query.<sub>[4][5]</sub><br >
## Langflow
### UV
### Structure
## Reference
[1] [ollama](https://github.com/ollama/ollama)<br >
[2] [ollama.com](https://ollama.com/)<br >
[3] [Llama 3.2: Revolutionizing edge AI and vision with open, customizable models](https://ai.meta.com/blog/llama-3-2-connect-2024-vision-edge-mobile-devices/)<br >
[4] [Introducing Nomic Embed: A Truly Open Embedding Model](https://www.nomic.ai/news/nomic-embed-text-v1)<br >
[5] [Build AI Chatbots (with RAG) for FREE using Langflow and Ollama (Run Models Locally)](https://www.youtube.com/watch?v=tVwdpQyjtOc&list=LL&index=11)<br >

