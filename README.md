<!DOCTYPE html>

<html lang=” en”>

<head>

<meta charset=” UTF-8”>

<meta name=”viewport” content=”width=device-width, initial-scale=1.0”>

<link rel=”stylesheet” type=”text/css” href=”styles.css”>

<title>Project Management Dashboard</title>

</head>

<body>

<header>

<h1>Project Management Dashboard</h1>

</header>

<main>

<section id=”task-list”>

<h2>Task List</h2>

<div class=”task-card”>

<h3>Task 1</h3>

<p>Description of Task 1.</p>

<div class=”status”>
<span>Status: </span>

<select class=”status-select”>

<option value=”Pending”>Pending</option>

<option value=”InProgress”>InProgress</option>

<option value=”Completed”>Completed</option>

</select>

</div>

</div>

</section>

<section id=”add-task”>

<h2>Add New Task</h2>

<div class=”task-title”>

<input type=”text” id=”task-title” placeholder=”Task Title”></div>

<div class=”task-description”>

<textarea id=”task-description” placeholder=”Task Description”></textarea></div>

<button id=”add-button”>Add Task</button>

</section>

</main>

<footer>

<p>&copy; 2023 Project Management Dashboard</p>

</footer>

<script src=”script.js”></script>

</body>

</html>
body {

Font-family: Arial, sans-serif;

Margin: 0;
Padding: 0;

background-color: #f0f0f0;

}

header {

background-color: #333;

color: white;

padding: 20px;

text-align: center;

}

main {

max-width: 800px;

margin: 0 auto;

padding: 20px;

}

.task-card {

border: 1px solid #ccc;

padding: 10px;

margin: 10px 0;

border-radius: 5px;

}

.status-select {

background-color: #fff;

color: #333;

border: 1px solid #ccc;

padding: 5px;

border-radius: 5px;

}

#add-task {
background-color: white;

border-radius: 5px;

box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);

padding: 20px;

}

#add-button {

background-color: #007bff;

color: white;

border: none;

padding: 5px 10px;

border-radius: 5px;

cursor: pointer;

}

.task-title{

padding:5px;

border-radius:5px;

}

.task-description{

padding:5px;

border-radius:5px;

}

const tasks = [

{title: "TASK 1 - Research paper on Artificial Intelligence", description: "Write a research paper 

exploring the benefits and challenges of Artificial Intelligence", status: "Pending"},

{title: "TASK 2 - Seminar presentation on Quantum Computing", description: "Research, prepare and 

deliver a seminar on the principles, advancement and potential applications of Quantum Computing", 

status: "InProgress"},
];

// Function to render the task list

function renderTaskList() {

const taskList = document.getElementById(“task-list”);

// Clear the existing task list

taskList.innerHTML = “ ”;

// Loop through tasks and create task cards

tasks.forEach((task, index) => {

const taskCard = document.createElement(“div”);

taskCard.className = “task-card”;

taskCard.innerHTML = `

<h3>${task.title}</h3>

<p>${task.description}</p>

<div class=”status”>

<span>Status: </span>

<select class=”status-select” data-index=”${index}”>

<option value=”Pending” ${task.status === “Pending” ? “selected” : “”}>Pending</option>

<option value=”InProgress” ${task.status === “InProgress” ? “selected” : “”}>InProgress</option>

<option value=”Completed” ${task.status === “Completed” ? “selected” : “”}>Completed</option>

</select>

</div>

`;

taskList.appendChild(taskCard);

});

// Add event listeners to status selects

const statusSelects = document.querySelectorAll(“.status-select”);

statusSelects.forEach((select) => {

select.addEventListener(“change”, updateTaskStatus);
});

}

// Function to update task status

function updateTaskStatus(event) {

const index = event.target.getAttribute(“data-index”);

const newStatus = event.target.value;

tasks[index].status = newStatus;

renderTaskList(); // Re-render the task list to reflect the updated status

}

// Function to add a new task

function addNewTask() {

const taskTitle = document.getElementById(“task-title”).value;

const taskDescription = document.getElementById(“task-description”).value;

if (taskTitle && taskDescription) {

atsks.push({ title: taskTitle, description: taskDescription, status: “Pending” });

renderTaskList(); // Re-render the task list to include the new task

document.getElementById(“task-title”).value = “”; // Clear input

document.getElementById(“task-description”).value = “”; // Clear input

}

}

// Add event listener to the “Add Task” button

document.getElementById(“add-button”).addEventListener(“click”, addNewTask);

// Initial rendering of the task list

renderTaskList();
