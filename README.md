# Ex04 Simple Calculator - React Project
## Date:11.04.2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
# Index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Simple Calculator</title>
  <link rel="stylesheet" href="index.css">
</head>
<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <div class="buttons">
    <button onclick="clearDisplay()">C</button>
    <button onclick="deleteLast()">DEL</button>
    <button onclick="append('%')">%</button>
    <button onclick="append('/')">/</button>

    <button onclick="append('7')">7</button>
    <button onclick="append('8')">8</button>
    <button onclick="append('9')">9</button>
    <button onclick="append('*')">*</button>

    <button onclick="append('4')">4</button>
    <button onclick="append('5')">5</button>
    <button onclick="append('6')">6</button>
    <button onclick="append('-')">-</button>

    <button onclick="append('1')">1</button>
    <button onclick="append('2')">2</button>
    <button onclick="append('3')">3</button>
    <button onclick="append('+')">+</button>

    <button onclick="append('0')">0</button>
    <button onclick="append('.')">.</button>
    <button class="equal" onclick="calculate()">=</button>
  </div>
</div>

<script src="index.js"></script>
</body>
</html>


```

# Index.css

```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    height: 100vh;
    background: linear-gradient(135deg, #74ebd5, #acb6e5);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Poppins', sans-serif;
  }
  
  .calculator {
    background: #fff;
    padding: 20px;
    border-radius: 16px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    width: 300px;
  }
  
  #display {
    width: 100%;
    height: 60px;
    font-size: 24px;
    text-align: right;
    padding: 10px;
    border: none;
    border-radius: 8px;
    margin-bottom: 20px;
    background: #f0f0f0;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }
  
  button {
    padding: 20px;
    font-size: 20px;
    border: none;
    border-radius: 10px;
    background: #f7f7f7;
    cursor: pointer;
    transition: background 0.3s;
  }
  
  button:hover {
    background: #d0d0d0;
  }
  
  .equal {
    grid-column: span 2;
    background: #0078ff;
    color: #fff;
  }
  
  .equal:hover {
    background: #005bb5;
  }
  



```


# Index.js

```

function append(value) {
    document.getElementById('display').value += value;
  }
  
  function clearDisplay() {
    document.getElementById('display').value = '';
  }
  
  function deleteLast() {
    const current = document.getElementById('display').value;
    document.getElementById('display').value = current.slice(0, -1);
  }
  
  function calculate() {
    try {
      document.getElementById('display').value = eval(document.getElementById('display').value);
    } catch (error) {
      document.getElementById('display').value = 'Error';
    }
  }
  


```


calculator.jsx
```jsx
import React, { useState } from 'react';
import './index.css';

const Calculator = () => {
  const [display, setDisplay] = useState('');

  const append = (value) => {
    setDisplay(prev => prev + value);
  };

  const clearDisplay = () => {
    setDisplay('');
  };

  const deleteLast = () => {
    setDisplay(prev => prev.slice(0, -1));
  };

  const calculate = () => {
    try {
      setDisplay(eval(display).toString()); // ⚠️ Using eval is risky; use with caution.
    } catch (error) {
      setDisplay('Error');
    }
  };

  return (
    <div className="calculator">
      <input type="text" value={display} disabled />

      <div className="buttons">
        <button onClick={clearDisplay}>C</button>
        <button onClick={deleteLast}>DEL</button>
        <button onClick={() => append('%')}>%</button>
        <button onClick={() => append('/')}>/</button>

        <button onClick={() => append('7')}>7</button>
        <button onClick={() => append('8')}>8</button>
        <button onClick={() => append('9')}>9</button>
        <button onClick={() => append('*')}>*</button>

        <button onClick={() => append('4')}>4</button>
        <button onClick={() => append('5')}>5</button>
        <button onClick={() => append('6')}>6</button>
        <button onClick={() => append('-')}>-</button>

        <button onClick={() => append('1')}>1</button>
        <button onClick={() => append('2')}>2</button>
        <button onClick={() => append('3')}>3</button>
        <button onClick={() => append('+')}>+</button>

        <button onClick={() => append('0')}>0</button>
        <button onClick={() => append('.')}>.</button>
        <button className="equal" onClick={calculate}>=</button>
      </div>
    </div>
  );
};

export default Calculator;
```

## OUTPUT


![image](https://github.com/user-attachments/assets/71106109-0fe7-4b53-a6be-22e6dc8e477b)


![image](https://github.com/user-attachments/assets/740582f7-b2b2-4fee-8fd2-c4640b5ea6dc)

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
