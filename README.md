<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Simulator</title>
    <style>
        /* Basic styling for the page */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            background-color: #f0f2f5;
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        #question-container {
            background-color: #fff;
            border-radius: 8px;
            padding: 20px;
            width: 80%;
            max-width: 600px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            text-align: center;
            margin-bottom: 20px;
        }

        button {
            margin-top: 10px;
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }

        button:hover {
            background-color: #0056b3;
        }

        .option-button {
            display: block;
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            background-color: #28a745;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }

        .option-button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <h1>IT Support Simulator</h1>
    <div id="question-container">
        <!-- Question and answer options will appear here -->
    </div>
    <button onclick="loadRandomIssue()">Next Issue</button>

    <script>
        // JSON data embedded directly with a few sample questions
        const issues = [
            {
                "issue": "The user's computer won't turn on.",
                "options": [
                    { "text": "Check the power cable and connection.", "correct": true },
                    { "text": "Restart the router.", "correct": false },
                    { "text": "Check for software updates.", "correct": false },
                    { "text": "Clear the browser cache.", "correct": false }
                ],
                "explanation": "Checking the power cable and connection is the first step for diagnosing a hardware power issue."
            },
            {
                "issue": "User reports that their internet connection is slow.",
                "options": [
                    { "text": "Restart the router and modem.", "correct": true },
                    { "text": "Clear the browser cache.", "correct": false },
                    { "text": "Install a new antivirus program.", "correct": false },
                    { "text": "Reinstall the operating system.", "correct": false }
                ],
                "explanation": "Restarting the router and modem can help refresh the internet connection and improve speed."
            },
            {
                "issue": "The printer is not responding to print commands.",
                "options": [
                    { "text": "Check if the printer is powered on and connected.", "correct": true },
                    { "text": "Close all applications and restart the computer.", "correct": false },
                    { "text": "Run a virus scan.", "correct": false },
                    { "text": "Check email settings.", "correct": false }
                ],
                "explanation": "Ensuring the printer is powered on and connected is the first step in troubleshooting printer issues."
            },
            // Add more questions in this format
        ];

        function loadRandomIssue() {
            // Pick a random issue from the list
            const randomIndex = Math.floor(Math.random() * issues.length);
            const issue = issues[randomIndex];
            
            // Display the issue and options
            const container = document.getElementById("question-container");
            container.innerHTML = `<h2>${issue.issue}</h2>`;
            issue.options.forEach((option, index) => {
                container.innerHTML += `<button class="option-button" onclick="checkAnswer(${randomIndex}, ${index})">${option.text}</button>`;
            });
        }

        function checkAnswer(issueIndex, optionIndex) {
            const selectedOption = issues[issueIndex].options[optionIndex];
            const explanation = selectedOption.correct ? "Correct! " + issues[issueIndex].explanation : "Incorrect. " + issues[issueIndex].explanation;
            alert(explanation);
        }

        // Load a random issue on page load
        loadRandomIssue();
    </script>
</body>
</html>
