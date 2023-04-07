# Lex Fridman Podcast QA Agent
This repository demonstrates how to build a conversational agent that answers user questions using transcripts from the Lex Fridman podcast.

The agent is built using the following Python packages: `langchain`, `pod-gpt`, `pinecone-client[grpc]`, `openai`, and `tqdm`.

## Description
The conversational agent is built on top of a vector database that indexes transcripts from the Lex Fridman podcast using an OpenAI GPT-3.5-turbo language model. The agent retrieves answers from the vector database using a question-answering model based on the `RetrievalQA` class from the langchain library.
The Memory class from the `langchain.chains.conversation.memory` module is used to provide conversational memory to the agent. Code is based off of Pinecone examples [here](https://github.com/pinecone-io/examples/blob/master/generation/chatbots/conversational-agents/langchain-lex-agent.ipynb). Great walkthrough!

## Steps
1. Download a pre-built dataset of Lex Fridman podcast transcripts using datasets from Hugging Face.
2. Use the pod-gpt package to create an indexer for the transcripts and index them to a Pinecone vector database.
3. Initialize the RetrievalQA class from the langchain.chains module with the OpenAI GPT-3.5-turbo language model and the Pinecone vector database.
4. Initialize a Tool object with the RetrievalQA object, a description of the tool, and a name for the tool.
5. Initialize a Memory object from the langchain.chains.conversation.memory module.
6. Use initialize_agent() from the langchain.agents module to create a conversational agent with the initialized Tool and Memory objects.

## License

This script is open-source and licensed under the MIT License. For more details, check the [LICENSE](LICENSE) file.
