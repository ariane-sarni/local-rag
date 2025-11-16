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

## Build goals: 

Build RAG pipeline that runs locally on my device. It will do the following:

1. Open up a document I pass it, whether it be a PDF, .MD file, etc.
2. Format the text for an embedding model.
3. Embed all the neccesary chunks of text and turn it into a numerical representation which can be stored.
4. Build a retrieval system (vector search?) to find relevant chunks of text based on the query.
5. Generate a prompt that incorporates the retrieved pieces of text.
6. Generate an answer to the query based on the passage of the document with an LLM.

1. Steps 1-3: Document preprocessing and embedding creation.
2. Step 4-6: Search and answer.

### 1. Document/Text processing and embedding creation

Neccesary:
* PDF document of choice (Not neccesarily PDF - could be Markdown, .txt, etc.)
* Embedding model of choice.

Steps:
1. Import document.
2. Proces text for embedding (split into chunks of sentences).
3. Embed text chunks with embedding model.
4. Save embeddings to file for later use. (Will store on file for many years, however long you need.) 