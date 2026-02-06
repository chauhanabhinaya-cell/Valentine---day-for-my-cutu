# Valentine---day-for-my-cutu
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Dancing Script', cursive;
            background: linear-gradient(135deg, #ffe6e6, #ffb3ba, #ffdfba);
            color: #d63384;
            text-align: center;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
            position: relative;
            transition: background 0.5s, transform 0.5s;
        }
        .shake {
            animation: shake 0.5s infinite;
        }
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            50% { transform: translateX(5px); }
            75% { transform: translateX(-5px); }
        }
        .invert {
            filter: invert(1);
        }
        .heart {
            position: absolute;
            color: #ff1493;
            font-size: 2em;
            animation: float 6s infinite ease-in-out;
            pointer-events: none;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(180deg); }
        }
        h1 {
            font-size: 4em;
            color: #e91e63;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.4);
            animation: pulse 2s infinite;
            margin-bottom: 20px;
        }
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        .gallery {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            margin: 30px 0;
        }
        .gallery img {
            width: 180px;
            height: 180px;
            object-fit: cover;
            margin: 15px;
            border-radius: 50%;
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
            transition: transform 0.4s;
        }
        .gallery img:hover {
            transform: scale(1.2) rotate(5deg);
        }
        video {
            width: 100%;
            max-width: 600px;
            border-radius: 15px;
            margin: 20px 0;
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
        }
        .question {
            font-size: 2.5em;
            margin: 40px 0;
            animation: bounce 2s infinite;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        .buttons {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 30px 0;
            position: relative;
        }
        button {
            font-family: 'Dancing Script', cursive;
            font-size: 1.8em;
            padding: 20px 40px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s;
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
            position: relative;
        }
        #yes {
            background: linear-gradient(45deg, #ff69b4, #ff1493);
            color: white;
        }
        #yes:hover {
            transform: scale(1.2);
            box-shadow: 0 8px 16px rgba(255, 105, 180, 0.5);
        }
        #no {
            background: linear-gradient(45deg, #ccc, #aaa);
            color: #666;
            transition: transform 0.1s;
        }
        #no:hover {
            transform: scale(1.05);
        }
        .dodging {
            animation: dodge 0.5s infinite alternate;
        }
        @keyframes dodge {
            0% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(50px) translateY(-20px); }
            50% { transform: translateX(-30px) translateY(30px); }
            75% { transform: translateX(40px) translateY(-10px); }
            100% { transform: translateX(0) translateY(0); }
        }
        .hidden {
            display: none;
        }
        .crazy-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 20;
            animation: crazyPulse 0.5s infinite;
        }
        @keyframes crazyPulse {
            0%, 100% { background: rgba(255, 0, 0, 0.8); }
            50% { background: rgba(255, 255, 0, 0.8); }
        }
        .crazy-text {
            font-size: 3em;
            color: white;
            text-shadow: 2px 2px 4px black;
            animation: crazyBounce 0.5s infinite;
        }
        @keyframes crazyBounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }
        .pleading {
            font-size: 2em;
            color: white;
            margin-top: 20px;
        }
        .celebration {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.95);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10;
            animation: fadeIn 1s;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .growing-yes {
            font-size: 2em;
            animation: grow 6s infinite linear;
            background: linear-gradient(45deg, #ff69b4, #ff1493);
            color: white;
            padding: 30px;
            border-radius: 50px;
            box-shadow: 0 0 30px rgba(255, 105, 180, 0.7);
            margin-bottom: 20px;
        }
        @keyframes grow {
            0% { transform: scale(1); font-size: 2em; }
            100% { transform: scale(6); font-size: 12em; }
        }
        .poem {
            font-size: 1.5em;
            color: #d63384;
            max-width: 600px;
            line-height: 1.6;
            animation: fadeIn 2s;
        }
        .confetti {
            position: absolute;
            width: 8px;
            height: 8px;
            background: #ff69b4;
            animation: confettiFall 4s infinite ease-in-out;
        }
        @keyframes confettiFall {
            0% { transform: translateY(-100vh) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }
        @media (max-width: 768px) {
            h1 { font-size: 3em; }
            .question { font-size: 2em; }
            button { font-size: 1.5em; padding: 15px 30px; }
            .gallery img { width: 120px; height: 120px; }
        }
    </style>
</head>
<body>
    <!-- Floating Hearts -->
    <div class="heart" style="left: 5%; animation-delay: 0s;">❤️</div>
    <div class="heart" style="left: 15%; animation-delay: 0.5s;">💖</div>
    <div class="heart" style="left: 25%; animation-delay: 1s;">💕</div>
    <div class="heart" style="left: 35%; animation-delay: 1.5s;">❤️</div>
    <div class="heart" style="left: 45%; animation-delay: 2s;">💖</div>
    <div class="heart" style="left: 55%; animation-delay: 2.5s;">💕</div>
    <div class="heart" style="left: 65%; animation-delay: 3s;">❤️</div>
    <div class="heart" style="left: 75%; animation-delay: 3.5s;">💖</div>
    <div class="heart" style="left: 85%; animation-delay: 4s;">💕</div>
    <div class="heart" style="left: 95%; animation-delay: 4.5s;">❤️</div>

    <h1>Happy Valentine's Day! 💕</h1>

    <!-- Photo Gallery -->
    <div class="gallery">
        <img src="https://images.unsplash.com/photo-1518709268805-4e9042af2176?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Roses">
        <img src="https://images.unsplash.com/photo-1526047932273-341f2a7631f9?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Hearts">
        <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Candlelight">
        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Love Note">
        <img src="https://images.unsplash.com/photo-1544717297-fa95b6ee9643?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Chocolate">
        <img src="https://images.unsplash.com/photo-1518895949257-7621c3c786d7?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Teddy Bear">
    </div>

    <!-- Video -->
    <video controls>
        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <!-- Question and Buttons -->
    <div class="question">Will you be my Valentine? 💖</div>
    <div class="buttons" id="buttons">
        <button id="yes">Yes! 😍</button>
        <button id="no">No</button>
    </div>

    <!-- Crazy No Overlay (Hidden Initially) -->
    <div class="crazy-overlay hidden" id="crazyOverlay">
        <div class="crazy-text">😢 Please say Yes! 😭</div>
        <div class="pleading">I promise it'll be fun! Click Yes to stop the madness! 💕</div>
    </div>

    <!-- Celebration Overlay (Hidden Initially) -->
    <div class="celebration hidden" id="celebration">
        <div class="growing-yes">Yes! ❤️ You're my Valentine! 💕</div>
        <div class="poem">
            Roses are red, violets are blue,<br>
            My heart beats for you, forever true.<br>
            With every smile, my love grows,<br>
            You're the one my heart chose! 💖
        </div>
        <!-- Confetti -->
        <div class="confetti" style="left: 10%; animation-delay: 0s;"></div>
        <div class="confetti" style="left: 20%; animation-delay: 0.3s;"></div>
        <div class="confetti" style="left: 30%; animation-delay: 0.6s;"></div>
        <div class="confetti" style="left: 40%; animation-delay: 0.9s;"></div>
        <div class="confetti" style="left: 50%; animation-delay: 1.2s;"></div>
        <div class="confetti" style="left: 60%; animation-delay: 1.5s;"></div>
        <div class="confetti" style="left: 70%; animation-delay: 1.8s;"></div>
        <div class="confetti" style="left: 80%; animation-delay: 2.1s;"></div>
        <div class="confetti" style="left: 90%; animation-delay: 2.4s;"></div>
    </div>

    <script>
        const yesBtn = document.getElementById('yes');
        const noBtn = document.getElementById('no');
        const buttons = document.getElementById('buttons');
        const crazyOverlay = document.getElementById('crazyOverlay');
        const celebration = document.getElementById('celebration');
        const body = document.body;

        let crazyMode = false;

        // No button: Trigger crazy effects and force Yes
        noBtn.addEventListener('click', () => {
            if (!crazyMode) {
                crazyMode = true;
                crazyOverlay.classList.remove('hidden');
                body.classList.add('shake', 'invert');
                noBtn.classList.add('dodging');
                // Add random messages
                setInterval(() => {
                    const messages = ["😭 Nooo!", "💔 Please reconsider!", "❤️ Say Yes!", "😢 I can't take it!"];
                    const randomMsg = messages[Math.floor(Math.random() * messages.length)];
                    const msgDiv = document.createElement('div');
                    msgDiv.textContent = randomMsg;
                    msgDiv.style.position = 'absolute';
                    msgDiv.style.left = Math.random() * 80 + '%';
                    msgDiv.style.top = Math.random() * 80 + '%';
                    msgDiv.style.fontSize = '2em';
                    msgDiv.style.color = '#ff0000';
                    msgDiv.style.animation = 'crazyBounce 0.5s infinite';
                    document.body.appendChild(msgDiv);
                    setTimeout(() => msgDiv.remove(), 2000);
                }, 1000);
            }
        });

        // Yes button: Stop crazy effects and celebrate
        yesBtn.addEventListener('click', () => {
            crazyMode = false;
            crazyOverlay.classList.add('hidden');
            body.classList.remove('shake', 'invert');
            noBtn.classList.remove('dodging');
            buttons.classList.add('hidden');
            celebration.classList.remove('hidden');
            // Add more hearts
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.textContent = '💖';
                heart.style.left = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 5 + 's';
                document.body.appendChild(heart);
            }
        });
    </script>
</body>
</html>
