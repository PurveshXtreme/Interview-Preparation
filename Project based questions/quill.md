
**Quill AI** is a platform that **summarizes large text** into **concise outputs**.  
It was built using **HTML, CSS, and JavaScript** for the **frontend** and **Python** for the **backend**.  
For summarization, we integrated **pre-trained LLMs from Hugging Face**.  

The **workflow** is straightforward:  
- The **user** enters text on the **frontend**, which then sends it to the **backend**.  
- The **backend** passes the text to the **LLM**, which generates the **summary**.  
- The **summarized output** is finally displayed back on the **screen**.  

I contributed to the **frontend development**, where I built the interface using **HTML, CSS, and JavaScript**.  
My focus was on creating a **simple** and **user-friendly design** so that users can easily input their text and view the **summarized output**.  


---
---

❓ Why did you choose these technologies?

✅ Answer:
“For the frontend, I used HTML, CSS, and JavaScript because they’re reliable, lightweight, and well-suited for building responsive interfaces. For the backend, we used Python since it has strong support for AI libraries and made it easier to integrate Hugging Face LLMs.”

---

❓ What did you learn from this project?

✅ Answer:
“I learned how to design a user-friendly frontend that interacts with an AI model. It improved my frontend development skills, gave me exposure to integrating with backends, and also taught me the importance of team collaboration and thinking from a user’s perspective.”

---

❓ What challenges did you face in this project?

✅ Answer:
“One challenge I faced was making the frontend responsive. At first, the website didn’t look good on different screen sizes, like smaller laptops or mobile screens. To solve this, I adjusted the CSS styling and tested the layout across different devices. This made the interface look consistent and user-friendly no matter what screen size the user was on.”

---

❓ Interviewer asks: “Why is Flask there if you said you used HTML, CSS, and JS?”

✅ Answer:
“Yes, you’re right, the backend is built with Flask. My main contribution was in the frontend, where I developed the interface using HTML, CSS, and JavaScript. Later, my teammate working on the backend integrated the frontend with Flask so that it could interact directly with the Hugging Face model. So while the Flask part was handled by my teammate, my focus was on making sure the UI remained simple, responsive, and user-friendly.”

---
---

### Project-Specific Questions – Quill AI

---

#### ❓ Which Hugging Face model did you use?  
**Answer:**  
“We integrated a **pre-trained Hugging Face summarization model**, such as `facebook/bart-large-cnn`. This model is designed for text summarization and can handle long passages efficiently, generating concise outputs that retain key points.”

---

#### ❓ How does this model summarize the text?  
**Answer:**  
“The model reads the input text and uses a **transformer-based architecture** to understand the context. It identifies important sentences and phrases and generates a concise summary, predicting the most relevant words for the output.”

---

#### ❓ How does the frontend communicate with the backend and vice versa?  
**Answer:**  
“The **frontend sends the user’s input text** to the backend using a **POST request** (via the form). The backend receives this text, passes it to the summarization model, and then the **summarized text is sent back** to the frontend. On the frontend, we display the summary in a dedicated output section.”

---

#### ❓ How did you ensure that the summarized text is placed properly on the frontend?  
**Answer:**  
“I created a **dedicated container** for the summarized text using HTML and CSS, separate from the input box. I also used scrollable divs for long summaries and consistent styling so that the output is clearly visible and easy to read for users.”

---

#### ❓ Did you preprocess the text before sending it to the backend?  
**Answer:**  
“From the frontend side, we performed **minimal preprocessing**—mainly trimming extra spaces and ensuring the input isn’t empty. The backend model can handle most formatting, so additional preprocessing wasn’t necessary.”

---
---


