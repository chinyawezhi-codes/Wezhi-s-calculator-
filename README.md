# Wezhi-s-calculator-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>calculator</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: #000;
      color: #fff;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background-image: 
        linear-gradient(rgba(0, 100, 255, 0.1) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0, 100, 255, 0.1) 1px, transparent 1px);
      background-size: 20px 20px;
    }
    .calculator {
      width: 320px;
      background: #111;
      border-radius: 20px;
      padding: 20px;
      box-shadow: 0 0 40px rgba(0, 100, 255, 0.3);
    }
    .display {
      background: #000;
      color: #0ff;
      font-size: 2.5rem;
      text-align: right;
      padding: 20px;
      border-radius: 10px;
      margin-bottom: 20px;
      overflow: hidden;
      border: 1px solid #0ff;
      min-height: 80px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      background: #222;
      color: #fff;
      border: none;
      border-radius: 50%;
      font-size: 1.5rem;
      height: 65px;
      cursor: pointer;
    }
    button:active { background: #444; }
    .operator { background: #0066ff; color: #fff; }
    .clear { background: #ff3b30; }
    .equals { background: #00ff88; color: #000; }
    .zero { grid-column: span 2; border-radius: 35px; }
  </style>
</head>
<body>
  <div class="calculator">
    <div class="display" id="display">0</div>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button onclick="appendToDisplay(')">(</button>
      <button onclick="appendToDisplay(')')">)</button>
      <button class="operator" onclick="appendToDisplay('/')">÷</button>
      
      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button class="operator" onclick="appendToDisplay('*')">×</button>
      
      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button class="operator" onclick="appendToDisplay('-')">−</button>
      
      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button class="operator" onclick="appendToDisplay('+')">+</button>
      
      <button class="zero" onclick="appendToDisplay('0')">0</button>
      <button onclick="appendToDisplay('.')">.</button>
      <button class="equals" onclick="calculate()">=</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');
    
    function appendToDisplay(value) {
      if (display.innerText === '0' && value !== '.') {
        display.innerText = value;
      } else {
        display.innerText += value;
      }
    }
    
    function clearDisplay() {
      display.innerText = '0';
    }
    
    function calculate() {
      try {
        display.innerText = eval(display.innerText.replace('×', '*').replace('÷', '/').replace('−', '-'));
      } catch {
        display.innerText = 'Error';
      }
    }
  </script>
</body>
</html>
