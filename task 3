<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Responsive Web Quiz & API</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 20px;
    }

    .container {
      max-width: 800px;
      margin: auto;
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h1, h2 {
      text-align: center;
      color: #333;
    }

    .quiz-question {
      margin: 20px 0;
    }

    button {
      padding: 10px 20px;
      margin: 10px 5px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #45a049;
    }

    .quote-box {
      margin-top: 20px;
      font-style: italic;
      color: #555;
      text-align: center;
    }

    #quiz-result {
      font-weight: bold;
      text-align: center;
      margin-top: 15px;
    }

    @media (max-width: 600px) {
      .container {
        padding: 15px;
      }

      button {
        width: 100%;
        margin: 10px 0;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Responsive Web Quiz</h1>

    <!-- Quiz Section -->
    <section>
      <h2>Quiz: Web Basics</h2>
      <div class="quiz-question">
        <p>Which HTML tag is used to define a paragraph?</p>
        <button onclick="checkAnswer(this, true)"> &lt;p&gt; </button>
        <button onclick="checkAnswer(this, false)"> &lt;div&gt; </button>
        <button onclick="checkAnswer(this, false)"> &lt;span&gt; </button>
      </div>
      <div class="quiz-question">
        <p>What does CSS stand for?</p>
        <button onclick="checkAnswer(this, true)"> Cascading Style Sheets </button>
        <button onclick="checkAnswer(this, false)"> Creative Style System </button>
        <button onclick="checkAnswer(this, false)"> Computer Style Sheet </button>
      </div>
      <p id="quiz-result">Score: 0</p>
    </section>

    <!-- API Section -->
    <section>
      <h2>Get a Random Quote</h2>
      <button onclick="fetchQuote()">Fetch Quote</button>
      <div class="quote-box" id="quoteBox">Click the button to see a quote.</div>
    </section>
  </div>

  <script>
    let score = 0;

    function checkAnswer(button, isCorrect) {
      if (isCorrect) {
        score++;
        button.style.backgroundColor = 'green';
      } else {
        button.style.backgroundColor = 'red';
      }
      button.disabled = true;
      document.getElementById('quiz-result').textContent = "Score: " + score;
    }

    function fetchQuote() {
      fetch("https://api.quotable.io/random")
        .then(response => response.json())
        .then(data => {
          document.getElementById("quoteBox").textContent =
            `"${data.content}" — ${data.author}`;
        })
        .catch(() => {
          document.getElementById("quoteBox").textContent = "Failed to load quote.";
        });
    }
  </script>

</body>
</html>
