index.html

<!DOCTYPE html>

<html lang="en">

<head>

<link rel="stylesheet" href="styles.css">

<title>Survey App</title>

</head>

<body>

<div class="container">

<h1>Random Survey</h1>

<form id="surveyForm">

<div id="questionsContainer"></div>

<button type="button" onclick="loadQuestions()">Start Survey</button>

<button type="submit" id="submitSurvey" style="display:none;">Submit Survey</button>

</form>

</div>

<script src="script.js"></script>

</body>

</html>
body {

 font-family: Arial, sans-serif;

 background-color: #808080;

 margin: 0;

 display: flex;

 justify-content: center;

 align-items: center;

 height: 100vh;

}

.container {

 text-align: center;

 background-color: #7FFFD4;

 padding: 20px;

 border-radius: 8px;

 box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

}

button {

 margin: 10px;

 padding: 8px 16px;

 font-size: 16px;

 cursor: pointer;

}
.input-container{

margin-button: 30px;

}

.input-container label,

.input-container input {

margin-bottom: 10px;

}
const questions = [

 "What is your favorite color?",

 "How often do you exercise?",

 "What's your preferred programming language?",

 "Do you enjoy reading books?",

 "What's your favorite type of music?",

 "How many cups of coffee do you drink per day?",

 "What's your favorite movie ?",

 "Do you prefer summer or winter?",

 "Are you a morning person?",

 "What's your dream travel destination?"

];

const form = document.getElementById("surveyForm");

const questionsContainer = document.getElementById("questionsContainer");

const startSurveyButton = document.querySelector("button[onclick='loadQuestions()']");

const submitSurveyButton = document.getElementById("submitSurvey");
function loadQuestions() {

 // Clear previous questions

 questionsContainer.innerHTML = "";

 // Shuffle questions to get a random set

 const shuffledQuestions = questions.sort(() => Math.random() - 0.5);

 // Display all questions with input fields

 shuffledQuestions.forEach((question, index) => {

 const inputContainer = document.createElement("div");

 inputContainer.className = "input-container";

 const inputLabel = document.createElement("label");

 inputLabel.textContent = question;

 const input = document.createElement("input");

 input.type = "text";

 input.name = `answer${index}`;

 input.placeholder = "Your Answer";

 inputContainer.appendChild(inputLabel);

 inputContainer.appendChild(input);

 questionsContainer.appendChild(inputContainer);

 });

 // Hide the 'Start Survey' button and show the 'Submit Survey' button
startSurveyButton.style.display = "none";

 submitSurveyButton.style.display = "block";

}

form.addEventListener("submit", function (event) {

 event.preventDefault();

 // You can handle the form submission here, e.g., send data to a server.

 const answers = Array.from(document.querySelectorAll('input[type="text"]'))

 .map(input => input.value);

 if (answers.filter(answer => answer.trim() !== "").length === 5) {

 alert("Survey submitted successfully!");

 } else {

 alert("Please provide answer for 5 questions.");

 }

})
