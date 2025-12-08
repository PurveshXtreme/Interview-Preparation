# LearnPlay – Project Documentation
- [LearnPlay – Project Documentation](#learnplay--project-documentation)
- [Challenges Faced in the Project](#challenges-faced-in-the-project)
- [What Is JWT?](#what-is-jwt)
- [Why These Technologies?](#why-these-technologies)
- [How Is Your Project Different from Existing Solutions?](#how-is-your-project-different-from-existing-solutions)
- [If Given More Time, What Would You Improve?](#if-given-more-time-what-would-you-improve)

---

# Quill.AI – Documentation
- [Quill.AI – Text Summarization Platform](#quillai--text-summarization-platform)
- [Challenges Faced](#challenges-faced)
- [How Is Your Project Different from Existing Solutions?](#how-is-your-project-different-from-existing-solutions)
- [If Given More Time, What Would You Improve?](#if-given-more-time-what-would-you-improve)
- [Frontend & Backend Technology Choices](#frontend--backend-technology-choices)
- [Model Choice (BART, GPT, Gemini)](#model-choice-bart-gpt-gemini)
- [Summarization Concepts](#summarization-concepts)
- [Tokens & Token Limits](#tokens--token-limits)
- [Libraries Used](#libraries-used)
- [LLM (Large Language Model) Explanation](#llm-large-language-model-explanation)
- [Types of LLMs](#types-of-llms)
- [Transformer Architecture](#transformer-architecture)
- [Attention Mechanism](#attention-mechanism)

---
---

# LearnPlay – Project Documentation

---

LearnPlay is a gamified education platform designed to make learning engaging by converting topics into interactive quiz games. It is a full-stack project built using React for the frontend, Spring Boot for the backend, and MySQL as the database.

For authentication, we implemented JWT authentication, which ensures secure login and protects all quiz-related APIs. We also integrated the Gemini API, which generates quiz questions dynamically based on the topic selected by the user.

The workflow is simple:

- The frontend allows users to play quizzes, view scores, and track their progress.  
- The backend handles user authentication, quiz logic, and stores all user and quiz data in MySQL.

My contribution to this project was mainly on the backend. I worked with Spring Boot to build REST APIs, implement JWT authentication, design the data models, and ensure smooth communication between the frontend and backend. I focused on making the backend secure, modular, and reliable so that users could log in, access quizzes, and track progress without issues.

Through this project, I learned how to build a secure backend system, integrate a React frontend with a Spring Boot API, and follow clean, modular coding practices.

[Back to Table of Contents](#learnplay--project-documentation)

---

## Challenges Faced in the Project

One of the main challenges I faced was implementing JWT authentication correctly. Initially, managing token generation, validation, and securing the API endpoints was confusing.

To solve this, I first went through the official Spring Security and JWT documentation to understand the workflow clearly. I also discussed a few parts with seniors and batchmates to validate my approach and make sure I was following the right structure.

After that, I broke the implementation into smaller steps—token creation, token validation, filters, and endpoint security—and tested each part individually. This step-by-step approach helped me implement JWT in a clean and reliable way.

[Back to Table of Contents](#learnplay--project-documentation)

---

## What Is JWT?

**JWT (JSON Web Token)** is a secure way of verifying users and communicating identity between the client and server **without storing any session data** on the server.  
It works because the token is digitally signed, making it tamper-proof.

### JWT Workflow:
- User logs in  
- Server verifies credentials and generates a token  
- Client stores the token and sends it with every request  
- Server validates the token before allowing access  

In my Spring Boot project, I used dependencies like `jjwt-api`, `jjwt-impl`, and `jjwt-jackson` to generate and validate tokens.

[Back to Table of Contents](#learnplay--project-documentation)

---

## Why These Technologies?

**React** – Fast, component-based, and great for building dynamic UIs.  
**Spring Boot** – Ideal for secure, production-ready backend applications; simplifies REST API creation.  
**MySQL** – Stable, relational database for structured data such as users, quizzes, and scores.  
**Gemini API** – Integrates well with Spring AI and allowed dynamic quiz generation based on topics.

[Back to Table of Contents](#learnplay--project-documentation)

---

## How Is Your Project Different from Existing Solutions?

Most learning platforms focus mainly on video lectures or static quizzes.  
LearnPlay is different because it introduces **gamification**, making learning interactive through quizzes, scoring, and progress tracking.

Another key difference is the use of the **Gemini API**, which generates quiz questions dynamically.  
This means learners get **fresh, personalized questions** every time instead of fixed question sets.

The combination of **gamified learning**, **dynamic AI-generated quizzes**, and a **simple, engaging UI** sets LearnPlay apart from traditional platforms.

[Back to Table of Contents](#learnplay--project-documentation)

---

## If Given More Time, What Would You Improve?

If given more time, I would work on:

- Adding more gamification features like **leaderboards, badges, and levels**  
- Improving user analytics to show strengths, weak areas, and detailed progress  
- Introducing more quiz formats and a **fully adaptive learning engine**  
- Building a **mobile-friendly version** or dedicated mobile app for better accessibility  

These improvements would make the platform more personalized, engaging, and user-friendly.

[Back to Table of Contents](#learnplay--project-documentation)

---
---

# Quill.AI – Documentation

## Table of Contents
- [Quill.AI – Text Summarization Platform](#quillai--text-summarization-platform)
- [Challenges Faced](#challenges-faced)
- [How Is Your Project Different from Existing Solutions?](#how-is-your-project-different-from-existing-solutions)
- [If Given More Time, What Would You Improve?](#if-given-more-time-what-would-you-improve)
- [Frontend & Backend Technology Choices](#frontend--backend-technology-choices)
- [Model Choice (BART, GPT, Gemini)](#model-choice-bart-gpt-gemini)
- [Summarization Concepts](#summarization-concepts)
- [Tokens & Token Limits](#tokens--token-limits)
- [Libraries Used](#libraries-used)
- [LLM (Large Language Model) Explanation](#llm-large-language-model-explanation)
- [Types of LLMs](#types-of-llms)
- [Transformer Architecture](#transformer-architecture)
- [Attention Mechanism](#attention-mechanism)

---

# Quill.AI – Text Summarization Platform

**Quill.AI is a simple text-summarization platform that takes long text as input and generates a concise summary. The main idea of the project was to allow users to quickly understand long articles or documents by using an AI model to shorten the content.**

The tech stack includes **HTML, CSS, and JavaScript** for the frontend, and **Python with the Hugging Face BART model** for the backend.

My contribution to this project was mainly on the **frontend side**. I designed the user interface, including the landing page and input forms, and focused on making the UI simple, clean, and easy to use.

From this project, I learned how the frontend communicates with a backend that uses AI models, and display the summarized text returned from the backend in a clear and readable manner.

[Back to TOC](#table-of-contents)

---

# Challenges Faced

### ⭐ Updated HR-safe version (mentions seniors)

**One challenge I faced was making the frontend clean and responsive. Initially, the layout was breaking on smaller screens.  
To solve this, I first tried different CSS adjustments and flexible units. I also discussed the issue with batchmates and seniors to confirm whether my approach was correct. After testing the UI across multiple screen sizes and refining the CSS, the layout became stable.**

**Another challenge was understanding how the summarization model works internally. I went through Hugging Face documentation and also asked peers for clarification on token limits and output variations. Experimenting with different summary lengths and parameters helped me achieve consistent summaries.**

[Back to TOC](#table-of-contents)

---

# How Is Your Project Different from Existing Solutions?

Most summarization tools depend completely on cloud-based APIs like GPT or Gemini.  
**Quill.AI is different because it uses an *offline, open-source* Hugging Face BART model**, meaning:

- No API cost  
- No dependency on external servers  
- Works locally  
- Fast response times  

Additionally:

- The UI is intentionally simple and lightweight  
- The tool focuses on purely text summarization (no distractions)  
- It provides reliable abstractive summaries similar to commercial tools, but completely free

This combination of **offline AI + simplicity + zero cost** makes it unique compared to typical online summarization platforms.

[Back to TOC](#table-of-contents)

---

# If Given More Time, What Would You Improve?

If given more time, I would work on:

- Adding support for multiple summary lengths (short, medium, detailed)  
- Improving UI/UX for a smoother user workflow  
- Supporting different summarization models (T5, Pegasus)  
- Adding file upload support (PDF, TXT)  
- Adding dark mode and better readability features  
- Creating a backend queue system so long text processing doesn’t block requests  

These improvements would make Quill.AI more flexible, accessible, and user-friendly.

[Back to TOC](#table-of-contents)

---

# Quill.AI – Interview Q&A Notes

## Frontend & Backend Technology Choices

### ⭐ 1. Why HTML, CSS, and JavaScript for the frontend?
**“I used HTML, CSS, and JavaScript because they are lightweight, fast, and ideal for building simple and responsive user interfaces.  
The project didn’t require a heavy framework like React, so plain JS gave full control over the UI and made the development process quick and flexible.”**

### ⭐ 2. Why Python for the backend?
**“We used Python because it has excellent support for AI/ML libraries. Hugging Face and transformer models run more smoothly in Python, so integrating the BART model for summarization was very easy. Python also has simple frameworks like Flask that make API development quick.”**

[Back to TOC](#table-of-contents)

---

## Model Choice (BART, GPT, Gemini)

### ⭐ 3. Why BART for summarization?
**“BART is a transformer-based encoder–decoder model that is specifically fine-tuned for summarization tasks.  
It is optimized for abstractive summarization and performs very well on general text.”**

### ⭐ 4. Why not GPT or Gemini?
**“GPT and Gemini are powerful, but they require API keys, have usage costs, and depend on external servers.  
Since our goal was a free and offline summarization backend, BART was a better option because it is open-source, free, and can run locally without any API dependency.”**

[Back to TOC](#table-of-contents)

---

## Summarization Concepts

### ⭐ Extractive vs Abstractive Summarization
**“Extractive summarization picks key sentences directly from the original text.  
Abstractive summarization generates new sentences using its understanding of the content.  
BART performs abstractive summarization.”**

[Back to TOC](#table-of-contents)

---

## Tokens & Token Limits

### ⭐ What are tokens?
**“Tokens are small units of text — like words or sub-words — that the model understands.  
The model doesn’t work directly with raw text; it works with token IDs that represent the text.”**


### ⭐ What is the token limit for BART?
**“The BART-large model has a limit of around 1,024 tokens for input.  
If the text is longer than this, it must be shortened or chunked before summarization.”**

[Back to TOC](#table-of-contents)

---

## Libraries Used

### ⭐ Hugging Face Transformers
**Final Answer:**  
**“The project uses the Hugging Face Transformers library.”**

### Why?
**“We used the Hugging Face Transformers library because it provides pre-trained models like BART that can be used directly for summarization.  
It also simplifies tokenization, model loading, and inference through the pipeline API.”**

[Back to TOC](#table-of-contents)

---

## LLM (Large Language Model) Explanation

### ⭐ What is an LLM?
**“An LLM (Large Language Model) is an AI model trained on a huge amount of text data.  
It learns patterns in language such as grammar, meaning, context, and relationships between words.  
LLMs are built using transformer architecture, which uses attention mechanisms to understand context in sentences.”**


[Back to TOC](#table-of-contents)

---

## Types of LLMs

### ⭐ 1. Encoder-Only Models  
**Examples:** BERT  
**Purpose:** Understanding tasks (classification, sentiment analysis, NER)  
**Reason:** Encoder-only models read input bidirectionally and are excellent for comprehension.

### ⭐ 2. Decoder-Only Models  
**Examples:** GPT(Generative Pretrained Transformer), LLaMA, Gemini (partially)  
**Purpose:** Text generation (chatbots, stories, code generation)  
**Reason:** They generate text one token at a time using previous context.

### ⭐ 3. Encoder–Decoder Models  
**Examples:** BART, T5  
**Purpose:** Summarization, translation, question answering  
**Reason:**  
- **Encoder** understands the full input  
- **Decoder** generates the output  
Perfect for input → output transformations.

[Back to TOC](#table-of-contents)

---

## Transformer Architecture

### ⭐ What is Transformer Architecture? (Short & Simple)
**“Transformer architecture is a deep learning model used for language tasks.  
It processes all words in a sentence at the same time (parallel), instead of one-by-one like older models.  
This makes it faster, more accurate, and better at understanding context.”

[Back to TOC](#table-of-contents)

---

## Attention Mechanism

### ⭐ What is Attention Mechanism? (Short & Simple)
**“Attention is the method transformers use to understand which words in a sentence are important.  
Instead of treating all words equally, attention lets the model ‘focus’ on the right words while reading or generating text.”**

[Back to TOC](#table-of-contents)

---
---
