# Information Retrieval with Qauntized Mistral 7b LLM, LangChain & HF

## Overview
This project focuses on information retrieval using Large Language Models (LLMs) with the LangChain library. LangChain is employed to build an agent that leverages Hugging Face Transformers for text generation and BitsAndBytes for model quantization. The goal is to demonstrate the retrieval of information about specific products using tools like Wikipedia and web search.

## Dependencies Installation
To set up the project, several dependencies need to be installed. Key libraries include Torch, LangChain, Tiktoken, Wikipedia, DuckDuckGo-Search, BitsAndBytes, TRL, and Accelerate. Additionally, GPU support is enabled through CUDA. The installation commands and successful installation confirmation are provided in the code.

BitsAndBytes is a crucial library for quantizing models, optimizing them for deployment.

## Model Quantization
The project employs model quantization using the BitsAndBytes library. Parameters such as the use of 4-bit precision, computation data type, quantization type, and nested quantization are configured. The quantization configuration is applied when loading the Hugging Face Transformers model.

## Model Preparation
A Hugging Face Transformers model (Mistral 7b) for causal language modeling is loaded using the specified model name and the previously configured quantization settings. Tokenization is performed using the AutoTokenizer from Hugging Face.

## Text Generation Pipeline
A text generation pipeline is created using the Hugging Face Transformers pipeline module. The pipeline includes the loaded model and tokenizer, specifying the task as text generation. Additional parameters such as temperature, return_full_text, and max_new_tokens are set.

## LangChain Integration
LangChain utilities, including WikipediaAPIWrapper and DuckDuckGoSearchRun, are instantiated for information retrieval. LangChain tools, represented as agents, are created for Wikipedia and web search. The tools are added to a list, and an agent is initialized using these tools and the previously configured Hugging Face pipeline.

## Agent Execution
A zero-shot retrieval action chain is executed using the initialized agent. The agent is designed to interact with the Wikipedia tool and the web search tool based on the input product. The retrieved information is observed and used to generate a final answer.

## Example Execution
The project provides an example execution where the agent retrieves information about "SageMaker" using Wikipedia and web search tools. The final answer includes a summary of Amazon SageMaker.

## Future Considerations
The project acknowledges certain limitations and considerations, such as the evolving state of LangChain, dependency on pre-generated prompts, and potential issues with accessing external websites. (20/12/23)

## Code Execution Notes
The code is demonstrated on Kaggle, and the author notes that using paid GPUs on Colab would offer browser functionality. Additionally, retrieval tools may face access issues over time, and the Google Search API from LangChain is mentioned as a paid alternative.

## Conclusion
The project serves as an illustrative example of utilizing LangChain and Hugging Face Transformers for information retrieval with LLMs. It showcases the workflow of a typical LLM-based search query and highlights areas for improvement and future development.
