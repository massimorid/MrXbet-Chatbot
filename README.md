# Project Proposal
The project is a Chatbot for Massimo Scolari which owns 5 different online casinos. The Chatbot will offer customer support and in-game assistance.

The chatbot will handle low-effort redundant customer querys. The result: Better customer experience, less CS workload.

The chatbot will offer 24/7 assistance giving the user assistance whenever needed.

If the query were to be high-complexity or the user asks to be passed on to a CS, the conversation will be transferred.


## Project Architecture
The chatbot will be a GPT wrapped RAG (Retrieval Augmented Generation) system.
Main components:

![image](https://github.com/user-attachments/assets/ce4d05c4-6d93-4c5c-86bc-53c6c002f0c7)

  1. Docker

     The chatbot will be deployed with docker. Docker allows for any device to successfully run the chatbot in a lightweight fashion
  2. GPT (or alternative LLM Models)

     GPT (or other LLMs) will take care of query refinement, query embedding and answer generation
  3. Pinecone

     Pinecone will take GPT's embeddings and run a similarity algorithm with the documentation given on the casino, then return the most relevant information related to the query
  4. FastText

     FastText will identify the intent of the user query. A classification algorithm will be run on every query before running the RAG as to make sure the query is related to the casino in some form
       
## Functional Requirements

In this section of the document we will present what the chatbot assistant should do, how it should behave and what it should not do
\n
  
  **FR1**: The chatbot will be able to answer a wide variety of casino related low-level questions

  **FR2**: The chatbot will not incentivize the user to gamble or offer gambling advice, as it should uniquely respond to user querys

  **FR3**: The chatbot will categorize every user query as 'Relevant' or 'Not Relevant'

  **FR4**: The chatbot will respond to non-related querys with the following message "I cannot answer your question, I am only here to assist you with casino related-queries"

  **FR5**: The chatbot will respond to gambling related queries with the following message "I cannot answer your question, I am not legally allowed to offer gamglind advice"

  **FR6**: The chatbot will redirect the conversation to CS if explicitly queried from the user

  **FR7**: When the chatbot is uncertain of what to answer, the customer will bre redirected to CS.

 
## Non Functional Requirements

  
  **TBD based on Customer Needs**
  
## Security


