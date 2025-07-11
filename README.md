# Interactive_Button_Click_Tracker
## Date:11.07.2025
## Objective:
To implement a counter using JavaScript closures and demonstrate how variables maintain their state across function calls, emphasizing the concepts of function scope and lexical closures.

## Tasks:

#### 1. Structure the HTML Layout:
Create a simple interface with:

A heading like ```<h1>ClickCounter</h1>```

A ```<button>``` labeled “Click Me”

A ```<p> or <div>``` to display the number of clicks

#### 2. Style with CSS:
Center the layout and apply padding and background color

Use large fonts for the click display

Add hover effects on the button

#### 3. Write JavaScript with Closure:
Create a function createCounter() that returns another function

The inner function should increment and return a count variable stored in the outer function’s scope

Use this closure to track how many times the button has been clicked

Update the DOM each time the button is clicked using the closure function
## HTML Code:
```<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>ClickCounter</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>ClickCounter</h1>
    <button id="clickButton">Click Me</button>
    <p>Number of clicks: <span id="clickCount">0</span></p>
  </div>
  <script src="script.js"></script>
</body>
</html>
```
## CSS Code:
```
body {
  margin: 0;
  padding: 0;
  background-color: lightblue;
  font-family: Arial, sans-serif;
}

.container {
  text-align: center;
  padding: 100px;
}

h1 {
  font-size: 2.5em;
  color: #333;
}

button {
  font-size: 1.5em;
  padding: 10px 20px;
  cursor: pointer;
  background-color: lightgreen;
  color: white;
  border: none;
  border-radius: 8px;
  transition: background-color 0.3s;
}

button:hover {
  background-color:yellowgreen;
}

p {
  font-size: 1.8em;
  margin-top: 20px;
  color: #333;
}
```
## JavaScript Code:
```
function createCounter() {
  let count = 0; 
  return function() {
    count++;
    return count;
  }
}
const counter = createCounter();
const button = document.getElementById('clickButton');
const display = document.getElementById('clickCount');
button.addEventListener('click', function() {
  const currentCount = counter();
  display.textContent = currentCount;
});
```
## Output:
<img width="952" height="914" alt="image" src="https://github.com/user-attachments/assets/eba6b1e6-fac3-49fe-9873-8c6383c6eb66" />

## Result:
A mini module using JavaScript closure and scope is successfully implemented to build an interactive button click tracker that updates in real time without exposing internal variables.
