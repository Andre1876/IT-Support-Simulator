# IT-Support-Technician-Animation


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Simulator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f4f8fb;
        }
        .app-container {
            width: 400px;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            text-align: center;
        }
        .header {
            font-size: 24px;
            font-weight: bold;
            color: #333;
            margin-bottom: 10px;
        }
        .task {
            margin-top: 20px;
            padding: 15px;
            background-color: #e3f2fd;
            border-radius: 5px;
            font-size: 18px;
            color: #333;
        }
        .options {
            margin-top: 15px;
        }
        .option-button {
            display: inline-block;
            padding: 10px 20px;
            margin: 5px;
            font-size: 16px;
            color: #fff;
            background-color: #4CAF50;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .option-button:hover {
            background-color: #45a049;
        }
        .status {
            margin-top: 20px;
            font-size: 16px;
            color: #555;
        }
    </style>
</head>
<body>

    <div class="app-container">
        <div class="header">IT Support Simulator</div>
        <div class="task" id="task">Welcome! Click "Next Request" to begin helping clients.</div>
        <div class="options">
            <button class="option-button" onclick="handleOption('fix')">Fix the Issue</button>
            <button class="option-button" onclick="handleOption('ask')">Ask More Details</button>
            <button class="option-button" onclick="handleOption('escalate')">Escalate to Supervisor</button>
        </div>
        <button class="option-button" onclick="nextRequest()">Next Request</button>
        <div class="status" id="status">Status: Waiting for next request...</div>
    </div>

    <script>
        const requests = [
            { problem: "Cannot connect to VPN", fixResponse: "VPN reconnected!", askResponse: "Please check network settings.", escalateResponse: "Escalated to Network Team." },
            { problem: "Forgot email password", fixResponse: "Password reset successfully!", askResponse: "Is this a work or personal email?", escalateResponse: "Escalated to IT Security." },
            { problem: "Computer is too slow", fixResponse: "Ran system cleanup, speed improved!", askResponse: "Are you running multiple applications?", escalateResponse: "Escalated to Desktop Support." },
        ];

        let currentRequest = -1;

        function nextRequest() {
            currentRequest = (currentRequest + 1) % requests.length;
            document.getElementById('task').innerText = `Client Issue: ${requests[currentRequest].problem}`;
            document.getElementById('status').innerText = "Status: New request received.";
        }

        function handleOption(option) {
            let response;
            if (option === 'fix') {
                response = requests[currentRequest].fixResponse;
            } else if (option === 'ask') {
                response = requests[currentRequest].askResponse;
            } else if (option === 'escalate') {
                response = requests[currentRequest].escalateResponse;
            }
            document.getElementById('status').innerText = `Status: ${response}`;
        }
    </script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Technician Animation</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #e8f5fe;
        }
        .office-container {
            width: 500px;
            height: 400px;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }
        .technician {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 100px;
            background-color: #4CAF50;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            animation: bounce 1.5s infinite;
        }
        .technician::before {
            content: '';
            width: 30px;
            height: 30px;
            background-color: #333;
            border-radius: 50%;
            position: absolute;
            top: -30px;
        }
        .desk {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            height: 50px;
            background-color: #b0bec5;
        }
        .computer {
            position: absolute;
            top: -30px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 30px;
            background-color: #607d8b;
        }
        .screen {
            position: absolute;
            top: 3px;
            left: 5px;
            width: 30px;
            height: 20px;
            background-color: #333;
            color: #76ff03;
            font-size: 12px;
            font-family: monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        @keyframes bounce {
            0%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            50% {
                transform: translateX(-50%) translateY(-10px);
            }
        }
    </style>
</head>
<body>

<div class="office-container">
    <div class="technician"></div>
    <div class="desk">
        <div class="computer">
            <div class="screen" id="screen">Loading...</div>
        </div>
    </div>
</div>

<script>
    // Typing effect for "screen" text
    const screen = document.getElementById('screen');
    const messages = [
        "Loading system...",
        "Connecting to client...",
        "Checking VPN...",
        "Resetting password...",
        "Issue resolved!"
    ];
    let messageIndex = 0;
    let charIndex = 0;

    function typeMessage() {
        if (charIndex < messages[messageIndex].length) {
            screen.textContent += messages[messageIndex][charIndex];
            charIndex++;
            setTimeout(typeMessage, 100);
        } else {
            setTimeout(nextMessage, 1000);
        }
    }

    function nextMessage() {
        screen.textContent = "";
        charIndex = 0;
        messageIndex = (messageIndex + 1) % messages.length;
        typeMessage();
    }

    typeMessage();  // Start typing effect
</script>

</body>
</html>



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Simulator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
        }
        .simulator-container {
            width: 400px;
            padding: 20px;
            background-color: #ffffff;
            box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            text-align: center;
        }
        h1 {
            font-size: 24px;
            color: #333;
        }
        .issue {
            font-size: 18px;
            color: #444;
            margin: 20px 0;
        }
        .options {
            display: flex;
            flex-direction: column;
        }
        .option {
            margin: 8px 0;
            padding: 10px;
            background-color: #e0e0e0;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .option:hover {
            background-color: #cfd8dc;
        }
        .feedback {
            font-size: 16px;
            color: #28a745;
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div class="simulator-container">
    <h1>IT Support Simulator</h1>
    <div class="issue" id="issue">Loading issue...</div>
    <div class="options" id="options"></div>
    <div class="feedback" id="feedback"></div>
</div>

<script>
    const issues = [
        {
            issue: "User cannot connect to Wi-Fi.",
            options: [
                { text: "Check if airplane mode is enabled.", correct: true },
                { text: "Restart the computer.", correct: false },
                { text: "Tell the user to use a wired connection instead.", correct: false }
            ]
        },
        {
            issue: "Printer is not responding.",
            options: [
                { text: "Ensure the printer is turned on.", correct: true },
                { text: "Tell the user to print it later.", correct: false },
                { text: "Check if the toner needs to be replaced.", correct: false }
            ]
        },
        {
            issue: "User forgot their password.",
            options: [
                { text: "Reset the password through the IT portal.", correct: true },
                { text: "Tell them to remember it next time.", correct: false },
                { text: "Send them a tutorial on creating strong passwords.", correct: false }
            ]
        }
    ];

    let currentIssue = 0;

    function loadIssue() {
        const issueDisplay = document.getElementById("issue");
        const optionsDisplay = document.getElementById("options");
        const feedbackDisplay = document.getElementById("feedback");

        feedbackDisplay.innerHTML = ""; // Clear feedback
        const issue = issues[currentIssue];
        issueDisplay.innerText = issue.issue;
        optionsDisplay.innerHTML = ""; // Clear previous options

        issue.options.forEach((option, index) => {
            const optionDiv = document.createElement("div");
            optionDiv.className = "option";
            optionDiv.innerText = option.text;
            optionDiv.onclick = () => checkAnswer(option.correct);
            optionsDisplay.appendChild(optionDiv);
        });
    }

    function checkAnswer(correct) {
        const feedbackDisplay = document.getElementById("feedback");
        if (correct) {
            feedbackDisplay.innerText = "Correct! Issue resolved.";
            currentIssue = (currentIssue + 1) % issues.length; // Move to the next issue
            setTimeout(loadIssue, 2000); // Load next issue after a delay
        } else {
            feedbackDisplay.innerText = "Incorrect, try again!";
        }
    }

    loadIssue(); // Load the first issue when the page loads
</script>

</body>
</html>
