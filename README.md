<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Basic Calculator</title>

<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #f2f2f2;
    font-family: Arial, sans-serif;
}

.calculator {
    background: #111;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 15px rgba(0,0,0,0.4);
}

#display {
    width: 100%;
    height: 60px;
    margin-bottom: 15px;
    text-align: right;
    font-size: 28px;
    padding: 10px;
    border: none;
    border-radius: 10px;
    background: #eee;
    color: black;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 70px);
    gap: 12px;
}

button {
    height: 55px;
    font-size: 18px;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    background: #555;
    color: white;
    transition: 0.2s;
}

button:hover {
    background: #777;
}

/* Special buttons */
.operator {
    background: orange;
}

.equal {
    background: green;
    grid-column: span 2;
}

.clear {
    background: red;
}
</style>
</head>

<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendValue('/')">/</button>
        <button onclick="appendValue('*')">*</button>
        <button onclick="appendValue('-')">-</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button class="equal" onclick="calculate()">=</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>

        <button onclick="appendValue('0')">0</button>
        <button onclick="appendValue('.')">.</button>
    </div>
</div>

<script>
function appendValue(value) {
    document.getElementById("display").value += value;
}

function clearDisplay() {
    document.getElementById("display").value = "";
}

function calculate() {
    try {
        document.getElementById("display").value =
            eval(document.getElementById("display").value);
    } catch {
        alert("Invalid Input");
    }
}
</script>

</body>
</html>
