# 🔴 Why compare different ML Models?

## Problem
There are a bunch of good Machine-Learning models out there that you can use for you specific task or use-case. The problem is, most of the time you have to **pay** to use them, they are pre-trained for a **general usage** not for your specfifc problem and you are totally **dependant** from the company that is running the model. Depending on your use-case and in which country you operate, there are also **privacy issues** as you have to send you potentially sensible data to their API to their servers, where ever these are located.

## Solution
First of all, you can compare different models so that you find the one, that provides the **best results** for your specific use-case. That way you are also **mitigating your risks** because you are not dependant from one model or company. But you can also then try to run this model locally and therefor have **no more privacy issues** and also only have to pay the **costs** for your infrastructure but don't have to pay for the usage of an API any more.

## How To
We will compare 3 different models. The classic **GPT-4-Turbo** using the OpenAI API, we will download the **small Llama3** model (8 billion parameters) to run it locally and we will use Groq API to run the **big Llama3** model (70 billion parameters):

![CompareModels](https://github.com/Tobander/MLProject-CompareModels/assets/45336196/6d31b842-30d1-4236-91e1-aff023067a1e)

# 🟢 2. Loading the documents for your RAG
First thing we need to do is load all the relevant documents you want to use for your RAG. This could be infomration from your website, articles or transcripts from your lectures. We save them all in a folder and then go thru all those files and save them in a list.

# 🟢 3. Creating an Index and Retriever
The next step is to build an index of those documents and then create a tool to retrieve those documents efficiently. An **Inde** is a data structure that allows for fast retrieval of information. Like an organized list or a catalog where you can quickly find what you're looking for. A **retriever** on the other hand is a tool that helps you find documents from the index based on some query or input. So basically, we have our list of documents. We convert those  into Vectors that we can easily search through and then create an organized index of these vectors for fast retrieval. To do this, we use a Retriever that can quickly find the most relevant documents from this index based on a search query or a question.

# 🟢 4. Creating a Lanchain to use with different Models
The main purpose we're using **Langchain** is to efficiently manage and streamline the process of interacting with different AI models because it offers several benefits:

**1. Modularization:** By breaking down the interaction into separate steps (prompt creation, model selection, and output parsing), we can manage and modify each part independently. This modular approach makes our system more flexible and easier to maintain.

**2. Reusability:** Each component of the chain (prompt, model, parser) can be reused just as it is when we switch models. There is no need to change the code in any way as the Chain stays the sam no matter which AI model we are going to use.

**3. Maintainability:** Having a clear structure makes the code easier to read and maintain. If there is a need to change how the prompt is structured or to switch out the parser, these changes can be made in isolation without affecting the entire system.

**4. Consistency:** By using a chain, we ensure that every interaction follows the same process. This consistency helps in maintaining a coherent conversation flow and makes debugging easier.

**5. Conversation Context Management:** The chain allows us to incorporate conversation history into each interaction. This is crucial for maintaining context in a conversation, as it enables usto ask the model follow-up questions to earlier responses.
