<!DOCTYPE html>
<html>
<head>
    <title>Happy Valentine's Day ❤️</title>
    <meta charset="UTF-8">
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom right, #ff9a9e, #fad0c4);
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
        }

        /* Initial screen */
        #intro {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        #openBtn {
            background: #e91e63;
            color: white;
            padding: 20px 40px;
            font-size: 22px;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        #openBtn:hover {
            background: #d81b60;
        }

        /* Letter card */
        .card {
            display: none;
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            max-width: 600px;
            margin: 100px auto;
            position: relative;
            z-index: 2;
            opacity: 0;
            transition: opacity 2s ease-in;
        }

        h1 {
            color: #e91e63;
        }

        p {
            font-size: 18px;
            line-height: 1.6;
        }

        /* Floating hearts */
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background: red;
            transform: rotate(45deg);
            animation: float 6s infinite ease-in;
        }

        .heart::before,
        .heart::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
        }

        .heart::before {
            top: -10px;
            left: 0;
        }

        .heart::after {
            left: -10px;
            top: 0;
        }

        @keyframes float {
            0% {
                bottom: -50px;
                opacity: 1;
            }
            100% {
                bottom: 100%;
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <!-- Background Music -->
    <iframe width="0" height="0"
        src="https://www.youtube.com/embed/zKnA6WbRSCk?autoplay=1&loop=1&playlist=zKnA6WbRSCk"
        frameborder="0"
        allow="autoplay">
    </iframe>

    <!-- Initial screen -->
    <div id="intro">
        <button id="openBtn">Click to open your letter 💌</button>
    </div>

    <!-- Letter card -->
    <div class="card" id="letterCard">
        <h1>Happy Valentine’s Day 💌</h1>
        <p>
        I was thinking about us today, and I realized that “thank you” isn't a big enough phrase for everything you give me.
        Even with all these miles between us, you’re the person who makes my world feel quiet and safe when everything else is loud.
        <br><br>
        Distance is supposed to make things harder, but loving you is the easiest thing I’ve ever done.
        Every day with you feels like a gift I forgot to open until now — a reminder that no matter where I am, I’m never really alone because I have you with me.
        <br><br>
        Thank you for being my person, my constant, and my home, even from a distance.
        I’m counting down the seconds until “see you soon” becomes “finally here.”
        <br><br>
        ❤️ I love you more than any distance could ever measure. ❤️
        </p>
    </div>

    <!-- Floating Hearts Generator -->
    <script>
        const openBtn = document.getElementById("openBtn");
        const letterCard = document.getElementById("letterCard");
        const intro = document.getElementById("intro");

        openBtn.addEventListener("click", () => {
            intro.style.display = "none";
            letterCard.style.display = "block";
            setTimeout(() => {
                letterCard.style.opacity = 1;
            }, 100);

            // Start hearts
            function createHeart() {
                const heart = document.createElement("div");
                heart.classList.add("heart");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 6000);
            }

            setInterval(createHeart, 300);
        });
    </script>

</body>
</html>