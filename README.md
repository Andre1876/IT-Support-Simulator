<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Troubleshooting Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .question {
            margin-bottom: 20px;
        }
        .question p {
            font-weight: bold;
        }
        .options label {
            display: block;
            margin: 5px 0;
            cursor: pointer;
        }
        .options input[type="radio"] {
            margin-right: 10px;
        }
        .explanation {
            margin-top: 10px;
            font-style: italic;
            color: #666;
        }
        .submit-btn {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>IT Troubleshooting Quiz</h1>
        <form id="quiz-form">
            <!-- Question 1 -->
            <div class="question">
                <p>1. The user's computer won't turn on.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q1" value="1"> Check the power cable and connection.
                    </label>
                    <label>
                        <input type="radio" name="q1" value="2"> Restart the router.
                    </label>
                    <label>
                        <input type="radio" name="q1" value="3"> Check for software updates.
                    </label>
                    <label>
                        <input type="radio" name="q1" value="4"> Clear the browser cache.
                    </label>
                </div>
                <div class="explanation" id="explanation-q1"></div>
            </div>
            
            <!-- Question 2 -->
            <div class="question">
                <p>2. User cannot access Wi-Fi on their laptop.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q2" value="1"> Check if airplane mode is turned off.
                    </label>
                    <label>
                        <input type="radio" name="q2" value="2"> Restart the desktop computer.
                    </label>
                    <label>
                        <input type="radio" name="q2" value="3"> Increase the screen brightness.
                    </label>
                    <label>
                        <input type="radio" name="q2" value="4"> Clear cookies and cache.
                    </label>
                </div>
                <div class="explanation" id="explanation-q2"></div>
            </div>

            <!-- Question 3 -->
            <div class="question">
                <p>3. User’s email inbox is not receiving messages.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q3" value="1"> Check the spam/junk folder.
                    </label>
                    <label>
                        <input type="radio" name="q3" value="2"> Restart the computer.
                    </label>
                    <label>
                        <input type="radio" name="q3" value="3"> Clear browser history.
                    </label>
                    <label>
                        <input type="radio" name="q3" value="4"> Suggest they contact the ISP.
                    </label>
                </div>
                <div class="explanation" id="explanation-q3"></div>
            </div>

            <!-- Question 4 -->
            <div class="question">
                <p>4. The printer is not printing.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q4" value="1"> Check if the printer is connected and turned on.
                    </label>
                    <label>
                        <input type="radio" name="q4" value="2"> Update the operating system.
                    </label>
                    <label>
                        <input type="radio" name="q4" value="3"> Install antivirus software.
                    </label>
                    <label>
                        <input type="radio" name="q4" value="4"> Reinstall the browser.
                    </label>
                </div>
                <div class="explanation" id="explanation-q4"></div>
            </div>

            <!-- Question 5 -->
            <div class="question">
                <p>5. User forgot their system password.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q5" value="1"> Help them reset their password.
                    </label>
                    <label>
                        <input type="radio" name="q5" value="2"> Install new software.
                    </label>
                    <label>
                        <input type="radio" name="q5" value="3"> Suggest they wait 24 hours and try again.
                    </label>
                    <label>
                        <input type="radio" name="q5" value="4"> Turn off notifications.
                    </label>
                </div>
                <div class="explanation" id="explanation-q5"></div>
            </div>

            <!-- Question 6 -->
            <div class="question">
                <p>6. The browser is running slowly on the user’s computer.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q6" value="1"> Clear cookies and cache.
                    </label>
                    <label>
                        <input type="radio" name="q6" value="2"> Replace the hard drive.
                    </label>
                    <label>
                        <input type="radio" name="q6" value="3"> Update the router’s firmware.
                    </label>
                    <label>
                        <input type="radio" name="q6" value="4"> Lower the screen resolution.
                    </label>
                </div>
                <div class="explanation" id="explanation-q6"></div>
            </div>

            <!-- Question 7 -->
            <div class="question">
                <p>7. A user is receiving many spam emails.</p>
                <div class="options">
                    <label>
                        <input type="radio" name="q7" value="1"> Adjust spam filter settings.
                    </label>
                    <label>
                        <input type="radio" name="q7" value="2"> Turn on airplane mode.
                    </label>
                    <label>
                        <input type="radio" name="q7" value="3"> Change the browser’s language.
                    </label>
                    <label>
                        <input type="radio" name="q7" value="4"> Update the monitor settings.
                    </label>
                </div>
                <div class="explanation" id="explanation-q7"></div>
            </div>

            <!-- Submit Button -->
            <button type="submit" class="submit-btn">Submit Quiz</button>
        </form>
    </div>

    <script>
        // Array of questions with answers and explanations
        const quizData = [
            {
                issue: "The user's computer won't turn on.",
                options: [
                    { text: "Check the power cable and connection.", correct: true },
                    { text: "Restart the router.", correct: false },
                    { text: "Check for software updates.", correct: false },
                    { text: "Clear the browser cache.", correct: false }
                ],
                explanation: "Checking the power cable and connection is the first step for diagnosing a hardware power issue."
            },
            {
                issue: "User cannot access Wi-Fi on their laptop.",
                options: [
                    { text: "Check if airplane mode is turned off.", correct: true },
                    { text: "Restart the desktop computer.", correct: false },
                    { text: "Increase the screen brightness.", correct: false },
                    { text: "Clear cookies and cache.", correct: false }
                ],
                explanation: "Airplane mode blocks wireless connections. Ensure it's off to access Wi-Fi."
            },
            {
                issue: "User’s email inbox is not receiving messages.",
                options: [
                    { text: "Check the spam/junk folder.", correct: true },
                    { text: "Restart the computer.", correct: false },
                    { text: "Clear browser history.", correct: false },
                    { text: "Suggest they contact the ISP.", correct: false }
                ],
                explanation: "Email providers often filter emails to the spam/junk folder."
            },
            {
                issue: "The printer is not printing.",
                options: [
                    { text: "Check if the printer is connected and turned on.", correct: true },
                    {
