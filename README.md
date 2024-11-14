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
