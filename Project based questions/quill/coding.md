[reactcoding.md](https://github.com/PurveshXtreme/Interview-Preparation/blob/main/Technical/reactcoding.md)

---
---

# 📦 How to Publish a React Package on npm

Follow these steps to upload your project (like `zapi-ui`) to npm.

---

### 🪜 Step 1: Create an npm account
1. Go to 👉 [https://www.npmjs.com/signup](https://www.npmjs.com/signup)
2. Verify your email.

---

### 🪜 Step 2: Log in from terminal
```bash
npm login
```
Enter your **username**, **password**, and **email**.

---

### 🪜 Step 3: Prepare your project
Make sure your folder structure is clean:
```
zapi-ui/
 ┣ src/
 ┣ package.json
 ┣ README.md
 ┣ .gitignore
 ┗ index.js (or main entry file)
```

Your `package.json` must include:
```json
{
  "name": "zapi-ui",
  "version": "1.0.0",
  "description": "A reusable React UI library",
  "main": "dist/index.js",
  "author": "Purvesh Jambhulkar",
  "license": "MIT",
  "keywords": ["react", "ui", "components"],
  "homepage": "https://github.com/purveshjambhulkar/zapi-ui"
}
```

✅ **Important:**
- Package name must be **unique** on npm.
- If taken, use scoped naming: `"name": "@purveshjambhulkar/zapi-ui"`

---

### 🪜 Step 4: Build your package
If it’s a React library:
```bash
npm run build
```
Ensure your `dist/` folder (or build output) is ready.

If you’re using tools like `Vite`, `Rollup`, or `tsup`, ensure the final compiled JS is in `dist/index.js`.

---

### 🪜 Step 5: Ignore unwanted files
Create `.npmignore` file (similar to `.gitignore`):
```
src/
node_modules/
.git/
dist/**/*.map
```

---

### 🪜 Step 6: Publish to npm
```bash
npm publish
```

If you’re using a scoped package (like `@purveshjambhulkar/zapi-ui`), use:
```bash
npm publish --access public
```

---

### 🪜 Step 7: Install and test your package
Once published, you can install it anywhere with:
```bash
npm install zapi-ui
```
or for scoped package:
```bash
npm install @purveshjambhulkar/zapi-ui
```

---

### 🧹 Optional: Update the package
If you make changes:
```bash
npm version patch
npm publish
```

Example:
- `patch` → 1.0.1  
- `minor` → 1.1.0  
- `major` → 2.0.0

---
---

# Using zapi-ui in our project



