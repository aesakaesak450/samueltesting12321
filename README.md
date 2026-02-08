<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendValue('/')">÷</button>
        <button onclick="appendValue('*')">×</button>
        <button onclick="deleteLast()">⌫</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button onclick="appendValue('-')">−</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('+')">+</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="calculateResult()" class="equals">=</button>

        <button onclick="appendValue('0')" class="zero">0</button>
        <button onclick="appendValue('.')">.</button>
    </div>
</div>

<script src="script.js"></script>
</body>
</html>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #1e1e1e;
    font-family: Arial, sans-serif;
}

.calculator {
    background: #2c2c2c;
    padding: 20px;
    border-radius: 10px;
    width: 260px;
}

#display {
    width: 100%;
    height: 50px;
    font-size: 24px;
    margin-bottom: 10px;
    text-align: right;
    padding-right: 10px;
    border: none;
    border-radius: 5px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    height: 50px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    opacity: 0.8;
}

.equals {
    grid-row: span 2;
    background: #4caf50;
    color: white;
}

.zero {
    grid-column: span 2;
}

button:not(.equals) {
    background: #444;
    color: white;
}
let display = document.getElementById("display");

function appendValue(value) {
    display.value += value;
}

function clearDisplay() {
    display.value = "";
}

function deleteLast() {
    display.value = display.value.slice(0, -1);
}

function calculateResult() {
    try {
        display.value = eval(display.value);
    } catch {
        display.value = "Error";
    }
}



