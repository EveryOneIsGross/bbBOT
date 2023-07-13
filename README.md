# bbBOT
## Binary Branching Tree Logic Framework for Persona-Based Sentiment Reflection

bbBOT is a Python project that uses OpenAI's GPT-3 to generate responses from multiple chatbots with unique personas. The chatbots form a binary branching tree logic network, where the path of the conversation is determined by the sentiment detected in each chatbot's response. Each node in the network represents a chatbot, and the conversation flows from one chatbot to another based on whether the sentiment of a chatbot's response is positive or negative. The tree structure ends with two summary bots that summarize the conversation so far.

## Features

Supports any number of chatbots.
Each chatbot can have a unique persona.
Sentiment analysis of chatbot responses to guide the flow of conversation.
Summary bots that provide a running summary of the conversation.
Conversation history that is passed to each bot, allowing context-aware responses.
Output stored in JSON format for further analysis.

# How it Works

The chatbots are represented as nodes in a binary tree. Each chatbot (node) has two branches: one for a positive response (next_node_positive) and one for a negative response (next_node_negative). The sentiment of a chatbot's response, determined using NLTK's sentiment analysis, guides the path of the conversation.

If a chatbot's response has a positive sentiment, the conversation moves to the next_node_positive. If the response has a negative sentiment, it moves to the next_node_negative. The conversation continues to flow through the network of chatbots until it reaches one of two summary bots.

The summary bots summarize the conversation so far. They also serve as end nodes in the tree structure.

## Setup and Requirements

This project uses Python 3 and requires several libraries, including openai, nltk, json, and rake_nltk.

To set up the project:

Clone the repository.
Install the required libraries using pip: pip install -r requirements.txt
Set up the OpenAI API key in your environment variables.
Run the script with: python bbBOT.py

## Usage

You will be prompted to input your query and the number of chatbots. You can then customize the name, character role, and temperature for each chatbot and the summary bots. If you leave these inputs blank, default values will be used.

Once all inputs are provided, the conversation starts with the first chatbot and progresses through the network based on the sentiment of each response. The conversation ends with a summary from one of the summary bots.

The responses from each chatbot, along with the keywords and sentiment, are saved to a JSON file for further analysis.
