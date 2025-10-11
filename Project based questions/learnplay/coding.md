# Interview Preparation Guide - Table of Contents

## 📚 Quick Navigation

### [1. JWT (JSON Web Token)](#jwt-json-web-token)
- [1.1 What is JWT and why do we use it?](#11-what-is-jwt-and-why-do-we-use-it)
- [1.2 Generate a JWT Token in Java](#12-generate-a-jwt-token-in-java)
- [1.3 Validate a JWT Token](#13-validate-a-jwt-token)
- [1.4 JWT Storage and Transmission](#14-jwt-storage-and-transmission)
- [1.5 JWT Authentication Flow](#15-jwt-authentication-flow)

### [2. CRUD Operations](#crud-operations)
- [2.1 What is CRUD?](#21-what-is-crud)
- [2.2 User Entity Example](#22-user-entity-example)
- [2.3 Repository Layer](#23-repository-layer)
- [2.4 Controller Example (Basic CRUD)](#24-controller-example-basic-crud)
- [2.5 Possible Interview Questions](#25-possible-interview-questions)
- [2.6 Simple Flow](#26-simple-flow)

### [3. API Integration / REST Calls](#api-integration--rest-calls)
- [3.1 What is API Integration?](#31-what-is-api-integration)
- [3.2 REST Controller Example (Spring Boot)](#32-rest-controller-example-spring-boot)
- [3.3 Frontend API Call (React)](#33-frontend-api-call-react)
- [3.4 Integration Flow](#34-integration-flow)
- [3.5 Possible Interview Questions](#35-possible-interview-questions)
- [3.6 Summary Flow](#36-summary-flow)

### [4. Spring AI + Gemini API](#spring-ai--gemini-api)
- [4.1 What is Spring AI?](#41-what-is-spring-ai)
- [4.2 Gemini AI Integration with Backend](#42-gemini-ai-integration-with-backend)
- [4.3 Possible Interview Questions](#43-possible-interview-questions)
- [4.4 End-to-End Flow Summary](#44-end-to-end-flow-summary)

---

## JWT (JSON Web Token)

### 1.1 What is JWT and why do we use it?

**Answer (short and natural):**

JWT stands for **JSON Web Token**. It's used to securely transfer user information between the client and server after authentication.  
Once the user logs in, the server generates a token that the client includes in every request.  
The server validates this token instead of storing sessions, which makes it **stateless and scalable**.

---

### 1.2 Generate a JWT Token in Java

**Coding Task:**

> "Write a function to generate a JWT token after login."

```java
import io.jsonwebtoken.Jwts;
import io.jsonwebtoken.SignatureAlgorithm;
import java.util.Date;

public class JwtUtil {

    private static final String SECRET_KEY = "mysecretkey";

    public static String generateToken(String username) {
        return Jwts.builder()
                .setSubject(username)
                .setIssuedAt(new Date())
                .setExpiration(new Date(System.currentTimeMillis() + 1000 * 60 * 60)) // 1 hour expiry
                .signWith(SignatureAlgorithm.HS256, SECRET_KEY)
                .compact();
    }
}
```

---

### 1.3 Validate a JWT Token

**Coding Task:**

> "Now how will you validate this token?"

```java
import io.jsonwebtoken.Claims;
import io.jsonwebtoken.Jwts;
import io.jsonwebtoken.SignatureException;
import java.util.Date;

public class JwtUtil {

    private static final String SECRET_KEY = "mysecretkey";

    public static boolean validateToken(String token, String username) {
        try {
            Claims claims = Jwts.parser()
                    .setSigningKey(SECRET_KEY)
                    .parseClaimsJws(token)
                    .getBody();

            return claims.getSubject().equals(username) && claims.getExpiration().after(new Date());
        } catch (SignatureException e) {
            return false;
        }
    }
}
```

---

### 1.4 JWT Storage and Transmission

**Question:**

> "Where is JWT stored and how is it sent to the backend?"

**Answer:**

The JWT is usually stored on the client side — either in **localStorage** or a **secure HTTP-only cookie**.  
Every time the client makes a request, it sends the token in the **Authorization header** like:  
`Authorization: Bearer <token>`.  
The backend validates this token before allowing access to protected APIs.

---

### 1.5 JWT Authentication Flow

**Flow (Short Version):**

1️⃣ **User Login:**  
User enters credentials → frontend sends them to backend.  

2️⃣ **Verify & Generate Token:**  
Spring Boot checks credentials → if valid, generates a JWT token.  

3️⃣ **Send Token to Client:**  
Backend sends token → frontend stores it (usually in localStorage or cookie).  

4️⃣ **Include Token in Requests:**  
Frontend adds token in every API request header:  
```
Authorization: Bearer <token>
```

5️⃣ **Validate Token:**  
Backend validates token's signature & expiry before giving access.  

6️⃣ **Access Granted:**  
If valid, user can access protected routes; else 403 Forbidden.  

**Flow Summary:**  
👉 Login → Token Created → Sent → Stored → Verified → Access Granted ✅

---

## CRUD Operations

### 2.1 What is CRUD?

CRUD stands for **Create, Read, Update, Delete** — the four basic operations for managing data in an application.

---

### 2.2 User Entity Example

A simple **User** model for authentication or role-based access.

```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private String email;
    private String role;
}
```

---

### 2.3 Repository Layer

```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface UserRepository extends JpaRepository<User, Long> {
    User findByEmail(String email);
}
```

---

### 2.4 Controller Example (Basic CRUD)

```java
import org.springframework.web.bind.annotation.*;
import java.util.List;

@RestController
@RequestMapping("/api/users")
public class UserController {

    private final UserRepository userRepo;

    public UserController(UserRepository userRepo) {
        this.userRepo = userRepo;
    }

    // CREATE
    @PostMapping
    public User addUser(@RequestBody User user) {
        return userRepo.save(user);
    }

    // READ
    @GetMapping
    public List<User> getAllUsers() {
        return userRepo.findAll();
    }

    // UPDATE
    @PutMapping("/{id}")
    public User updateUser(@PathVariable Long id, @RequestBody User updatedUser) {
        return userRepo.findById(id).map(user -> {
            user.setName(updatedUser.getName());
            user.setRole(updatedUser.getRole());
            return userRepo.save(user);
        }).orElseThrow(() -> new RuntimeException("User not found"));
    }

    // DELETE
    @DeleteMapping("/{id}")
    public void deleteUser(@PathVariable Long id) {
        userRepo.deleteById(id);
    }
}
```

---

### 2.5 Possible Interview Questions

- "Can you explain how CRUD operations work in your backend?"  
- "How do you handle errors if an ID doesn't exist?"  
- "What's the difference between `@RequestBody` and `@PathVariable`?"  
- "How does Spring Data JPA simplify CRUD operations?"  
- "How do you connect CRUD with the frontend (React)?"  

---

### 2.6 Simple Flow

Frontend → sends request (POST/GET/PUT/DELETE) →  
Backend (Spring Boot) → interacts with DB via JPA →  
Response → JSON → Frontend updates UI ✅

---

## API Integration / REST Calls

### 3.1 What is API Integration?

API integration is the process of connecting the **frontend (React)** with the **backend (Spring Boot)** using **HTTP requests** like GET, POST, PUT, DELETE.

It allows the frontend to send data to the backend or fetch data dynamically.

---

### 3.2 REST Controller Example (Spring Boot)

```java
@RestController
@RequestMapping("/api/quiz")
public class QuizController {

    @PostMapping("/generate")
    public String generateQuiz(@RequestBody QuizRequest request) {
        // Logic to generate quiz using Gemini API
        return "Quiz generated for topic: " + request.getTopic();
    }

    @GetMapping("/questions")
    public List<String> getQuestions() {
        return List.of("Q1: What is AI?", "Q2: Define Machine Learning");
    }
}
```

---

### 3.3 Frontend API Call (React)

```javascript
import axios from "axios";

async function fetchQuestions() {
  try {
    const response = await axios.get("http://localhost:8080/api/quiz/questions");
    console.log(response.data);
  } catch (error) {
    console.error("Error fetching quiz data:", error);
  }
}
```

- `axios.get()` → Fetch data  
- `axios.post()` → Send data  
- `try-catch` → Handle errors safely  

---

### 3.4 Integration Flow

1. User clicks "Generate Quiz" on React app  
2. React sends a **POST** request to Spring Boot (`/api/quiz/generate`)  
3. Spring Boot processes data and calls Gemini API  
4. Response (JSON) is sent back to React  
5. React updates UI to display generated questions ✅  

---

### 3.5 Possible Interview Questions

- "How does your frontend communicate with the backend?"
- "Which library did you use for API calls?" → **Axios / Fetch API**
- "What kind of data format is exchanged between frontend and backend?" → **JSON**
- "How do you handle API errors or failed responses?"
- "How do you secure API endpoints?" → (JWT Authentication)

---

### 3.6 Summary Flow

```
React (Frontend)
   ↓   REST API call (Axios)
Spring Boot (Backend)
   ↓
Gemini API (External AI)
   ↓
Response → React → Display on UI
```

---

## Spring AI + Gemini API

### 4.1 What is Spring AI?

**Question:** 
"What is Spring AI and how did you use it in your project?"

**Answer:**
Spring AI is a framework that simplifies integrating AI models into Spring Boot applications.  
In my project, I used Spring AI to connect with **Google's Gemini API** and process user prompts to generate quiz questions or explanations dynamically.  
It allowed me to easily call AI endpoints, handle responses, and integrate results into my backend logic.

---

### 4.2 Gemini AI Integration with Backend

**Question:**
"How did you integrate Gemini AI with your backend?"

**Answer (in simple flow):**
1. Created a service class in Spring Boot.
2. Sent user input from the frontend to the backend (via REST API).
3. The backend called Gemini API using Spring AI or an HTTP client (like `RestTemplate` or `WebClient`).
4. The Gemini API returned the generated content, which was then sent back to the frontend.

**Example (simplified code):**
```java
@Service
public class GeminiService {

    private static final String GEMINI_API_URL = "https://generativelanguage.googleapis.com/v1/models/gemini-pro:generateContent";
    private static final String API_KEY = "YOUR_API_KEY";

    public String generateQuiz(String topic) {
        // call to Gemini API via WebClient
        WebClient client = WebClient.create(GEMINI_API_URL + "?key=" + API_KEY);

        String prompt = "Generate 3 quiz questions about " + topic;

        return client.post()
                .bodyValue(Map.of("contents", List.of(Map.of("parts", List.of(Map.of("text", prompt))))))
                .retrieve()
                .bodyToMono(String.class)
                .block();
    }
}
```

---

### 4.3 Possible Interview Questions

- "Why did you choose Gemini API over OpenAI or others?"
  - It's **lightweight**, integrates easily with **Spring AI**, and has strong support for **educational content generation**.

- "What kind of data did you send to Gemini?"
  - I sent **user prompts** like topic names or learning goals, and Gemini returned **text-based quiz questions or summaries**.

- "How do you handle API keys securely?"
  - By storing them in **environment variables** or **application.properties**, never hardcoding them in code.

- "How do you handle slow or failed AI responses?"
  - Using **timeouts**, **try-catch blocks**, and **fallback responses** (like predefined messages).

---

### 4.4 End-to-End Flow Summary

```
Frontend (React)
   ↓ user enters topic
Spring Boot Backend
   ↓ sends prompt to Gemini API via Spring AI
Gemini API
   ↓ returns AI-generated quiz
Spring Boot
   ↓ sends response to frontend
React displays generated quiz to user ✅
```

---

