### 🧠 Prepify – AI-Powered Mock Interview Platform

Prepify is an AI-driven platform that helps users practice job interviews by generating personalized interview questions and analyzing responses.  
It was built using **Next.js** and **Tailwind CSS** for the frontend, and integrates **Gemini AI APIs** for intelligent question generation and feedback.  

The workflow is straightforward:  
- The user selects a job role and starts a mock interview.  
- The frontend records audio/video responses using **MediaRecorder APIs**.  
- These responses are transcribed and sent to the backend, where **Gemini AI** evaluates them and returns structured feedback.  

I contributed to **authentication and AI integration**, implementing **Clerk authentication** for secure user management and handling **Gemini API calls** for question generation and feedback processing.  
The app also supports progress tracking and is deployed on **Vercel** for scalability and performance.  

👉 [Live Demo](https://prepify-ai-powered-mock-interview-p.vercel.app)

---

# 💬 Project-Based Interview Questions – Prepify (AI-Powered Mock Interview Platform)

---

## 1. **What was your role in this project?**

> I worked on the **frontend using Next.js and Tailwind CSS**, handled **authentication with Clerk**, and integrated **Gemini AI APIs** for question generation and feedback. I also implemented **media recording** using the MediaRecorder API to make the mock interviews realistic.

---

## 2. **How are interview questions generated?**

> The system uses **Gemini AI** to generate job-specific interview questions based on the user’s selected role. Gemini also provides **model answers**, which are shown at the end of the interview for better learning.

---

## 3. **How does feedback work in Prepify?**

> After the user finishes, their **audio/video responses are transcribed** using the browser’s Web Speech API. The text is then sent to **Gemini AI**, which provides feedback on communication, clarity, and technical depth.

---

## 4. **How did you handle user data and privacy?**

> No audio or video is stored. Everything is processed locally through the **MediaRecorder API**, and only the **transcribed text** is sent to the backend for AI analysis.

---

## 5. **What were the main challenges you faced?**

> I faced issues with **media permissions and browser compatibility**, especially for recording. Another challenge was **AI response latency**, which I handled by adding loading states for a smoother UX.

---

## 6. **Why did you choose Clerk for authentication?**

> **Clerk** integrates seamlessly with **Next.js** and offers pre-built, secure authentication flows with minimal setup. It simplified user login and session handling compared to Firebase or Auth0.

---

## 7. **Why Next.js, Tailwind, and Drizzle ORM?**

> **Next.js** gave us server-side rendering and fast routing, **Tailwind CSS** helped build a responsive UI quickly, and **Drizzle ORM** made database queries clean and type-safe with PostgreSQL.

---

## 8. **How is user progress tracked?**

> Each interview session’s data — questions, feedback, and scores — is stored in **PostgreSQL**. This lets users review their past sessions and track improvements.

---

## 9. **How does the transcription work?**

> The **Web Speech API** converts audio to text in real-time. The transcript is then cleaned and sent to **Gemini AI** for feedback generation.

---

## 10. **How did you ensure the app works across devices?**

> The UI is built with **responsive Tailwind utilities**, and I adjusted how media components behave on smaller screens to keep the interface consistent across mobile, tablet, and desktop.

---
