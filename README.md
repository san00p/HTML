<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rock Paper Scissors Game</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }

        #game-container {
            margin-top: 50px;
        }

        .btn {
            font-size: 18px;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        #result {
            font-size: 24px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Rock Paper Scissors Game</h1>

    <div id="game-container">
        <button class="btn" onclick="playGame('rock')">Rock</button>
        <button class="btn" onclick="playGame('paper')">Paper</button>
        <button class="btn" onclick="playGame('scissors')">Scissors</button>

        <div id="result"></div>
    </div>

    <script>
        function playGame(userChoice) {
            var choices = ['rock', 'paper', 'scissors'];
            var computerChoice = choices[Math.floor(Math.random() * 3)];

            var result = '';

            if (userChoice === computerChoice) {
                result = 'It\'s a tie!';
            } else if (
                (userChoice === 'rock' && computerChoice === 'scissors') ||
                (userChoice === 'paper' && computerChoice === 'rock') ||
                (userChoice === 'scissors' && computerChoice === 'paper')
            ) {
                result = 'You win!';
            } else {
                result = 'You lose!';
            }

            document.getElementById('result').innerText = `Computer chose ${computerChoice}. ${result}`;
        }
    </script>

</body>
</html>
