# Ex03 To-Do List using JavaScript
## Date:17/11/2026

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

## PROGRAM

### HTML
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My To-Do List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">

        <h1>My To-Do List</h1>
        <p class="subtitle">Plan your day and stay productive!</p>

        <div class="input-section">
            <input type="text" id="taskInput"
                   placeholder="Enter your task here...">
            <button id="addButton">Add Task</button>
        </div>

        <h2>My Tasks</h2>

        <ul class="task-list" id="taskList">
            <!-- User tasks will appear here -->
        </ul>

        <p class="empty-message" id="emptyMessage">
            No tasks yet! Add your first task.
        </p>

        <footer>
            <p>Designed by: Akashini V</p>
            <p>Register Number: 212225230009</p>
        </footer>

    </div>

    <script src="script.js"></script>

</body>
</html>
```
### CSS
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    background: white;
    width: 420px;
    padding: 30px;
    border-radius: 15px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.2);
}

h1 {
    text-align: center;
    color: #5b4baf;
    margin-bottom: 10px;
}

.subtitle {
    text-align: center;
    color: gray;
    margin-bottom: 25px;
}

.input-section {
    display: flex;
    gap: 10px;
    margin-bottom: 25px;
}

input[type="text"] {
    flex: 1;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 5px;
    outline: none;
}

input[type="text"]:focus {
    border-color: #667eea;
}

button {
    padding: 12px 15px;
    background: #667eea;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: #764ba2;
}

h2 {
    color: #444;
    margin-bottom: 15px;
}

.task-list {
    list-style: none;
}

.task-list li {
    background: #f3f3ff;
    padding: 12px;
    margin-bottom: 10px;
    border-radius: 5px;
    display: flex;
    align-items: center;
    gap: 10px;
    overflow-wrap: anywhere;
}

.task-list li span {
    flex: 1;
}

.task-list input {
    cursor: pointer;
}

.delete-btn {
    background: #e74c3c;
    padding: 7px 10px;
}

.delete-btn:hover {
    background: #c0392b;
}

.empty-message {
    text-align: center;
    color: gray;
    padding: 15px 0;
}

footer {
    text-align: center;
    margin-top: 25px;
    padding-top: 15px;
    border-top: 1px solid #ddd;
    color: #666;
    font-size: 14px;
    line-height: 1.8;
}
```
### JAVASCRIPT
```
const taskInput = document.getElementById("taskInput");
const addButton = document.getElementById("addButton");
const taskList = document.getElementById("taskList");
const emptyMessage = document.getElementById("emptyMessage");

// Function to add a task
function addTask() {

    const taskText = taskInput.value.trim();

    if (taskText === "") {
        alert("Please enter a task!");
        return;
    }

    // Create list item
    const li = document.createElement("li");

    // Create checkbox
    const checkbox = document.createElement("input");
    checkbox.type = "checkbox";

    // Create task text
    const span = document.createElement("span");
    span.textContent = taskText;

    // Mark task as completed
    checkbox.addEventListener("change", function() {
        if (checkbox.checked) {
            span.style.textDecoration = "line-through";
            span.style.color = "gray";
        } else {
            span.style.textDecoration = "none";
            span.style.color = "black";
        }
    });

    // Create delete button
    const deleteButton = document.createElement("button");
    deleteButton.textContent = "Delete";
    deleteButton.className = "delete-btn";

    deleteButton.addEventListener("click", function() {
        li.remove();
        updateMessage();
    });

    // Add elements to list
    li.appendChild(checkbox);
    li.appendChild(span);
    li.appendChild(deleteButton);

    taskList.appendChild(li);

    // Clear input
    taskInput.value = "";

    updateMessage();
}

// Show or hide empty message
function updateMessage() {
    if (taskList.children.length === 0) {
        emptyMessage.style.display = "block";
    } else {
        emptyMessage.style.display = "none";
    }
}

// Button click event
addButton.addEventListener("click", addTask);

// Enter key event
taskInput.addEventListener("keypress", function(event) {
    if (event.key === "Enter") {
        addTask();
    }
});

// Initial empty state
updateMessage();
```

## OUTPUT
<img width="1917" height="1012" alt="Screenshot 2026-11-17 154552" src="https://github.com/user-attachments/assets/9a7dc6d6-a4a7-402d-ba2c-9afbb222e44d" />


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
