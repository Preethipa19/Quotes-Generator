# Quotes-Generator
# Quote Generator

A simple and stylish web application that displays a random quote with a dynamic background color change.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [License](#license)

## Introduction

This project is a Quote Generator that changes the background color of the webpage and displays a random quote every time the button is clicked. It is built with HTML, CSS, and JavaScript.

## Features

- Randomly generates a quote from a predefined list.
- Changes the background color to a random RGB color when a new quote is generated.
- Stylish button with a sparkle effect on hover.
- Responsive design.

## Usage

To use the Quote Generator:

1. Clone the repository:
    ```sh
    git clone https://github.com/Preethipa19/quote-generator.git
    ```

2. Navigate to the project directory:
    ```sh
    cd quote-generator
    ```

3. Open the `index.html` file in your web browser:
    ```sh
    open index.html
    ```

## Code Overview

### HTML

The HTML file structure for the Quote Generator:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>QUOTE GENERATOR!</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h1>Quote of the day!!</h1>
    <button onclick="color()">Generate Quote</button>
    <div id="root"></div>

    <script>
      function color() {
        var a = Math.floor(Math.random() * 255);
        var b = Math.floor(Math.random() * 255);
        var c = Math.floor(Math.random() * 255);
        var d = `rgb(${a},${b},${c})`;
        document.body.style.backgroundColor = d;

        const q = [
          "The only way to do great work is to love what you do. - Steve Jobs",
          "It does not matter how slowly you go as long as you do not stop. - Confucius",
          "In the end, it's not the years in your life that count. It's the life in your years. - Abraham Lincoln",
          "The greatest leader is not necessarily the one who does the greatest things. He is the one that gets the people to do the greatest things. - Ronald Reagan",
          "Courage is not the absence of fear, but the triumph over it. - Nelson Mandela",
          "Success is not final, failure is not fatal: It is the courage to continue that counts. - Winston Churchill",
          "Happiness is not something ready made. It comes from your own actions. - Dalai Lama",
          "Be the change that you wish to see in the world. - Mahatma Gandhi",
          "An investment in knowledge pays the best interest. - Benjamin Franklin",
          "Love is not only something you feel, it is something you do. - David Wilkerson"
        ];

        const index = Math.floor(Math.random() * q.length);
        document.getElementById("root").textContent = q[index];
      }
    </script>
  </body>
</html>


*###CSSfile
body {
  font-family: "Arial", sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  margin: 0;
}

h1 {
  font-size: 3rem;
  color: #fff;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  text-transform: capitalize;
}

button {
  position: relative;
  padding: 15px 30px;
  font-size: 1.2rem;
  color: #fff;
  background: linear-gradient(45deg, #6a11cb 0%, #2575fc 100%);
  border: none;
  border-radius: 50px;
  cursor: pointer;
  overflow: hidden;
  transition: background 0.3s ease, transform 0.3s ease;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

button::before {
  content: "";
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(
    circle,
    rgba(255, 255, 255, 0.5) 10%,
    transparent 10.01%
  );
  background-size: 10px 10px;
  opacity: 0.4;
  transform: translateX(0) translateY(0);
  transition: opacity 0.3s ease;
}

button:hover::before {
  opacity: 1;
  animation: sparkle 1s infinite linear;
}

button:hover {
  transform: scale(1.1);
  background: linear-gradient(45deg, #2575fc 0%, #6a11cb 100%);
}

@keyframes sparkle {
  0% {
    background-position: 0 0;
  }
  100% {
    background-position: 100% 100%;
  }
}

#root {
  margin-top: 30px;
  font-size: 1.8rem;
  color: #fff;
  text-align: center;
  padding: 20px;
  border: 3px solid #fff;
  border-radius: 15px;
  background: rgba(0, 0, 0, 0.5);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: background 0.5s ease;
}

