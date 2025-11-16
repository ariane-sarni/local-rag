# Local RAG pipeline and LLM model on local machine.


## What does RAG stand for?

Stands for Retrieval Augmented Generation.

Essentially takes info and passes it to LLM, then LLM generates output based on that information.

* Retrieval - Find info given a certain question, in this example with a PDF discussing nutrition, "What are micronutrients, and what do they do?". The LLM retrieves text related to micronutrients from the textbook.  
* Augmented - Take relevant info and augment are input (The prompt we are giving) to an LLM with that info.
* Generation - Takes first two steps, passes to an LLM for generative outputs. 

## What is the usage of Retrieval Augmented Generation?

RAG improves generation output of LLM.

1. Prevents hallucinations - LLMs are given information factually - they're less likely to hallucinate when they are given actual info as opposed to making up their own information.
2.  Allows LLM to work with custom data - Since LLMs are already trained with internet scaled data, they have a decent understanding of language in general but because of this their responses can be fairly generic. RAG essentially helps create specific responses based on input documents (i.e. your own companies customer support docs, etc.)



## How can RAG be used?

* Customer support chat - Have an existing LLM supported by documentation from the respective company. Retrieves documents already created on how to do certain things, have the LLM use that data when answering. Essentially chatbot for given documentation.
* Email chain analysis - If you're a company with a lost of emails of customer chains, could use a RAG by feeding all of these emails into an LLM, then using said LLM to process that info into more structured data for you to parse through. Maybe turn to JSON.
* Company internal documentation chat
* Textbook Q&A

Essentially: Take relevent documents to a query, and process with an LLM.

Could think of LLM as a calculator for words in this instance.

## Why run locally?

1. No API calls - Potentially faster speed since you're not calling some other LLM.
2. Privacy - Perhaps you're using internal documents you don't want to feed somewhere.
3. Cost - No pricing for API calls.