# Interview – Infocepts

## Table of Contents
- [Technical Round Introduction](#technical-round-introduction)
- [HR Round Introduction](#hr-round-introduction)
- [LearnPlay Project Documentation](#learnplay-project-documentation)
- [Quill.AI – Text Summarization Platform](#quillai--text-summarization-platform)
- 
  

---

## Technical Round Introduction

**Good morning sir. My name is Purvesh Jambhulkar, and I’m currently pursuing my B.E. in Information Technology from D.Y. Patil College of Engineering, Akurdi.**

I’ve built a strong foundation in programming, databases, and big data fundamentals through my academics and the projects I’ve worked on. I have developed several full-stack applications using React, Spring Boot, and MySQL, such as **LearnPlay**, a gamified learning platform, and **Quill.AI**, a text-summarization platform built using LLMs. I’ve also worked on projects like **ZAPI-UI**, a React component library, and a few college event websites.

Working on these projects helped me understand how APIs work, **how databases work in real-world applications**, and how data flows between the frontend, backend, and database. I also practice problem-solving on LeetCode and GeeksforGeeks, which has strengthened my logic-building and DSA fundamentals.

I’m interested in **Infocepts** because the role focuses on analysis, problem-solving, and continuous learning, which aligns well with my strengths. I’m looking forward to applying my technical foundation, learning new technologies, and contributing to meaningful, data-driven projects.

---

## HR Round Introduction

**Good morning sir. My name is Purvesh Jambhulkar, and I’m currently pursuing my B.E. in Information Technology from D.Y. Patil College of Engineering, Akurdi.**

I’ve built a strong foundation in programming, databases, and big data fundamentals through my academics and the projects I’ve worked on. I also practice problem-solving on LeetCode and GeeksforGeeks, which has strengthened my logic-building and DSA fundamentals.

Along with academics, I have been actively involved in teamwork-oriented activities. As a member of the **ITESA club**, I helped organize technical workshops and events, which taught me coordination, planning, and working with diverse teams. I have also participated in **hackathons**, including the Smart India Hackathon, where collaborating under time constraints improved my communication, adaptability, and problem-solving skills.

I would describe myself as someone who enjoys learning new things, understands responsibilities well, and stays consistent with whatever I start. 

I’m interested in **Infocepts** because the role focuses on analysis, problem-solving, and continuous learning, which aligns well with my strengths. I’m looking forward to applying my technical foundation, learning new technologies, and contributing to meaningful, data-driven projects.

---

# LearnPlay Project Documentation

---

LearnPlay is a gamified education platform designed to make learning engaging by converting topics into interactive quiz games. It is a full-stack project built using React for the frontend, Spring Boot for the backend, and MySQL as the database.

For authentication, we implemented JWT authentication, which ensures secure login and protects all quiz-related APIs. We also integrated the Gemini API, which generates quiz questions dynamically based on the topic selected by the user.

The workflow is simple:

- The frontend allows users to play quizzes, view scores, and track their progress.  
- The backend handles user authentication, quiz logic, and stores all user and quiz data in MySQL.

My contribution to this project was mainly on the backend. I worked with Spring Boot to build REST APIs, implement JWT authentication, design the data models, and ensure smooth communication between the frontend and backend. I focused on making the backend secure, modular, and reliable so that users could log in, access quizzes, and track progress without issues.

Through this project, I learned how to build a secure backend system, integrate a React frontend with a Spring Boot API, and follow clean, modular coding practices.

---

**Challenges faced in the project**

One challenge I faced in this project was implementing JWT authentication correctly. At first, managing the token and securing API endpoints was tricky. I solved this problem by breaking it into steps. First, I understood how JWT works, then implemented token generation, implemented token validation, and finally secured the endpoints. Testing each part separately helped me overcome this issue.

---

**Whats is JWT?**

**JWT stands for JSON Web Token. It is a secure way of verifying users and communicating identity between the client and server without storing any session data on the server. It allows information to be transferred safely because the token is digitally signed.**

**The workflow is simple:**

- The user logs in,  
- The server verifies the credentials and generates a JWT,  
- The client stores this token and sends it with every API request,  
- The server validates the token before giving access.

**In my Spring Boot application, I used JWT by adding dependencies like `jjwt-api`, `jjwt-impl`, and `jjwt-jackson`, which help in generating, signing, and validating the token.**

---

**Why these technologies?**

**We used React because it allows us to build a fast and responsive UI using reusable components. Its component-based architecture made the development process easy and efficient.**

**For the backend, we chose Spring Boot because it is a strong framework for building secure and production-ready applications. It simplifies the creation of REST APIs and provides smooth integration with databases like MySQL.**

**We used the Gemini API because it integrates well with Spring AI and was suitable for generating quiz questions based on the user’s selected topic. Its support within Spring Boot made the integration smooth, reliable, and free to use for our project requirements.**

---
---

# Quill.AI – Documentation

---

## Quill.AI – Text Summarization Platform

**Quill.AI is a simple text-summarization platform that takes long text as input and generates a concise summary. The main idea of the project was to allow users to quickly understand long articles or documents by using an AI model to shorten the content.**

The tech stack includes **HTML, CSS, and JavaScript** for the frontend, and **Python with the Hugging Face BART model** for the backend.

My contribution to this project was mainly on the **frontend side**. I designed the user interface, including the landing page and input forms, and focused on making the UI simple, clean, and easy to use.

From this project, I learned how the frontend communicates with a backend that uses AI models, and display the summarized text returned from the backend in a clear and readable manner.

---

# Quill.AI – Interview Q&A Notes

## Table of Contents
- [Frontend & Backend Technology Choices](#frontend--backend-technology-choices)
- [Model Choice (BART, GPT, Gemini)](#model-choice-bart-gpt-gemini)
- [Summarization Concepts](#summarization-concepts)
- [Tokens & Token Limits](#tokens--token-limits)
- [Challenges Faced](#challenges-faced)
- [Libraries Used](#libraries-used)
- [LLM (Large Language Model) Explanation](#llm-large-language-model-explanation)
- [Types of LLMs](#types-of-llms)
- [Transformer Architecture](#transformer-architecture)
- [Attention Mechanism](#attention-mechanism)

---

## Frontend & Backend Technology Choices

### ⭐ 1. Why HTML, CSS, and JavaScript for the frontend?
**“I used HTML, CSS, and JavaScript because they are lightweight, fast, and ideal for building simple and responsive user interfaces.  
The project didn’t require a heavy framework like React, so plain JS gave full control over the UI and made the development process quick and flexible.”**

### ⭐ 2. Why Python for the backend?
**“We used Python because it has excellent support for AI/ML libraries. Hugging Face and transformer models run more smoothly in Python, so integrating the BART model for summarization was very easy. Python also has simple frameworks like Flask that make API development quick.”**

---

## Model Choice (BART, GPT, Gemini)

### ⭐ 3. Why BART for summarization?
**“BART is a transformer-based encoder–decoder model that is specifically fine-tuned for summarization tasks.  
It is optimized for abstractive summarization and performs very well on general text.”**

### ⭐ 4. Why not GPT or Gemini?
**“GPT and Gemini are powerful, but they require API keys, have usage costs, and depend on external servers.  
Since our goal was a free and offline summarization backend, BART was a better option because it is open-source, free, and can run locally without any API dependency.”**

---

## Summarization Concepts

### ⭐ 7. Difference between extractive vs abstractive summarization
**“Extractive summarization picks key sentences directly from the original text.  
Abstractive summarization generates new sentences using its understanding of the content.  
BART performs abstractive summarization.”**

---

## Tokens & Token Limits

### ⭐ 10. What are tokens?
**“Tokens are small units of text — like words or sub-words — that the model understands.  
The model doesn’t work directly with raw text; it works with token IDs that represent the text.”**

### ⭐ 11. What is the token limit for BART?
**“The BART-large model has a limit of around 1,024 tokens for input.  
If the text is longer than this, it must be shortened or chunked before summarization.”**

---

## Challenges Faced

### ⭐ 13. Challenges you faced & how you solved them
**“A challenge I faced was making the frontend clean and responsive. Initially, the layout was breaking on smaller screens. I solved this by adjusting the CSS, using flexible units, and testing the UI across multiple screen sizes.  
Another challenge was understanding how the summarization model works. I solved it by reading the Hugging Face documentation and experimenting with different summary lengths until the output was stable.”**

---

## Libraries Used

### ⭐ Hugging Face Transformers
**Final Answer:**  
**“The project uses the Hugging Face Transformers library.”**

### Why?
**“We used the Hugging Face Transformers library because it provides pre-trained models like BART that can be used directly for summarization.  
It also simplifies tokenization, model loading, and inference through the pipeline API.”**

---

## LLM (Large Language Model) Explanation

### ⭐ What is an LLM?
**“An LLM (Large Language Model) is an AI model trained on a huge amount of text data.  
It learns patterns in language such as grammar, meaning, context, and relationships between words.  
LLMs are built using transformer architecture, which uses attention mechanisms to understand context in sentences.”**

---

## Types of LLMs

### ⭐ 1. Encoder-Only Models  
**Examples:** BERT  
**Purpose:** Understanding tasks (classification, sentiment analysis, NER)  
**Reason:** Encoder-only models read input bidirectionally and are excellent for comprehension.

### ⭐ 2. Decoder-Only Models  
**Examples:** GPT, LLaMA, Gemini (partially)  
**Purpose:** Text generation (chatbots, stories, code generation)  
**Reason:** They generate text one token at a time using previous context.

### ⭐ 3. Encoder–Decoder Models  
**Examples:** BART, T5  
**Purpose:** Summarization, translation, question answering  
**Reason:**  
- **Encoder** understands the full input  
- **Decoder** generates the output  
Perfect for input → output transformations.

---

## Transformer Architecture

### ⭐ What is Transformer Architecture? (Short & Simple)
**“Transformer architecture is a deep learning model used for language tasks.  
It processes all words in a sentence at the same time (parallel), instead of one-by-one like older models.  
This makes it faster, more accurate, and better at understanding context.”**

---

## Attention Mechanism

### ⭐ What is Attention Mechanism? (Short & Simple)
**“Attention is the method transformers use to understand which words in a sentence are important.  
Instead of treating all words equally, attention lets the model ‘focus’ on the right words while reading or generating text.”**

---
---






