# MWAD-EX_03-To-Do-List-using-JavaScript

```
NAME: V. POOJAA SREE
REG. NO: 212223040147

```

## Date:

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM:

```
main.jsx

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>,
)

```


```
App.jsx


import React, { useState } from "react";
import "./app.css"; // Import your styles

const App = () => {
  // State to store tasks
  const [tasks, setTasks] = useState([]);
  const [task, setTask] = useState(""); // Input field state

  // Add task
  const addTask = () => {
    if (task.trim() === "") return;
    setTasks([...tasks, { id: Date.now(), text: task, completed: false }]);
    setTask("");
  };

  // Toggle completion of task
  const toggleComplete = (id) => {
    setTasks(tasks.map((t) => t.id === id ? { ...t, completed: !t.completed } : t));
  };

  // Remove task
  const removeTask = (id) => {
    setTasks(tasks.filter((t) => t.id !== id));
  };

  return (
    <div className="todo-container">
      <h1>To-Do List</h1>
      <div className="input-section">
        <input
          type="text"
          value={task}
          onChange={(e) => setTask(e.target.value)}
          placeholder="Add a new task"
        />
        <button onClick={addTask}>Add</button>
      </div>
      <ul id="todo-list">
        {tasks.map((task) => (
          <li key={task.id} className={task.completed ? "completed" : ""}>
            <input
              type="checkbox"
              checked={task.completed}
              onChange={() => toggleComplete(task.id)}
            />
            <span>{task.text}</span>
            <button onClick={() => removeTask(task.id)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default App;

```

```
App.css


body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    padding: 50px;
  }
  
  .todo-container {
    background: #fff;
    padding: 30px;
    border-radius: 10px;
    width: 300px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  h1 {
    text-align: center;
  }
  
  .input-section {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
  }
  
  input[type="text"] {
    flex: 1;
    padding: 8px;
  }
  
  button {
    padding: 8px 12px;
    cursor: pointer;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    background-color: #eee;
    padding: 10px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  li.completed span {
    text-decoration: line-through;
    color: gray;
  }
  
  li button {
    background-color: red;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
  
  li input[type="checkbox"] {
    margin-right: 10px;
  }
  
```

## OUTPUT:

![o1](https://github.com/user-attachments/assets/38063f76-39c2-4eb4-af3c-fa495163992d)

![o2](https://github.com/user-attachments/assets/aa2ac22a-1d24-491f-9e8a-140bfcadd47b)

![o3](https://github.com/user-attachments/assets/f39013c0-bb25-4ac0-991e-607da167b827)



## RESULT:
The program for creating To-do list using JavaScript is executed successfully.
