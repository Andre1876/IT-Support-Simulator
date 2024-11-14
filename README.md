# IT-Support-Technician-Animation

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive IT Support Desk</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #e8f4f8;
        }

        .office {
            position: relative;
            width: 400px;
            height: 300px;
            background-color: #b0d4f1;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }

        .desk {
            position: absolute;
            bottom: 20px;
            width: 100%;
            height: 40px;
            background-color: #646f8d;
        }

        .computer {
            position: absolute;
            top: 20px;
            left: 130px;
            width: 120px;
            height: 80px;
            background-color: #2f3d5e;
            border-radius: 5px;
        }

        .screen {
            width: 90%;
            height: 60%;
            background-color: #1c293f;
            margin: 10px auto;
            border-radius: 3px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            color: #a4cdf7;
            animation: typing 3s infinite;
        }

        @keyframes typing {
            0%, 100% { content: 'Typing...'; }
            50% { content: 'Working on tickets...'; }
        }

        .chair {
            position: absolute;
            bottom: 0;
            left: 90px;
            width: 60px;
            height: 40px;
            background-color: #5b6b82;
            border-radius: 5px 5px 0 0;
        }

        .requests {
            position: absolute;
            top: 130px;
            right: 20px;
            width: 80px;
            padding: 10px;
            background-color: #4b6584;
            border-radius: 5px;
            cursor: pointer;
            color: #fff;
            text-align: center;
            font-size: 14px;
            transition: 0.3s ease;
        }

        .requests:hover {
            background-color: #2d4059;
        }

        .popup {
            position: absolute;
            bottom: 70px;
            right: 0;
            width: 200px;
            background-color: #fff;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 15px;
            font-size: 12px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            display: none;
        }

        .close {
            position: absolute;
            top: 5px;
            right: 10px;
            cursor: pointer;
            color: #888;
            font-weight: bold;
        }

    </style>
</head>
<body>

    <div class="office">
        <div class="computer">
            <div class="screen">Typing...</div>
        </div>
        <div class="desk"></div>
        <div class="chair"></div>
        <div class="requests" onclick="showPopup()">Client Request</div>
        <div class="popup" id="popup">
            <span class="close" onclick="closePopup()">&times;</span>
            <p><strong>Client:</strong> “I’m unable to connect to the VPN. Can you help me out?”</p>
            <button onclick="respondToClient()">Respond</button>
        </div>
    </div>

    <script>
        function showPopup() {
            document.getElementById('popup').style.display = 'block';
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
        }

        function respondToClient() {
            alert("Response Sent: 'Hello! I'm looking into the VPN issue now.'");
            closePopup();
        }
    </script>

</body>
</html>
