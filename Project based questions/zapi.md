
**ZAPI-UI** is a **React component library** that is also **published as an npm package**. It provides **customizable components** like **Avatar, Button, Carousel, Checkbox, Input**, and more. The library is built with **plain CSS** to keep it **lightweight** and **easy to integrate** into any project.

My contributions to this project include **building some components** like the **Button** and **Avatar**. My main focus was **handling the npm workflow** for the library — I **published it on npm**, making it easy for developers to install and use via `npm install zapi-ui`.

From this project, I **learned how npm packages work** and how to **create and publish my own npm package**, gaining hands-on experience in distributing reusable libraries.



---
---


❓ **What challenges did you face, and how did you solve them?**

✅ *Answer:*  
“One challenge I faced was when I tried to **publish an updated version of the library on npm**. After making changes and attempting to publish again, I got an error. I realized this happens because **npm requires the version in `package.json` to be incremented** for each new release. I solved this by updating the version number, and then I was able to successfully publish the updated package.”

---
❓ **Why did you choose plain CSS instead of Tailwind or styled-components?**

✅ *Answer:*  
“We chose **plain CSS** to keep the library **lightweight and framework-independent**. This makes it easier for developers to integrate the components into any React project without needing additional dependencies or learning a new styling framework.”

---

❓ **How does a user integrate ZAPI-UI into their project? (Installation/usage flow)**

✅ *Answer:*  
“Integration is simple. First, the developer installs the library using `npm install zapi-ui` or `yarn add zapi-ui`. Then they import the CSS file: `import 'zapi-ui/dist/index.css';`. After that, they can import and use any component directly in their React code, for example: `import { Checkbox } from 'zapi-ui';` and use it like any standard React component.”

---

❓ **What steps did you take to make the components customizable?**

✅ *Answer:*  
“We made the components **customizable via props and the `className` attribute**. This allows developers to change styling, add custom classes, or override default styles easily. Each component is designed to be flexible while still maintaining accessibility and consistent behavior across projects.”

---
