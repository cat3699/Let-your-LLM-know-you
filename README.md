# Let-your-LLM-know-you

## Project Overview
This project utilizes a large language model (LLM), specifically Meta's Llama 3.2, a 3B model provided by Ollama, to respond to messages that a user receives. The goal is to mimic the user's tone, personality, and communication style as closely as possible, providing highly personalized responses that feel authentic to the user.

## Technologies Used
### Programming Language: 
- Python
### Libraries & Frameworks:
- Ollama: A client for interacting with the Llama 3.2 model.
- Chroma DB: For performing similarity searches in the user databases.
- Pandas & NumPy: For data manipulation and analysis.

## Approach
The system works by utilizing several key components:

### User Database Integration in Prompt Template:
This part of the prompt template contains a database with the user's contact list, the familiarity level with each contact, and the tone the user typically uses when addressing each individual.

### Few-Shot Example Generation :
To ensure the LLM can replicate the user's style accurately, three separate databases are used to retrieve relevant few-shot examples:

- **Past Messages Database**: Contains previous messages sent by the user to their contacts, along with annotations about the tone used in each message (e.g., formal, casual, friendly).
- **Personal Habits and Hobbies Database**: A collection of responses provided by the user to prompts designed to uncover their daily habits, hobbies, and general preferences.
- **36 Questions to Fall in Love Database**: A set of answers from the user to the "36 Questions to Fall in Love," which reveals deeper insights into their values, principles, and emotional responses.

### Similarity Search:
The system performs similarity searches within these three databases to identify the most relevant examples for the current message context. These examples are then used as few-shot examples to guide the LLM in crafting the response.

## How It Works
When a message is received, the system analyzes the content and searches the relevant databases for examples that match the context and tone of the message, as well as the information present in the database about the person sending the message.
This information is them provided to the LLM, which uses them to generate a response that reflects the user’s communication style, habits, and personal values.


## Objective
The primary goal is to provide responses that feel authentic and consistent with how the user would naturally communicate with their contacts, considering their relationships and the context of the message.


