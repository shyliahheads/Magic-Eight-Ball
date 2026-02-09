# Magic-Eight-Ball
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Magic Eight Ball</title>
  <style>
    body {
      font-family: "Comic Sans MS", "Comic Sans", cursive;
      background-color: #111;
      color: white;
      text-align: center;
      padding-top: 100px;
    }

    button {
      padding: 12px 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 8px;
      border: none;
    }

    #answerBox {
      margin-top: 30px;
      font-size: 22px;
      font-weight: bold;
      color: #00e5ff;
    }
  </style>
</head>
<body>

  <h1>🔮 Magic Eight Ball 🔮</h1>
  <p>Ask a yes or no question… if you dare.</p>

  <button onclick="startGame()">Ask the Eight Ball</button>

  <div id="answerBox"></div>

  <script>

    // Array of 8 fortune responses
    var responses = [
      "Yes, definitely.",
      "No, not at all.",
      "Ask again later.",
      "It is certain.",
      "Very doubtful.",
      "Signs point to yes.",
      "Better not tell you now.",
      "My sources say no."
    ];

    function startGame() {

      var playAgain = true;

      while (playAgain) {

        // Prompt user for question
        var question = prompt("Ask the Magic Eight Ball a YES or NO question:");

        if (question === null || question.trim() === "") {
          alert("You must ask a question!");
        } else {

          // Randomizer
          var randomNumber = Math.floor(Math.random() * responses.length);
          var answer = responses[randomNumber];

          // Display answer on page
          document.getElementById("answerBox").innerHTML = answer;

          alert("🎱 " + answer);
        }

        // Ask user if they want to continue
        playAgain = confirm("Do you want to ask another question?");
      }

      alert("Thanks for playing the Magic Eight Ball!");
    }

  </script>

</body>
</html>
