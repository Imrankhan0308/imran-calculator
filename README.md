<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendOperator('/')">/</button>
            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendOperator('*')">*</button>
            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendOperator('-')">-</button>
            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="appendOperator('+')">+</button>
            <button onclick="appendNumber('0')">0</button>
            <button onclick="appendNumber('.')">.</button>
            <button class="equal" onclick="calculateResult()">=</button>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f5f5f5;
}

.calculator {
    width: 300px;
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

#display {
    width: 100%;
    height: 50px;
    background-color: #e6e6e6;
    border: none;
    text-align: right;
    font-size: 24px;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    width: 100%;
    padding: 20px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    background-color: #f2f2f2;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #ddd;
}

button:active {
    background-color: #ccc;
}

.equal {
    background-color: #4caf50;
    color: white;
}

.equal:hover {
    background-color: #45a049;
}
let display = document.getElementById('display');

// Append numbers to the display
function appendNumber(number) {
    display.value += number;
}

// Append operators to the display
function appendOperator(operator) {
    display.value += operator;
}

// Clear the display
function clearDisplay() {
    display.value = '';
}

// Delete the last character
function deleteLast() {
    display.value = display.value.slice(0, -1);
}

// Calculate the result of the expression
function calculateResult() {
    try {
        display.value = eval(display.value);
    } catch (error) {
        display.value = 'Error';
    }
}
