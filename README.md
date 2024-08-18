### **Preview**

**Live Demo:** [Click here to view the calculator in action](https://srinandhan-s.github.io/Simple-Calculator/)

Explore the fully functional web-based calculator that performs basic arithmetic operations. The clean, responsive interface ensures seamless interaction across devices.
### **Code**

#### **HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stylish Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button class="btn function" onclick="clearDisplay()">C</button>
            <button class="btn function" onclick="deleteLast()">DEL</button>
            <button class="btn operator" onclick="appendCharacter('/')">/</button>
            <button class="btn operator" onclick="appendCharacter('*')">x</button>
            <button class="btn" onclick="appendCharacter('7')">7</button>
            <button class="btn" onclick="appendCharacter('8')">8</button>
            <button class="btn" onclick="appendCharacter('9')">9</button>
            <button class="btn operator" onclick="appendCharacter('-')">-</button>
            <button class="btn" onclick="appendCharacter('4')">4</button>
            <button class="btn" onclick="appendCharacter('5')">5</button>
            <button class="btn" onclick="appendCharacter('6')">6</button>
            <button class="btn operator" onclick="appendCharacter('+')">+</button>
            <button class="btn" onclick="appendCharacter('1')">1</button>
            <button class="btn" onclick="appendCharacter('2')">2</button>
            <button class="btn" onclick="appendCharacter('3')">3</button>
            <button class="btn" onclick="appendCharacter('.')">.</button>
            <button class="btn zero" onclick="appendCharacter('0')">0</button>
            <button class="btn equals" onclick="calculateResult()">=</button>
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
    background: linear-gradient(135deg, #667eea, #764ba2);
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}

.calculator {
    width: 400px;
    background: #1e1e1e;
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
    overflow: hidden;
}

.display {
    background-color: #111;
    color: #fff;
    font-size: 2.5em;
    text-align: right;
    padding: 20px;
    box-sizing: border-box;
    border-bottom: 2px solid #333;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    padding: 20px;
}

.btn {
    padding: 20px;
    background-color: #333;
    color: #fff;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-size: 1.5em;
    transition: all 0.3s ease;
    box-shadow: 0 5px rgba(0, 0, 0, 0.2);
}

.btn:hover {
    background-color: #444;
}

.btn:active {
    box-shadow: 0 2px rgba(0, 0, 0, 0.2);
    transform: translateY(4px);
}

.function {
    background-color: #ff5c5c;
}

.operator {
    background-color: #ff9500;
}

.equals {
    background-color: #34c759;
    grid-column: span 2;
}

.zero {
    grid-column: span 2;
}

.function:hover, .operator:hover, .equals:hover {
    opacity:    0.8;
}
function clearDisplay() {
    document.getElementById('display').innerText = '0';
}

function deleteLast() {
    const display = document.getElementById('display');
    if (display.innerText.length > 1) {
        display.innerText = display.innerText.slice(0, -1);
    } else {
        display.innerText = '0';
    }
}

function appendCharacter(character) {
    const display = document.getElementById('display');
    if (display.innerText === '0' && character !== '.') {
        display.innerText = character;
    } else {
        display.innerText += character;
    }
}

function calculateResult() {
    const display = document.getElementById('display');
    try {
        const result = eval(display.innerText);
        display.innerText = result;
    } catch (error) {
        display.innerText = 'Error';
    }
}

### **Blame**

- **HTML:** Defines the structure of the calculator interface.
- **CSS:** Manages the styling to ensure a clean and responsive design.
- **JavaScript:** Implements functionality for arithmetic operations and user interactions.


