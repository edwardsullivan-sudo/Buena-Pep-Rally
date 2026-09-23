# Buena-Pep-Rally
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Magenta Screen</title>
    <style>
        /* Resets margins and stretches the page to fill the screen */
        html, body {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            background-color: #FF00FF; /* Pure Magenta Hex Code */
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            font-family: sans-serif;
        }

        /* Styling for the optional fullscreen button */
        .fs-button {
            padding: 12px 24px;
            font-size: 16px;
            font-weight: bold;
            color: #FF00FF;
            background-color: white;
            border: none;
            border-radius: 25px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: transform 0.1s ease;
        }

        .fs-button:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body>

    <!-- Optional: Button to hide mobile browser bars for full immersion -->
    <button class="fs-button" id="fullscreenBtn">Go Immersive Fullscreen</button>

    <script>
        const btn = document.getElementById('fullscreenBtn');

        btn.addEventListener('click', () => {
            // Request full screen mode
            if (document.documentElement.requestFullscreen) {
                document.documentElement.requestFullscreen();
            } else if (document.documentElement.webkitRequestFullscreen) { /* Safari support */
                document.documentElement.webkitRequestFullscreen();
            } else if (document.documentElement.msRequestFullscreen) { /* IE/Edge support */
                document.documentElement.msRequestFullscreen();
            }
            
            // Hide the button once fullscreen is activated
            btn.style.display = 'none';
        });

        // Hide button automatically if user exits fullscreen manually
        document.addEventListener('fullscreenchange', () => {
            if (!document.fullscreenElement) {
                btn.style.display = 'block';
            }
        });
        document.addEventListener('webkitfullscreenchange', () => {
            if (!document.webkitFullscreenElement) {
                btn.style.display = 'block';
            }
        });
    </script>
</body>
</html>
