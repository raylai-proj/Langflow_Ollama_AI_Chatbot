# Langflow_Ollama_AI_Chatbot
This is a self implementation to understand frame of AI chatbot using Langflow and Ollama<br >
## Ollama
In this repo, I utilized __Ollama__, which is an open source tool, to allowed me run LLM (Large Language Model) locally.<sub>[1]</sub> __Ollama__ provides multiple models in library for the user to easily download for direct use and can fine tune to certain field specialized models.<sub>[2]</sub><br >
### Models
In this repo, I used following LLMs to build the AI chatbot.<br >
- __llama3.2:1b__: <br >
__llama 3.2:1b__ is a lightweight version of the __Llama 3.2__ family, designed to help users build customized agentic applications locally. By running applications locally, it ensures superior privacy since data remains on the device and is never shared with the cloud. Additionally, as a text-only model specializing in multilingual text generation, it allows for easy personalization without language barriers.<sub>[3]</sub><br >
- __nomic-embed-text:latest__: <br >
__nomic-embed-text__ model is a popular open-source model featuring an 8192-token context length. It outperforms OpenAI’s text-embedding-ada-002 and text-embedding-3-small in both short and long-context tasks. As a vital component for NLP applications, it enables LLMs to perform Retrieval-Augmented Generation (RAG). In our implementation, we used the model to convert uploaded files into numerical vectors, allowing the database to perform high-speed semantic searches. This ensures the system can quickly retrieve the most relevant context to answer a user's query.<sub>[4][5]</sub><br >
## Langflow<br >
__Langflow__ is a visual IDE that supports major LLMs and customized AI models, enabling the development of AI agents through a low-code or no-code approach. It provides a built-in API alongside its visual interface, allowing us to seamlessly build, deploy, and manage agent workflows. Because every component is integrated into a modular toolbox, it offers a clear structural overview of the AI agent's logic. This let us to design customized agents via a drag-and-drop interface and immediately refine or validate them using the integrated testing playground. In this repo, we use __Langflow__ to build a medical AI agent specializing in the treatment of Plantar fasciitis. We have collected and uploaded relevant medical data so the agent can recommend treatments and provide guidance to help users improve their condition and recover more effectively.<sub>[6][7][8][9]</sub><br>
### UV<br >
__UV__ is a python package manager like `pip` and `poetry`, but it performs outstanding speed in installing Langflow and is compatible with `pip` which makes it great for beginners who can practice using __UV__; in the mean time, they can switch back to `pip` whenever they want.<sub>[6][10]</sub><br >
### Structure<br >
- AI model:<br >
The AI model is the heart of any chatbot, governing how the system interprets and responds to user queries. In this repository, we utilize __Llama 3.2-1B__ to process questions, analyze context retrieved from the vector store, and generate responses with a predefined personality. To power our retrieval system, we integrated the __nomic-embed-text:latest__ model. This model converts text into high-dimensional vectors, enabling high-speed data indexing and highly accurate semantic searches.<sub>[5][11][12]</sub><br ><br >
- RAG (Retrieval-Augmented Generation):<br >
RAG is an AI workflow where models follow developer-designed workflows to search for information in vector stores or the internet before responding to users <sub>[13]</sub>. In this repository, we built a vector store containing specialized information on Plantar Fasciitis. We designed a workflow that requires the AI to search for specific symptoms and treatments within that database before answering any user queries.<br >
  1. Data Ingestion:<br >
  To populate the database, we created an ingestion pipeline using __File__, __Splitter__, and __Vector Store__ components. We gathered data by converting Plantar Fasciitis YouTube videos <sub>[7][8]</sub> into text via `YouTubeToTranscript.com` <sub>[9]</sub>. To optimize this process, we used a __Splitter__ to break the text into smaller chunks. These chunks were then stored in __ChromaDB__, where the __nomic-embed-text:latest__ model converted them into vectors for efficient indexing and semantic retrieval. <sub>[5]</sub><br >
  2. Query & Retrieval:<br >
  For the search phase, we configured a ChromaDB instance pointing to our existing database using the same embedding model. This allows the system to take a question from the __Chat Input__, convert it into a vector, and retrieve the most relevant text segments from the store. <sub>[5]</sub><br ><br >
- Input and Output:<br >
We utilized __Chat Input__ and __Chat Output__ components to manage user interaction. When a user submits a question, the system searches the vector store and uses a __Parse Data__ component to format the retrieved chunks into clean text. This text is then passed into a __Prompt Template__, where we have predefined the AI’s personality as a medical assistant specializing in Plantar Fasciitis. This ensures the final output is a professional response containing accurate information and recommended treatments. <sub>[5][7][8]</sub><br >
## Reference
[1] [ollama github](https://github.com/ollama/ollama)<br >
[2] [ollama.com](https://ollama.com/)<br >
[3] [Llama 3.2: Revolutionizing edge AI and vision with open, customizable models](https://ai.meta.com/blog/llama-3-2-connect-2024-vision-edge-mobile-devices/)<br >
[4] [Introducing Nomic Embed: A Truly Open Embedding Model](https://www.nomic.ai/news/nomic-embed-text-v1)<br >
[5] [Build AI Chatbots (with RAG) for FREE using Langflow and Ollama (Run Models Locally)](https://www.youtube.com/watch?v=tVwdpQyjtOc&list=LL&index=11)<br >
[6] [langflow github](https://github.com/langflow-ai/langflow)<br >
[7] [Fix Plantar Fasciitis Fast - Foot Pain Gone (50+)](https://www.youtube.com/watch?v=Eq0SssY4ZXs)<br >
[8] [How To Fix Plantar Fasciitis (NO MORE HEEL PAIN!)](https://www.youtube.com/watch?v=NE0GqcRb9f8)<br >
[9] [YouTubeToTranscript.com](https://youtubetotranscript.com/)<br >
[10] [uv introduction](https://docs.astral.sh/uv/)<br >
[11] [How to Run AI Models Locally with Langflow and Ollama](https://www.youtube.com/watch?v=kFEMtax1yd4)<br >
[12] [Using Ollama with Agents in Langflow](https://www.youtube.com/watch?v=bZDk5sgMLsk)<br >
[13] [AI Agents, Clearly Explained](https://www.youtube.com/watch?v=FwOTs4UxQS4)<br >

