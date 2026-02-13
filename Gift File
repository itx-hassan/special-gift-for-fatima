<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Forever Valentine</title>
    <link
        href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap"
        rel="stylesheet">
    <style>
        :root {
            --primary-color: #e31b6d;
            --secondary-color: #ff99ac;
            --accent-color: #fff0f3;
            --text-color: #fff;
            --bg-gradient: linear-gradient(135deg, #2e001f 0%, #680026 100%);
            --glass-bg: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: var(--bg-gradient);
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--text-color);
            perspective: 1000px;
            position: relative;
        }

        /* ===== LIVE BUBBLES WALLPAPER ===== */
        #liveWallpaper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }

        .bubble {
            position: absolute;
            width: 15px;
            height: 15px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 50%;
            animation: float 10s ease-in-out infinite alternate;
        }

        @keyframes float {
            0% { transform: translate3d(0,0,0); }
            25% { transform: translate3d(2px, 1px, 2px); }
            50% { transform: translate3d(-2px, -1px, -2px); }
            75% { transform: translate3d(1px, -1px, 1px); }
            100% { transform: translate3d(-1px, 1px, -1px); }
        }

        .container {
            background: var(--glass-bg);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid var(--glass-border);
            padding: 2.5rem;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            text-align: center;
            max-width: 90%;
            width: 600px;
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: none;
            flex-direction: column;
            align-items: center;
        }

        .container.active {
            display: flex;
            animation: fadeIn 0.8s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 { font-size: 3rem; margin-bottom: 1.5rem; color: var(--secondary-color); text-shadow: 0 0 10px rgba(227,27,109,0.8); }

        @media (max-width: 600px) {
            h1 { font-size: 2rem; }
            .container { padding: 1.5rem; }
        }

        p { font-size: 1.1rem; margin-bottom: 1.5rem; line-height: 1.7; color: #ddd; }

        .btn {
            padding: 12px 30px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            margin: 10px;
            position: relative;
            background: linear-gradient(45deg, #ff3366, #ff6b6b);
            color: white;
            box-shadow: 0 5px 15px rgba(255,51,102,0.4);
            text-decoration: none;
            display: inline-block;
        }

        .btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(255,51,102,0.6);
        }

        .gallery-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; margin-bottom: 20px; width: 100%; }
        .photo-card { background: white; padding: 10px 10px 25px 10px; border-radius: 2px; box-shadow: 0 5px 15px rgba(0,0,0,0.2); transform: rotate(-3deg); transition: transform 0.3s; }
        .photo-card:nth-child(even) { transform: rotate(3deg); }
        .photo-card:hover { transform: scale(1.05) rotate(0deg); z-index: 10; }
        .photo-card img { width: 100%; height: 120px; object-fit: cover; border-radius: 2px; }

        .letter-content {
            font-size: 1rem;
            text-align: left;
            background: rgba(255,255,255,0.9);
            color: #333;
            padding: 25px;
            border-radius: 5px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-bottom: 20px;
            min-height: 220px;
            position: relative;
        }

        .cursor::after { content: '|'; animation: blink 1s infinite; }
        @keyframes blink { 50% { opacity: 0; } }

        .proposal-btns { position: relative; height: 80px; width: 100%; display: flex; justify-content: center; align-items: center; gap: 20px; }
        #noBtn { background: #4a4a4a; box-shadow: 0 5px 15px rgba(0,0,0,0.3); }

        /* ===== MUSIC ICON UPDATE: DARK PINK ===== */
        .music-control {
            position: fixed;
            top: 20px; 
            right: 20px;
            background: #b0124a; /* dark pink shade of primary #e31b6d */
            border: 1px solid #e31b6d; /* slightly lighter pink border */
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            z-index: 100;
            font-size: 20px;
            color: #fff;
            transition: all 0.3s;
        }

        .music-control:hover { 
            background: #c3165e; /* slightly brighter on hover */
            transform: rotate(360deg); 
        }

        .burst-box { position: fixed; width: 12px; height: 12px; z-index: 999; pointer-events: none; }
        @keyframes burstAnimation { 0% { transform: translate(0,0) scale(1); opacity: 1; } 100% { transform: translate(var(--x), var(--y)) scale(0.5); opacity: 0; } }
    </style>
</head>

<body>
    <!-- LIVE WALLPAPER CONTAINER -->
    <div id="liveWallpaper"></div>

    <!-- Screen 1: Intro -->
    <div class="container active" id="screen-intro">
        <h1>Hello My Princess Fatima!</h1>
        <p>Let's start our special journey.</p>
        <button class="btn" onclick="nextScreen('screen-gallery')">Start</button>
    </div>

    <!-- Screen 2: Gallery -->
    <div class="container" id="screen-gallery">
        <h1>Our Memories</h1>
        <p>Every moment together is precious.</p>
        <div class="gallery-grid">
            <div class="photo-card"><img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?w=400" alt="Memory 1"></div>
            <div class="photo-card"><img src="https://images.unsplash.com/photo-1529333166437-7750a6dd5a70?w=400" alt="Memory 2"></div>
            <div class="photo-card"><img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?w=400" alt="Memory 3"></div>
            <div class="photo-card"><img src="https://images.unsplash.com/photo-1511988617509-a57c8a288659?w=400" alt="Memory 4"></div>
        </div>
        <button class="btn" onclick="nextScreen('screen-letter')">Next</button>
    </div>

    <!-- Screen 3: Letter -->
    <div class="container" id="screen-letter">
        <h1>For You 💌</h1>
        <div class="letter-content">
            <span id="typewriter-text"></span><span class="cursor"></span>
        </div>
        <button class="btn" id="letter-next-btn" style="opacity: 0; pointer-events: none;" onclick="nextScreen('screen-proposal')">Next</button>
    </div>

    <!-- Screen 4: Proposal -->
    <div class="container" id="screen-proposal">
        <h1>Will You Be My Valentine?</h1>
        <p>You are my sunshine, my heart, my everything.</p>
        <div class="proposal-btns">
            <button class="btn" id="yesBtn" onclick="acceptProposal()">Yes</button>
            <button class="btn" id="noBtn" onmouseover="dodgeButton()">No</button>
        </div>
    </div>

    <!-- Screen 5: Celebration -->
    <div class="container" id="screen-celebration">
        <h1>I Knew It 🤭❤️</h1>
        <img src="https://media.giphy.com/media/26BRv0ThflsHCqDrG/giphy.gif" alt="Celebration" style="width: 100%; border-radius: 10px; margin-bottom: 20px;">
        <p>I love you endlessly, my princess. Every smile of yours brightens my day, and every moment together feels like a dream. 💖</p>
    </div>

    <!-- Audio -->
    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-15.mp3" type="audio/mp3">
    </audio>
    <div class="music-control" onclick="toggleMusic()">🎵</div>

    <script>
        const loveLetterText = "My Sweet Princess Fatima,\n\nFrom the moment I saw you, my heart knew. Your smile, your laugh, your gentle touch make every day magical. I promise to cherish, adore, and love you forever. You are my everything, my dream come true.\n\nSo, I have a very important question...";

        function nextScreen(id) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            if (id === 'screen-letter') startTypewriter();
        }

        let charIndex = 0;
        function startTypewriter() {
            const elem = document.getElementById('typewriter-text');
            elem.innerHTML = "";
            charIndex = 0;
            type();
        }

        function type() {
            if (charIndex < loveLetterText.length) {
                const char = loveLetterText.charAt(charIndex);
                document.getElementById('typewriter-text').innerHTML += char === '\n' ? '<br>' : char;
                charIndex++;
                setTimeout(type, 50);
            } else {
                const btn = document.getElementById('letter-next-btn');
                btn.style.opacity = '1';
                btn.style.pointerEvents = 'auto';
            }
        }

        function dodgeButton() {
            const btn = document.getElementById('noBtn');
            btn.style.position = 'fixed';
            btn.style.left = Math.random() * 80 + 'vw';
            btn.style.top = Math.random() * 80 + 'vh';
        }

        function acceptProposal() {
            nextScreen('screen-celebration');
            triggerBurst();
        }

        function triggerBurst() {
            const colors = ['#ff3366', '#ff6b6b', '#ff99ac', '#ffcc00', '#ff1493', '#00ffff', '#00ff99', '#ff00ff'];
            const centerX = window.innerWidth / 2;
            const centerY = window.innerHeight / 2;

            for (let i = 0; i < 150; i++) {
                const box = document.createElement('div');
                box.classList.add('burst-box');
                box.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                box.style.left = centerX + 'px';
                box.style.top = centerY + 'px';

                const randomX = (Math.random() - 0.5) * 800 + 'px';
                const randomY = (Math.random() - 0.5) * 800 + 'px';
                box.style.setProperty('--x', randomX);
                box.style.setProperty('--y', randomY);
                box.style.animation = "burstAnimation 1.5s ease-out forwards";

                document.body.appendChild(box);

                setTimeout(() => { box.remove(); }, 1500);
            }
        }

        function toggleMusic() {
            const music = document.getElementById('bgMusic');
            if (music.paused) music.play();
            else music.pause();
        }

        // ===== CREATE BUBBLES FOR LIVE WALLPAPER =====
        const liveWallpaper = document.getElementById('liveWallpaper');
        const bubbleCount = 50;

        for (let i = 0; i < bubbleCount; i++) {
            const bubble = document.createElement('div');
            bubble.classList.add('bubble');
            bubble.style.left = Math.random() * window.innerWidth + 'px';
            bubble.style.top = Math.random() * window.innerHeight + 'px';
            bubble.style.width = (10 + Math.random() * 10) + 'px';
            bubble.style.height = bubble.style.width;
            bubble.style.animationDuration = (8 + Math.random() * 4) + 's';
            bubble.style.animationDelay = Math.random() * 5 + 's';
            liveWallpaper.appendChild(bubble);
        }
    </script>
</body>
</html>
