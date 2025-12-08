# LearnPlay – Project Documentation

---

## Project Overview

LearnPlay is a gamified education platform designed to make learning engaging by converting topics into interactive quiz games. It is a full-stack project built using **React** for the frontend, **Spring Boot** for the backend, and **MySQL** as the database.

For authentication, we implemented **JWT authentication**, which ensures secure login and protects all quiz-related APIs. We also integrated the **Gemini API**, which generates quiz questions dynamically based on the topic selected by the user.

### Workflow:
- The frontend allows users to play quizzes, view scores, and track their progress.  
- The backend handles user authentication, quiz logic, and stores all user and quiz data in MySQL.

---

## My Contribution

My contribution to this project was mainly on the backend.  
I worked with Spring Boot to:

- Build REST APIs  
- Implement JWT authentication  
- Design data models  
- Handle communication with the frontend  
- Ensure secure and modular backend architecture  

The goal was to make the backend reliable so users could log in, access quizzes, and track progress smoothly.

---

## What I Learned

Through this project, I learned:

- How to build a secure backend system with Spring Boot  
- How JWT authentication works in real applications  
- How to integrate a React frontend with a Spring Boot REST API  
- How to design clean, modular, and expandable backend code  

---

## Challenges Faced in the Project

One of the main challenges I faced was implementing **JWT authentication** correctly. Managing token generation, validation, and securing endpoints was initially confusing.

I solved this by:

1. Studying the official Spring Security and JWT documentation  
2. Discussing a few parts with seniors and batchmates to validate my approach  
3. Breaking the implementation into smaller steps:  
   - Token creation  
   - Token validation  
   - Adding filters  
   - Securing endpoints  
4. Testing each part separately  

This structured approach helped me implement JWT cleanly and reliably.

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

