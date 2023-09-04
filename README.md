# To-do-List
# It is one of the easiest solutions for task management and delivers a comfortable and smart way of handling tasks an individual wishes to accomplish.This To-Do List web application is an application for keeping a record of tasks that need to be completed and is typically arranged in order of importance.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 600px;
            margin: 20px auto;
            background-color: #fff;
            padding: 20px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
            border-radius: 5px;
            text-align: center;
        }
        .add-task {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        .add-task input[type="text"] {
            flex: 1;
            padding: 10px;
        }
        .add-task button {
            background-color: #333;
            color: #fff;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
        }
        ul {
            list-style: none;
            padding: 0;
        }
        li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f0f0f0;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 5px;
        }
        li.completed {
            background-color: #c8e6c9;
            text-decoration: line-through;
        }
        li button {
            background-color: #f44336;
            color: #fff;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <div class="add-task">
            <input type="text" id="task" placeholder="Add a new task...">
            <button id="addBtn">Add</button>
        </div>
        <ul id="taskList">
            <!-- Tasks will be added here dynamically using JavaScript -->
        </ul>
    </div>
    <script>
        const taskInput = document.getElementById("task");
        const addBtn = document.getElementById("addBtn");
        const taskList = document.getElementById("taskList");
        addBtn.addEventListener("click", addTask);
        taskList.addEventListener("click", handleTaskClick);
        function addTask() {
            const taskText = taskInput.value.trim();
            if (taskText !== "") {
                const newTask = document.createElement("li");
                newTask.textContent = taskText;
                const deleteBtn = document.createElement("button");
                deleteBtn.textContent = "Delete";
                deleteBtn.className = "delete-button";
                newTask.appendChild(deleteBtn);
                taskList.appendChild(newTask);
                taskInput.value = "";
            }
        }
        function handleTaskClick(event) {
            if (event.target.classList.contains("delete-button")) {
                event.target.parentElement.remove();
            } else if (event.target.tagName === "LI") {
                event.target.classList.toggle("completed");
            }
        }
    </script>
</body>
</html>
#![Screenshot (143)](https://github.com/Monica-3/To-do-List/assets/101280403/62ab4c8d-4bc9-4de0-b045-26fa0f5382b2)
#![Screenshot (144)](https://github.com/Monica-3/To-do-List/assets/101280403/a9ff499e-bf56-491f-ac8f-11dca3d36614)
