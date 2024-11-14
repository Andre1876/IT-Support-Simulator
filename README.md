# IT-Support-Technician-Animation

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Animation</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            position: relative;
        }

        .desk {
            background-color: #cfcfcf;
            width: 300px;
            height: 200px;
            position: relative;
            border-radius: 10px;
            overflow: hidden;
        }

        .desk-top {
            width: 100%;
            height: 40px;
            background-color: #4c4c4c;
            position: absolute;
            top: 0;
        }

        .person {
            position: absolute;
            bottom: 30px;
            left: 50px;
            width: 50px;
            height: 100px;
            z-index: 1;
        }

        .head {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background-color: #f9d5a7;
            margin: 0 auto;
        }

        .body {
            width: 50px;
            height: 60px;
            background-color: #6a9fb5;
            margin: 5px auto;
        }

        .arms {
            width: 70px;
            height: 10px;
            background-color: #e4a84e;
            position: absolute;
            left: -10px;
            bottom: 20px;
        }

        .legs {
            width: 50px;
            height: 10px;
            background-color: #4d7f9e;
            position: absolute;
            left: 0;
            bottom: 0;
        }

        .computer-screen {
            position: absolute;
            top: 10px;
            left: 20px;
            width: 60px;
            height: 40px;
            background-color: #333;
            border-radius: 5px;
            z-index: 2;
        }

        .animation {
            animation: moveArms 2s infinite;
        }

        @keyframes moveArms {
            0% {
                transform: rotate(0deg);
            }
            50% {
                transform: rotate(20deg);
            }
            100% {
                transform: rotate(0deg);
            }
        }

    </style>
</head>
<body>
    <div class="container">
        <div class="desk">
            <div class="desk-top"></div>
            <div class="person">
                <div class="head"></div>
                <div class="body"></div>
                <div class="arms animation"></div>
                <div class="legs"></div>
            </div>
            <div class="computer-screen"></div>
        </div>
    </div>

    <script>
        // Add interactivity or animation
        document.querySelector('.person').addEventListener('click', function() {
            alert("IT Support is working on a ticket!");
        });
    </script>
</body>
</html>
