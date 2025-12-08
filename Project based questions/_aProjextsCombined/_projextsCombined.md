# LearnPlay – Project Documentation
- [LearnPlay – Project Documentation](#learnplay--project-documentation)
- [Challenges Faced in the Project](#challenges-faced-in-the-project)
- [What Is JWT?](#what-is-jwt)
- [Why These Technologies?](#why-these-technologies)
- [How Is Your Project Different from Existing Solutions?](#how-is-your-project-different-from-existing-solutions)
- [If Given More Time, What Would You Improve?](#if-given-more-time-what-would-you-improve)


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

---

## Challenges Faced in the Project

One of the main challenges I faced was implementing JWT authentication correctly. Initially, managing token generation, validation, and securing the API endpoints was confusing.

To solve this, I first went through the official Spring Security and JWT documentation to understand the workflow clearly. I also discussed a few parts with seniors and batchmates to validate my approach and make sure I was following the right structure.

After that, I broke the implementation into smaller steps—token creation, token validation, filters, and endpoint security—and tested each part individually. This step-by-step approach helped me implement JWT in a clean and reliable way.

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

---

## Why These Technologies?

**React** – Fast, component-based, and great for building dynamic UIs.  
**Spring Boot** – Ideal for secure, production-ready backend applications; simplifies REST API creation.  
**MySQL** – Stable, relational database for structured data such as users, quizzes, and scores.  
**Gemini API** – Integrates well with Spring AI and allowed dynamic quiz generation based on topics.

---

## How Is Your Project Different from Existing Solutions?

Most learning platforms focus mainly on video lectures or static quizzes.  
LearnPlay is different because it introduces **gamification**, making learning interactive through quizzes, scoring, and progress tracking.

Another key difference is the use of the **Gemini API**, which generates quiz questions dynamically.  
This means learners get **fresh, personalized questions** every time instead of fixed question sets.

The combination of **gamified learning**, **dynamic AI-generated quizzes**, and a **simple, engaging UI** sets LearnPlay apart from traditional platforms.

---

## If Given More Time, What Would You Improve?

If given more time, I would work on:

- Adding more gamification features like **leaderboards, badges, and levels**  
- Improving user analytics to show strengths, weak areas, and detailed progress  
- Introducing more quiz formats and a **fully adaptive learning engine**  
- Building a **mobile-friendly version** or dedicated mobile app for better accessibility  

These improvements would make the platform more personalized, engaging, and user-friendly.

---
---




