

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
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
    <h1></h1>
    <div id="question-container">
        <!-- Question and answer options will appear here -->
    </div>
    <button onclick="loadRandomIssue()">Next Issue</button>

    <script>
        // JSON data embedded directly with a few sample questions
        const issues = [

[
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
        "issue": "User cannot access Wi-Fi on their laptop.",
        "options": [
            { "text": "Check if airplane mode is turned off.", "correct": true },
            { "text": "Restart the desktop computer.", "correct": false },
            { "text": "Increase the screen brightness.", "correct": false },
            { "text": "Clear cookies and cache.", "correct": false }
        ],
        "explanation": "Airplane mode blocks wireless connections. Ensure it's off to access Wi-Fi."
    },
    {
        "issue": "User’s email inbox is not receiving messages.",
        "options": [
            { "text": "Check the spam/junk folder.", "correct": true },
            { "text": "Restart the computer.", "correct": false },
            { "text": "Clear browser history.", "correct": false },
            { "text": "Suggest they contact the ISP.", "correct": false }
        ],
        "explanation": "Email providers often filter emails to the spam/junk folder."
    },
    {
        "issue": "The printer is not printing.",
        "options": [
            { "text": "Check if the printer is connected and turned on.", "correct": true },
            { "text": "Update the operating system.", "correct": false },
            { "text": "Install antivirus software.", "correct": false },
            { "text": "Reinstall the browser.", "correct": false }
        ],
        "explanation": "Checking the printer’s connection and power status is a primary troubleshooting step."
    },
    {
        "issue": "User forgot their system password.",
        "options": [
            { "text": "Help them reset their password.", "correct": true },
            { "text": "Install new software.", "correct": false },
            { "text": "Suggest they wait 24 hours and try again.", "correct": false },
            { "text": "Turn off notifications.", "correct": false }
        ],
        "explanation": "Password reset is the solution for accessing a locked-out system."
    },
    {
        "issue": "The browser is running slowly on the user’s computer.",
        "options": [
            { "text": "Clear cookies and cache.", "correct": true },
            { "text": "Replace the hard drive.", "correct": false },
            { "text": "Update the router’s firmware.", "correct": false },
            { "text": "Lower the screen resolution.", "correct": false }
        ],
        "explanation": "Clearing cookies and cache often improves browser performance."
    },
    {
        "issue": "A user is receiving many spam emails.",
        "options": [
            { "text": "Adjust spam filter settings.", "correct": true },
            { "text": "Turn on airplane mode.", "correct": false },
            { "text": "Change the browser’s language.", "correct": false },
            { "text": "Update the monitor settings.", "correct": false }
        ],
        "explanation": "Spam filter settings help reduce unwanted emails."
    },
    {
        "issue": "User reports a frozen screen.",
        "options": [
            { "text": "Press Ctrl + Alt + Delete and open Task Manager.", "correct": true },
            { "text": "Reset the Wi-Fi settings.", "correct": false },
            { "text": "Turn off notifications.", "correct": false },
            { "text": "Reboot the router.", "correct": false }
        ],
        "explanation": "Accessing Task Manager can end unresponsive programs and resolve screen freezes."
    },
    {
        "issue": "User's computer is overheating.",
        "options": [
            { "text": "Check for dust in the fans and vents.", "correct": true },
            { "text": "Increase the display brightness.", "correct": false },
            { "text": "Reduce font size.", "correct": false },
            { "text": "Turn off Wi-Fi.", "correct": false }
        ],
        "explanation": "Dust build-up often causes overheating. Cleaning it improves airflow."
    },
    {
        "issue": "User is unable to connect to a VPN.",
        "options": [
            { "text": "Verify VPN credentials and server address.", "correct": true },
            { "text": "Check if the monitor is on.", "correct": false },
            { "text": "Clear the browser history.", "correct": false },
            { "text": "Suggest they contact their email provider.", "correct": false }
        ],
        "explanation": "Correct credentials and server settings are essential for VPN connections."
    },
    {
        "issue": "System shows 'No boot device found' error.",
        "options": [
            { "text": "Check BIOS settings for boot device priority.", "correct": true },
            { "text": "Reset the user’s email password.", "correct": false },
            { "text": "Close all open applications.", "correct": false },
            { "text": "Reduce display brightness.", "correct": false }
        ],
        "explanation": "Adjusting BIOS boot settings can resolve the 'No boot device' error."
    },
    {
        "issue": "User cannot hear any audio.",
        "options": [
            { "text": "Check if the speakers or headphones are plugged in and not muted.", "correct": true },
            { "text": "Lower the screen brightness.", "correct": false },
            { "text": "Increase font size.", "correct": false },
            { "text": "Turn off Bluetooth.", "correct": false }
        ],
        "explanation": "Ensuring the audio device is connected and not muted is the first troubleshooting step."
    },
    {
        "issue": "User reports frequent pop-up ads.",
        "options": [
            { "text": "Run an antivirus or malware scan.", "correct": true },
            { "text": "Adjust the screen resolution.", "correct": false },
            { "text": "Change the desktop wallpaper.", "correct": false },
            { "text": "Turn off the Wi-Fi.", "correct": false }
        ],
        "explanation": "Pop-up ads are often caused by adware or malware."
    },
    {
        "issue": "User accidentally deleted an important file.",
        "options": [
            { "text": "Check the recycle bin for the file.", "correct": true },
            { "text": "Turn off notifications.", "correct": false },
            { "text": "Ask them to restart their computer.", "correct": false },
            { "text": "Update the sound driver.", "correct": false }
        ],
        "explanation": "Deleted files can often be recovered from the recycle bin."
    }
]
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
