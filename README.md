# Ex04 Simple Calculator - React Project
## Date:

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
### App.js
```
import React, { useState } from 'react';
import './styles.css';

function App() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      calculateResult();
    } else if (value === 'AC') {
      setInput('');
    } else if (value === '⌫') {
      setInput((prevInput) => prevInput.slice(0, -1));
    } else {
      setInput((prevInput) => prevInput + value);
    }
  };

  const calculateResult = () => {
    try {
      setInput(eval(input).toString());
    } catch (error) {
      setInput('Error');
    }
  };

  return (
    <div className="calculator">
      <h1>Calculator</h1>
      <div className="display">
        <input type="text" value={input} readOnly />
        
      </div>
      <div className="buttons">
        {[ 'AC', '⌫', '%', '/', '7', '8', '9', '*', '4', '5', '6', '-', '1', '2', '3', '+', '0', '.', '=' ].map((button) => (
          <button
            key={button}
            onClick={() => handleClick(button)}
            className={`button-circle ${
              button === '=' ? 'equals' :
              button === 'AC' ? 'all-clear' :
              button === '⌫' ? 'backspace' :
              ['/','*','-','+','%'].includes(button) ? 'operator' : 'number'
            }`}
          >
            {button}
          </button>
        ))}
      </div>
      <footer className="footer">
        <p>&copy; Dhareene R K (212222040035)</p>
      </footer>
    </div>
  );
}

export default App;
```

### App.css
```
import React, { useState } from 'react';
import "./App.css";

function App() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      calculateResult();
    } else if (value === 'AC') {
      setInput('');
    } else if (value === '⌫') {
      setInput((prevInput) => prevInput.slice(0, -1));
    } else {
      setInput((prevInput) => prevInput + value);
    }
  };

  const calculateResult = () => {
    try {
      setInput(eval(input).toString());
    } catch (error) {
      setInput('Error');
    }
  };

  return (
    <div className="calculator">
      <h1>Calculator</h1>
      <div className="display">
        <input type="text" value={input} readOnly />
      </div>
      <div className="buttons">
        {[ 'AC', '⌫', '%', '/', '7', '8', '9', '*', '4', '5', '6', '-', '1', '2', '3', '+', '0', '.', '=' ].map((button) => (
          <button
            key={button}
            onClick={() => handleClick(button)}
            className={`button-circle ${
              button === '=' ? 'equals' :
              button === 'AC' ? 'all-clear' :
              button === '⌫' ? 'backspace' :
              ['/','*','-','+','%'].includes(button) ? 'operator' : 'number'
            }`}
          >
            {button}
          </button>
        ))}
      </div>
      <footer className="footer">
        <p>&copy; Developed by: Deepika S</p>
        <p>Register Number: 212222230028</p>
      </footer>
    </div>
  );
}

export default App;

/* CSS */

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(135deg, #ffebf0, #dbe7ff);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.calculator {
  background: #f8d7da;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0px 10px 25px rgba(0, 0, 0, 0.2);
  width: 400px;
  text-align: center;
}

.display {
  background: #ffdde1;
  padding: 15px;
  border-radius: 10px;
  margin-bottom: 15px;
  box-shadow: inset 0px 0px 10px rgba(0, 0, 0, 0.1);
}

.display input {
  width: 100%;
  height: 60px;
  font-size: 32px;
  text-align: right;
  padding: 10px;
  border: none;
  background: transparent;
  color: #333;
  outline: none;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  width: 70px;
  height: 70px;
  font-size: 24px;
  cursor: pointer;
  border: none;
  background: #ffcbf2;
  color: #333;
  border-radius: 12px;
  transition: all 0.3s ease;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

button:hover {
  background: #ffc8dd;
}

button:active {
  background: #ffafcc;
  transform: scale(0.95);
}

.equals {
  background: #ffb4a2;
  color: #fff;
  border-radius: 25px;
}

.equals:hover {
  background: #e5989b;
}

.all-clear {
  background: #ffb3c6;
}

.all-clear:hover {
  background: #ff8fab;
}

.backspace {
  background: #b5e2fa;
}

.backspace:hover {
  background: #99d5ee;
}

.operator {
  background: #c1e1c1;
}

.operator:hover {
  background: #a3d2a3;
}

.footer {
  margin-top: 15px;
  padding: 10px;
  text-align: center;
  font-size: 14px;
  color: #555;
}


```
## OUTPUT
![dhareeneweb4 sc1](https://github.com/user-attachments/assets/ff4b9f5f-26f8-4dd3-8e9f-6e621b18d52d)

![dhareeneweb4 sc2](https://github.com/user-attachments/assets/0e3d46a9-9ad3-40b1-8ebf-0c51e052d7b2)

![dhareeneweb4 sc3](https://github.com/user-attachments/assets/458afb4d-3031-421c-a802-4a13f6352b56)




## RESULT
The program for developing a simple calculator in React.js is executed successfully.
