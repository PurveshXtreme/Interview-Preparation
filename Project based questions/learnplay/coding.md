## JWT based Questions

⚙️ **1️⃣ Basic: “What is JWT and why do we use it?”**

**Answer (short and natural):**

JWT stands for **JSON Web Token**. It’s used to securely transfer user information between the client and server after authentication.  
Once the user logs in, the server generates a token that the client includes in every request.  
The server validates this token instead of storing sessions, which makes it **stateless and scalable**.

---

💻 **2️⃣ Coding Task: Generate a JWT Token in Java**

They may say:

> “Write a function to generate a JWT token after login.”

Here’s a simple version (no bluff, realistic code):

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

🧾 **3️⃣ Coding Task: Validate a JWT Token**

They might follow up:

> “Now how will you validate this token?”

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

🔐 **4️⃣ Explanation-based Question:**

> “Where is JWT stored and how is it sent to the backend?”

**Answer:**

The JWT is usually stored on the client side — either in **localStorage** or a **secure HTTP-only cookie**.  
Every time the client makes a request, it sends the token in the **Authorization header** like:  
`Authorization: Bearer <token>`.  
The backend validates this token before allowing access to protected APIs.

---

### 🔐 **JWT Authentication Flow (Short Version)**

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
Backend validates token’s signature & expiry before giving access.  

6️⃣ **Access Granted:**  
If valid, user can access protected routes; else 403 Forbidden.  

---

**Flow Summary:**  
👉 Login → Token Created → Sent → Stored → Verified → Access Granted ✅

---

## Crud Operations

## ⚙️ CRUD Operations (Spring Boot – LearnPlay / AtLease Backend)

### 🧠 1️⃣ What is CRUD?
CRUD stands for **Create, Read, Update, Delete** — the four basic operations for managing data in an application.

---

### 💡 2️⃣ Example: User Entity
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

### 🛠️ 3️⃣ Repository Layer
```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface UserRepository extends JpaRepository<User, Long> {
    User findByEmail(String email);
}
```

---

### 🌐 4️⃣ Controller Example (Basic CRUD)

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

### 🧩 5️⃣ Possible Interview Questions

- "Can you explain how CRUD operations work in your backend?"  
- "How do you handle errors if an ID doesn’t exist?"  
- "What’s the difference between `@RequestBody` and `@PathVariable`?"  
- "How does Spring Data JPA simplify CRUD operations?"  
- "How do you connect CRUD with the frontend (React)?"  

---

### 🔁 Simple Flow
Frontend → sends request (POST/GET/PUT/DELETE) →  
Backend (Spring Boot) → interacts with DB via JPA →  
Response → JSON → Frontend updates UI ✅

---

## 🌐 API Integration / REST Calls (LearnPlay – Full Stack Flow)

### 🧠 1️⃣ What is API Integration?
API integration is the process of connecting the **frontend (React)** with the **backend (Spring Boot)** using **HTTP requests** like GET, POST, PUT, DELETE.

It allows the frontend to send data to the backend or fetch data dynamically.

---

### ⚙️ 2️⃣ Example REST Controller (Spring Boot)

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

### ⚛️ 3️⃣ Frontend API Call (React)

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

### 🔄 4️⃣ Integration Flow

1. User clicks “Generate Quiz” on React app  
2. React sends a **POST** request to Spring Boot (`/api/quiz/generate`)  
3. Spring Boot processes data and calls Gemini API  
4. Response (JSON) is sent back to React  
5. React updates UI to display generated questions ✅  

---

### 💬 5️⃣ Possible Interview Questions

- “How does your frontend communicate with the backend?”
- “Which library did you use for API calls?” → **Axios / Fetch API**
- “What kind of data format is exchanged between frontend and backend?” → **JSON**
- “How do you handle API errors or failed responses?”
- “How do you secure API endpoints?” → (JWT Authentication)

---

### 🧭 6️⃣ Summary Flow

```
React (Frontend)
   ↓   REST API call (Axios)
Spring Boot (Backend)
   ↓
Gemini API (External AI)
   ↓
Response → React → Display on UI
```






