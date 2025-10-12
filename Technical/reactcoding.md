# React Counter 

## Code Overview
This is a simple **counter app** built using React functional components and the `useState` hook.  
It demonstrates **state management** and **two different ways of declaring functions** in React.

```javascript
import { useState } from "react";

export default function App() {
  const [count, setCount] = useState(0);

  // Arrow function syntax
  const incrementCount = () => {
    setCount(count + 1);
  };

  // Function declaration syntax
  function decrementCount() {
    setCount(count - 1);
  }

  return (
    <div className="App">
      <div>Counter : {count}</div>
      <button onClick={incrementCount}>Increment</button>
      <button onClick={decrementCount}>Decrement</button>
    </div>
  );
}
```

---

## Key Points

### useState
- `useState` is a **React hook** used to create a state variable and its setter.
- `count` is the current value.
- `setCount` is used to **update the state** and re-render the component.

### Function Declaration vs Arrow Function
| Feature               | Arrow Function (`()=>`)          | Function Declaration (`function`) |
|-----------------------|---------------------------------|---------------------------------|
| Syntax                | `const fn = () => {}`           | `function fn() {}`              |
| Hoisting              | Not hoisted                     | Hoisted                         |
| `this` context        | Inherits parent `this`          | Own `this`                      |


---
---

# React Toggle Switch – Two Approaches

## Approach 1 – Using String State

```javascript
import { useState } from "react";

export default function App() {
  const [toggle, setToggle] = useState("OFF");

  const change = () => {
    setToggle(toggle === "OFF" ? "ON" : "OFF");
  };

  return (
    <div>
      <div>{toggle}</div>
      <button onClick={change}>Toggle</button>
    </div>
  );
}
```

---

## Approach 2 – Using Boolean State

```javascript
import { useState } from "react";

export default function App() {
  const [toggle, setToggle] = useState(false);

  const change = () => {
    setToggle(!toggle);
  };

  return (
    <div>
      <div>{toggle ? "ON" : "OFF"}</div>
      <button onClick={change}>Toggle</button>
    </div>
  );
}
```
**Ternary Operator:** A concise one-line conditional: `condition ? valueIfTrue : valueIfFalse` (e.g., `toggle ? "ON" : "OFF"`).


---
---


# 📝 React To-Do List Example

```javascript
import "./styles.css";
import { useState } from "react";

export default function App() {
  const [list, setList] = useState([]);
  const [text, setText] = useState("");

  const addTodo = () => {
    if (text) {
      setList([...list, { text, completed: false }]);
      setText("");
    }
  };

  const removeTodo = (index) => {
    const newtodo = [...list];
    newtodo.splice(index, 1);
    setList(newtodo);
  };

  const toggleTodo = (index) => {
    const newtodo = [...list];
    newtodo[index].completed = !newtodo[index].completed;
    setList(newtodo);
  };

  return (
    <div className="App">
      <h1>Todo List</h1>
      <input
        type="text"
        placeholder="add todo"
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <button onClick={addTodo}>Add</button>
      <ul>
        {list.map((l, index) => (
          <li key={index} style={{ textDecoration: l.completed ? "line-through" : "none" }}>
            {l.text}
            <button onClick={() => removeTodo(index)}>Remove</button>
            <button onClick={() => toggleTodo(index)}>Toggle</button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

---

## 📌 Notes

- `useState` is used to store the **list of todos** and the **input text**.
- `[...list, newItem]` creates a **new array** by spreading the existing items and adding a new one.  
  This is **immutable update** pattern in React.
- `.map()` iterates over the `list` array to render `<li>` elements dynamically in the `<ul>`.
- `splice(index, 1)` removes an item from an array at a specific index.
- `list[index].completed = !list[index].completed` toggles the **completion status**.
# 📝 Common JavaScript Array Methods – Syntax

| Method | Syntax | Description |
|--------|--------|-------------|
| `push` | `arr.push(element1, element2, ...)` | Adds one or more elements to the **end** of the array. |
| `pop` | `arr.pop()` | Removes the **last element** of the array and returns it. |
| `shift` | `arr.shift()` | Removes the **first element** of the array and returns it. |
| `unshift` | `arr.unshift(element1, element2, ...)` | Adds one or more elements to the **start** of the array. |
| `splice` | `arr.splice(startIndex, deleteCount, item1, item2, ...)` | Removes, replaces, or adds elements at a specific **position**. |
| `slice` | `arr.slice(startIndex, endIndex)` | Returns a **new array** containing elements from `startIndex` to `endIndex - 1`. |
| `map` | `arr.map((element, index, array) => { ... })` | Creates a **new array** by applying a function to each element. |
| `filter` | `arr.filter((element, index, array) => { ... })` | Creates a **new array** with elements that **pass a test**. |
| `forEach` | `arr.forEach((element, index, array) => { ... })` | Executes a function for **each element**; does not return a new array. |
| `find` | `arr.find((element) => condition)` | Returns the **first element** that satisfies the condition. |
| `findIndex` | `arr.findIndex((element) => condition)` | Returns the **index of the first element** that satisfies the condition. |
| `includes` | `arr.includes(element)` | Checks if the array **contains a specific element**, returns true/false. |
| `indexOf` | `arr.indexOf(element)` | Returns the **first index** of the element, or -1 if not found. |
| `concat` | `arr1.concat(arr2, arr3, ...)` | Returns a **new array** by merging arrays. |
| `reverse` | `arr.reverse()` | Reverses the array **in place**. |
| `sort` | `arr.sort((a, b) => a - b)` | Sorts the array **in place** based on a comparison function. |
| `join` | `arr.join(separator)` | Combines array elements into a **string** with a separator. |
| `reduce` | `arr.reduce((acc, curr) => ..., initialValue)` | Reduces the array to a **single value** by applying a function. |

> ✅ **Tip:** Use methods like `map`, `filter`, `reduce` to **avoid mutating** the original array and follow React’s **immutable state update** practices.


---
---
