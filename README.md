<!DOCTYPE html>

<html lang="en">

<head>

 <meta charset="UTF-8">

 <style>

body {

 font-family: 'cursive', sans-serif;

 background-color: lightgreen;

 margin: 0;

 padding: 0;

 display: flex;

 align-items: center;

 justify-content: center;

 height: 100vh;

}

.container {

 max-width: 600px;

 background-color: #fff;

 padding: 20px;
border-radius: 8px;

 box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

}

.sell,

.buy {

 margin-top: 20px;

}

button {

 background-color: #4caf50;

 color: #fff;

 border: none;

 padding: 10px;

 cursor: pointer;

 border-radius: 4px;

}

button:hover {

 background-color: #45a049;

}

 </style>

 <title>Buy and Sell App</title>

</head>

<body>

 <div class="container">

 <h1>Buy and Sell App</h1>

 <div class="sell">
<h2>Sell</h2>

 <input type="text" id="sellInput" placeholder="Enter product to sell">

 <button onclick="sellProduct()">Sell</button>

 <ul id="sellList"></ul>

 </div>

 <div class="buy">

 <h2>Buy </h2>

 <ul id="buyList"></ul>

 </div>

 </div>

 <script>

 // script.js

function sellProduct() {

 const sellInput = document.getElementById('sellInput');

 const sellList = document.getElementById('sellList');

 const buyList = document.getElementById('buyList');

 const product = sellInput.value.trim();

 if (product !== '') {

 const listItem = document.createElement('li');

 listItem.textContent = product;

 const buyButton = document.createElement('button');

 buyButton.textContent = 'Buy';

 buyButton.onclick = function () {

 buyList.appendChild(listItem);

 listItem.removeChild(buyButton); // Remove the "Buy" button after buying
};

 listItem.appendChild(buyButton);

 sellList.appendChild(listItem);

 sellInput.value = '';

 }

}

 </script>

</body>

</html>
