<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personality Results</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to right, #ff7e5f, #feb47b);
            color: #fff;
        }
        .container {
            text-align: center;
            margin: 50px auto;
            max-width: 800px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.6);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
        }
        h1, h2, p {
            margin: 20px 0;
        }
        .button {
            display: inline-block;
            margin: 20px;
            padding: 10px 20px;
            color: #fff;
            background: #007bff;
            text-decoration: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            border: none;
        }
        .button:hover {
            background: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Your Personality Result</h1>
        <p id="result"></p>
        <a href="index.html" class="button">Take the Test Again</a>
    </div> 

    <script>
        // Parse URL Parameters
        const params = new URLSearchParams(window.location.search);
        const scores = { A: 0, B: 0, C: 0 }; 

        // Count answers
        params.forEach((value) => {
            scores[value]++;
        }); 

        // Determine Personality
        let personality;
        if (scores.A > scores.B && scores.A > scores.C) {
            personality = "Highly Organized and Methodical!";
        } else if (scores.B > scores.A && scores.B > scores.C) {
            personality = "Adventurous and Spontaneous!";
        } else {
            personality = "Thoughtful and Reflective!";
        } 

        // Display Result
        document.getElementById("result").textContent = You are: ${personality};
    </script>
</body>
</html>
