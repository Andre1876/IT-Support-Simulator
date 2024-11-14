# IT-Support-Technician-Animation
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Support Technician Animation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .desk {
            background-color: #fff;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            text-align: center;
        }

        .technician {
            margin-bottom: 20px;
        }

        .computer {
            position: relative;
        }

        .computer img {
            width: 200px;
        }

        .ticket {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(255, 255, 255, 0.9);
            border: 1px solid #ccc;
            border-radius: 8px;
            padding: 10px;
            display: none;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="desk">
            <div class="technician">
                <img src="assets/technician.png" alt="IT Technician">
            </div>
            <div class="computer">
                <img src="assets/computer-screen.png" alt="Computer Screen">
                <div class="ticket" id="supportTicket">
                    <p>Support Ticket: Issue Detected!</p>
                    <button id="closeTicket">Close</button>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.1/gsap.min.js"></script>
    <script>
        // Wait for the page to load
        window.onload = function () {
            // Animate technician typing at the desk
            gsap.from(".technician", {
                duration: 1.5,
                opacity: 0,
                y: -50,
                ease: "power3.out"
            });

            // Function to trigger the ticket pop-up animation
            document.querySelector(".computer").addEventListener("click", function() {
                // Show the support ticket
                const ticket = document.getElementById("supportTicket");
                ticket.style.display = 'block';

                // Animate the ticket popping up
                gsap.fromTo(ticket, 
                    { opacity: 0, y: -20 }, 
                    { opacity: 1, y: 0, duration: 0.5, ease: "power2.out" }
                );

                // Animate technician's typing action
                gsap.to(".technician img", {
                    rotation: 5,
                    duration: 1,
                    repeat: 3,
                    yoyo: true,
                    ease: "power2.inOut"
                });
            });

            // Close ticket when button is clicked
            document.getElementById("closeTicket").addEventListener("click", function () {
                const ticket = document.getElementById("supportTicket");
                gsap.to(ticket, { opacity: 0, y: -20, duration: 0.5, ease: "power2.in" });

                setTimeout(function () {
                    ticket.style.display = 'none';
                }, 500);
            });
        };
    </script>

</body>
</html>
