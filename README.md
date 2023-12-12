<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    #calculator {
      border: 1px solid #ccc;
      border-radius: 8px;
      padding: 20px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    input {
      width: 100%;
      margin-bottom: 10px;
      padding: 10px;
      font-size: 18px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    button {
      width: 48px;
      height: 48px;
      font-size: 18px;
      margin: 5px;
      border: 1px solid #ccc;
      border-radius: 4px;
      cursor: pointer;
    }

    button:hover {
      background-color: #f0f0f0;
    }

    #result {
      font-size: 24px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div id="calculator">
    <input type="text" id="result" readonly>
    <div>
      <button onclick="appendToResult('1')">1</button>
      <button onclick="appendToResult('2')">2</button>
      <button onclick="appendToResult('3')">3</button>
      <button onclick="operate('+')">+</button>
    </div>
    <div>
      <button onclick="appendToResult('4')">4</button>
      <button onclick="appendToResult('5')">5</button>
      <button onclick="appendToResult('6')">6</button>
      <button onclick="operate('-')">-</button>
    </div>
    <div>
      <button onclick="appendToResult('7')">7</button>
      <button onclick="appendToResult('8')">8</button>
      <button onclick="appendToResult('9')">9</button>
      <button onclick="operate('*')">*</button>
    </div>
    <div>
      <button onclick="appendToResult('0')">0</button>
      <button onclick="clearResult()">C</button>
      <button onclick="calculate()">=</button>
      <button onclick="operate('/')">/</button>
    </div>
  </div>

  <script>
    let result = document.getElementById('result');

    function appendToResult(value) {
      result.value += value;
    }

    function clearResult() {
      result.value = '';
    }

    function calculate() {
      try {
        result.value = eval(result.value);
      } catch (error) {
        result.value = 'Error';
      }
    }

    function operate(operator) {
      result.value += operator;
    }
  </script>
</body>
</html>
