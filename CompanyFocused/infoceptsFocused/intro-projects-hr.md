# Interview – Infocepts

## Table of Contents
- [Technical Round Introduction](#technical-round-introduction)
- [HR Round Introduction](#hr-round-introduction)
- [LearnPlay Project Documentation](#learnplay-project-documentation)
- [Quill.AI – Text Summarization Platform](#quillai--text-summarization-platform)
- [Zync – Chat and Social Feed Platform](#zync--chat-and-social-feed-platform)
- [ZapUI – React Component Library](#zapui--react-component-library)

# HR Interview Answers – Infocepts

## Table of Contents
- [What do you know about Infocepts?](#what-do-you-know-about-infocepts)
- [Why Infocepts?](#why-infocepts)
- [Where do you see yourself in 5 years?](#where-do-you-see-yourself-in-5-years)
- [Why Should We Hire You?](#why-should-we-hire-you)
- [What are your strengths?](#what-are-your-strengths)
- [What is your weakness?](#what-is-your-weakness)
- [Tell me about a time you worked in a team](#tell-me-about-a-time-you-worked-in-a-team)
  

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

**The layers of AI typically refer to the AI technology stack:  
1) Data Layer, 2) Model Layer, 3) Infrastructure Layer, and 4) Application Layer.  
If you mean neural network layers, then they consist of Input Layer, Hidden Layers, and Output Layer.**


---
---

# Project Documentation

---

## Zync – Chat and Social Feed Platform

**Zync is a simple chat and social feed platform where users can post updates and view messages in a clean interface.  
The aim of the project was to create a basic communication system with a structured backend and an organized frontend.**

The tech stack includes **Spring Boot** for the backend and **React with Redux** for the frontend.

- **Spring Boot** handles APIs for users, posts, and chat-related data.  
- **React** manages the UI.  
- **Redux** is used to keep the state consistent across the application, especially for posts, user data, and chat messages.

My contribution to this project was mainly on the **backend and frontend integration**.

- On the backend, I worked with Spring Boot to build **REST APIs** for users, posts, and chat data.  
- On the frontend, I used **React + Redux** to manage application state and display the data smoothly.

From this project, I learned how to design **clean REST APIs**, connect them with a React frontend, and use **Redux** to manage shared state.  
It also helped me understand **how data flows in a social platform** and how to structure both backend and frontend for smooth interaction.

---

## ZapUI – React Component Library

**ZapUI is a React component library published as an npm package.  
It provides reusable components like Avatar, Button, Input, Browser components, etc.  
The library is built using plain CSS to keep it lightweight and framework-independent.**

My contribution to this project included:

- Developing core components such as **Button**, **Avatar**, etc.  
- Handling the **npm workflow** — publishing the package, updating versions, and ensuring smooth installation for other developers through:

```bash
npm install zapui
```

From this project, I learned how to build reusable UI components, maintain consistent styling with plain CSS, and manage the full **npm publishing workflow**, including versioning and distribution.

---
---
---

# HR Interview Answers – Infocepts

## Table of Contents
- [What do you know about Infocepts?](#what-do-you-know-about-infocepts)
- [Why Infocepts?](#why-infocepts)
- [Where do you see yourself in 5 years?](#where-do-you-see-yourself-in-5-years)
- [Why Should We Hire You?](#why-should-we-hire-you)
- [What are your strengths?](#what-are-your-strengths)
- [What is your weakness?](#what-is-your-weakness)
- [Tell me about a time you worked in a team](#tell-me-about-a-time-you-worked-in-a-team)

---

## What do you know about Infocepts?

Infocepts is a global leader in data and AI solutions — the company helps organizations across industries to become data-driven, leveraging data platforms, analytics, and AI-based applications to extract business value.  
Infocepts also has a strong global presence and works with clients worldwide, which means working there gives exposure to varied domains and large-scale data projects.  
I’m particularly interested in Infocepts because they focus a lot on learning and development, which aligns with my goal of growing in data, analytics, and software engineering.”

---

## Why Infocepts?

Infocepts is a global leader in data and AI solutions — the company helps organizations across industries to become data-driven, leveraging data platforms, analytics, and AI-based applications to extract business value.  
“Infocepts gives exposure to real-world data and AI projects, encourages continuous learning, and provides a strong growth path for freshers. Since I’m interested in backend, databases, and AI, I feel it’s the right place for me to learn and contribute.”

---

## Where do you see yourself in 5 years?

“In five years, I see myself as a more skilled and confident professional with strong technical foundations. I want to learn from real projects, improve continuously, and take more responsibility in areas like IT operations and security. My focus is to grow steadily, contribute well to the team, and build a stable career.”

---

## Why Should We Hire You?

“You should hire me because I have a strong technical foundation, I learn quickly, and I’m genuinely interested in growing in the areas Infocepts focuses on — data, backend systems, and analytics-driven applications.  
Through my projects, I’ve worked with real technologies like React, Spring Boot, MySQL, JWT authentication, and even AI/LLM integration, which has helped me build practical problem-solving abilities. I also practice DSA regularly, so I am comfortable with logical thinking and structured problem solving.

Along with technical skills, I am consistent, responsible, and a good team player — through ITESA club activities and hackathons, I’ve gained experience in collaborating under deadlines.  
I believe I will be able to learn quickly during the training period and contribute effectively to real projects, while also growing within Infocepts.”

---

## What are your strengths?

### ⭐ Strength 1: Quick Learning  
"One of my strengths is that I learn new concepts quickly. Whenever I work on a project, I try to understand both the basics and the practical implementation. For example, I learned Spring Boot, JWT authentication, and React by building real projects, which helped me pick things up faster."

### ⭐ Strength 2: Teamwork  
"I'm also good at teamwork. I've worked with teams during college events and hackathons, and we always coordinated tasks, shared ideas, and supported each other. I communicate clearly and adjust myself to the needs of the team, which helps in completing work smoothly."

---

## What is your weakness?

⭐ Answer:  
"One area I'm working on is my tendency to take on too many tasks at once. I realized that this can reduce efficiency at times. To improve this, I've started prioritizing tasks based on urgency and importance, and I break work into smaller steps. This helps me stay productive."

---

## Tell me about a time you worked in a team

"I worked as part of the ITESA tech team during college events. We had to create and manage the event website and handle various technical tasks. The team was divided into small groups, and we coordinated our work through regular discussions. I contributed by helping with frontend updates and solving small issues quickly. This taught me how to communicate clearly, organize tasks, and support team members when required."

---
---




