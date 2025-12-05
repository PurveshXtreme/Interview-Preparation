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






