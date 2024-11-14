<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Full-Screen IT Support Simulator</title>
    <style>
        /* Full-screen styling */
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #e0f7fa;
            font-family: Arial, sans-serif;
        }

        .simulator-container {
            width: 80%;
            height: 80%;
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            font-size: 32px;
            margin: 20px 0;
        }

        .issue {
            font-size: 22px;
            color: #333;
            margin: 20px 0;
            height: 60px;
        }

        .options {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            width: 80%;
        }

        .option {
            background-color: #e0e0e0;
            padding: 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
            font-size: 18px;
        }

        .option:hover {
            background-color: #b3e5fc;
        }

        .feedback {
            font-size: 20px;
            color: #388e3c;
            margin-top: 20px;
        }

        .score, .progress {
            font-size: 20px;
            color: #00796b;
            margin: 10px;
        }
    </style>
</head>
<body>

<div class="simulator-container">
    <h1>IT Support Simulator</h1>
    <div class="progress" id="progress">Progress: 0%</div>
    <div class="score" id="score">Score: 0</div>
    <div class="issue" id="issue">Loading issue...</div>
    <div class="options" id="options"></div>
    <div class="feedback" id="feedback"></div>
</div>

<script>
    // Sample issue data (extend this with 100s of issues)
    const issues = [
        {
            issue: "User cannot access their email account.",
            options: [
                { text: "Reset the user’s password.", correct: true },
                { text: "Tell them to contact their ISP.", correct: false },
                { text: "Ask them to restart their computer.", correct: false },
                { text: "Suggest using a different browser.", correct: false }
            ],
            explanation: "Resetting the password is the most common solution for account access issues."
        },
        {
            issue: "Computer is running slowly.",
            options: [
                { text: "Run a virus scan.", correct: true },
                { text: "Tell the user to buy a new computer.", correct: false },
                { text: "Suggest they close all applications.", correct: false },
                { text: "Recommend they add more RAM.", correct: false }
            ],
            explanation: "A virus scan can detect malicious software causing slow performance."
        },
        // Add more issues here...
    ];

    let currentIssueIndex = 0;
    let score = 0;

    function loadIssue() {
        const issueElement = document.getElementById("issue");
        const optionsElement = document.getElementById("options");
        const feedbackElement = document.getElementById("feedback");
        const scoreElement = document.getElementById("score");
        const progressElement = document.getElementById("progress");

        feedbackElement.innerText = ""; // Clear feedback

        // Load current issue
        const issue = issues[currentIssueIndex];
        issueElement.innerText = issue.issue;
        optionsElement.innerHTML = ""; // Clear previous options

        // Display answer options
        issue.options.forEach(option => {
            const optionDiv = document.createElement("div");
            optionDiv.className = "option";
            optionDiv.innerText = option.text;
            optionDiv.onclick = () => checkAnswer(option.correct, issue.explanation);
            optionsElement.appendChild(optionDiv);
        });

        // Update progress
        progressElement.innerText = `Progress: ${Math.floor((currentIssueIndex / issues.length) * 100)}%`;
        scoreElement.innerText = `Score: ${score}`;
    }

    function checkAnswer(correct, explanation) {
        const feedbackElement = document.getElementById("feedback");
        if (correct) {
            feedbackElement.innerText = "Correct! " + explanation;
            score++;
        } else {
            feedbackElement.innerText = "Incorrect. " + explanation;
        }

        // Move to the next issue after delay
        currentIssueIndex = (currentIssueIndex + 1) % issues.length;
        setTimeout(loadIssue, 3000); // Load next issue after delay
    }

    // Initialize the first issue
    loadIssue();
</script>

</body>
</html>
