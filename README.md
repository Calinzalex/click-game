
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Click the Button Game</h1>
    <p>Click the button as many times as you can in 10 seconds!</p>
    <button id="clickButton" onclick="incrementScore()">Click Me!</button>
    <div class="score">
        <p>Score: <span id="score">0</span></p>
        <p>Time Left: <span id="timeLeft">10</span> seconds</p>
    </div>
    <script>
        let score = 0;
        let timeLeft = 10;
        let gameActive = true;

        function incrementScore() {
            if (gameActive) {
                score++;
                document.getElementById("score").textContent = score;
            }
        }

        function countdown() {
            const timer = setInterval(() => {
                if (timeLeft > 0) {
                    timeLeft--;
                    document.getElementById("timeLeft").textContent = timeLeft;
                } else {
                    clearInterval(timer);
                    gameActive = false;
                    alert("Time's up! Your final score is: " + score);
                }
            }, 1000);
        }

        // Start the countdown when the page loads
        window.onload = countdown;
    </script>
</body>
</html>
