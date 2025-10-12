**LearnPlay** is an **educational platform** that makes learning **engaging and fun** by turning topics into **interactive quizzes and games**.  
It was built using **React, TypeScript, and Tailwind CSS** for the **frontend** and **Spring Boot with Java 17** for the **backend**.  
For authentication and APIs, we implemented **JWT authentication** and **RESTful endpoints**.  

The **workflow** is straightforward:  

- The **user** interacts with the **frontend**, playing quizzes and tracking progress.  
- The **frontend** communicates with the **backend** through **REST APIs**.  
- The **backend** manages **user accounts**, **progress tracking**, and **content transformation into quizzes**, and sends the processed data back to the **frontend**.  

I contributed to the **frontend development**, where I worked with **React**, **TypeScript**, and **Tailwind CSS**.  
My focus was on building an **intuitive UI**, handling **API integration**, and ensuring **smooth state management** for user sessions and quiz progress.  

---

---

❓ **How did you handle API integration in the frontend?**  
✅ *Answer:*  
“I used **Axios** (or Fetch) to make REST API calls to the backend. For example, when a user logs in, the frontend sends credentials to the backend, receives a **JWT token**, and stores it in local storage. That token is then attached to subsequent API requests for authentication. I also handled loading states, errors, and response parsing to make the flow user-friendly.”  

---

❓ **How did you manage state between different components (like quiz progress, user data, etc.)?**  
✅ *Answer:*  
“I used **React hooks** like `useState` and `useEffect` for local component state and **Context API** to share global data like user info and quiz progress. This helped maintain synchronization between pages like Dashboard, Quiz, and Results without prop drilling.”  

---

❓ **How did you ensure responsiveness and good UI/UX design?**  
✅ *Answer:*  
“I used **Tailwind CSS** for responsive design — it made it easy to adjust layouts with breakpoints for mobile, tablet, and desktop. I also kept the design consistent using utility classes and followed clean spacing, typography, and accessibility practices.”  

---

❓ **What challenges did you face in frontend integration?**  
✅ *Answer:*  
“One issue I faced was **handling async data rendering**, where components tried to render before API responses arrived. I solved this by adding conditional rendering and loading states. Another challenge was keeping the UI consistent across devices, which I handled using Tailwind’s responsive utilities.”  

---

❓ **What did you learn from this project?**  
✅ *Answer:*  
“I learned how to build a **frontend that communicates effectively with REST APIs**, manage **authentication using JWT**, and design **responsive UIs** with Tailwind CSS. It strengthened my understanding of **state management** and **API-driven development** in React.”  
