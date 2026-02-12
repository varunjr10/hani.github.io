<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Hani</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;700&family=Great+Vibes&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
      
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background-color: #050505;
            color: #fff;
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
            overflow-y: hidden; 
        }

      
        .stars {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 50%, #1a0b14 0%, #000000 100%);
            z-index: -2;
        }
        .glow-orb {
            position: absolute;
            width: 400px; height: 400px;
            background: radial-gradient(circle, rgba(255, 20, 147, 0.2) 0%, rgba(0,0,0,0) 70%);
            border-radius: 50%;
            animation: float 10s infinite ease-in-out;
            z-index: -1;
        }

        @keyframes float {
            0% { transform: translate(0, 0); }
            50% { transform: translate(50px, -50px); }
            100% { transform: translate(0, 0); }
        }

     
        .screen {
            height: 100vh;
            width: 100vw;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: absolute;
            top: 0; left: 0;
            transition: opacity 1s ease, transform 1s ease;
            opacity: 0;
            pointer-events: none;
        }
        
        .screen.active {
            opacity: 1;
            pointer-events: all;
            transform: translateY(0);
        }

        .screen.exit {
            opacity: 0;
            transform: translateY(-50px);
        }

        
        h1 {
            font-size: 4rem;
            text-transform: uppercase;
            letter-spacing: 5px;
            text-shadow: 0 0 20px rgba(255, 20, 147, 0.8);
            margin-bottom: 20px;
            text-align: center;
        }

        h2 {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: #ff69b4;
        }

        p {
            font-size: 1.2rem;
            max-width: 600px;
            text-align: center;
            line-height: 1.6;
            margin-bottom: 40px;
            color: #ddd;
        }

        
        .btn {
            padding: 15px 40px;
            border: 2px solid #ff1493;
            background: transparent;
            color: #fff;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
            border-radius: 30px;
        }

        .btn:hover {
            background: #ff1493;
            box-shadow: 0 0 30px #ff1493;
        }

   
        .gallery {
            display: flex;
            gap: 20px;
            perspective: 1000px;
        }

        .polaroid {
            width: 200px;
            height: 280px;
            background: white;
            padding: 10px 10px 40px 10px;
            color: #333;
            text-align: center;
            font-weight: bold;
            font-family: 'Great Vibes', cursive;
            font-size: 1.5rem;
            transform: rotate(-5deg);
            transition: 0.5s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            opacity: 0; /* Hidden initially */
        }
        
        .polaroid img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            background: #eee;
        }

        .polaroid:nth-child(2) { transform: rotate(5deg) translateY(-20px); transition-delay: 0.2s; }
        .polaroid:nth-child(3) { transform: rotate(-3deg); transition-delay: 0.4s; }

        .polaroid.show {
            opacity: 1;
            transform: rotate(var(--r)) translateY(0);
        }

      
        .valentine-box {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 50px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.2);
            text-align: center;
        }

        .choices {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
        }

        .btn-yes { background: #ff1493; border: none; }
        .btn-no { background: #333; border: none; }

    </style>
</head>
<body>

    <div class="stars"></div>
    <div class="glow-orb" style="top: 10%; left: 10%;"></div>
    <div class="glow-orb" style="bottom: 10%; right: 10%; background: radial-gradient(circle, rgba(100, 149, 237, 0.2) 0%, rgba(0,0,0,0) 70%);"></div>

    <div class="screen active" id="screen1">
        <h2>hey hani...</h2>
        <h1>I have a question.</h1>
        <p>but first, are you worthy? hmmmmm lets review your profile.</p>
        <button class="btn" onclick="nextScreen(2)">Proceed</button>
    </div>

    <div class="screen" id="screen2">
        <h2>what.the.fuck.</h2>
        <div class="gallery">
            <div class="polaroid" style="--r: -5deg;">
                <img src="https://files.catbox.moe/n5pocc.jpg" alt="Us">
                <p>ur so prettyyyyyy so fucking pretttyyyy</p>
            </div>
            <div class="polaroid" style="--r: 5deg;">
                <img src="https://files.catbox.moe/7lqx9c.png" alt="Us">
                <p>adorableeeeeeee cutie cutie cutie pie</p>
            </div>
            <div class="polaroid" style="--r: -2deg;">
                <img src="https://files.catbox.moe/03n0zw.png" alt="Us">
                <p>god really took his time creating u</p>
            </div>
        </div>
        <br><br>
        <button class="btn" onclick="nextScreen(3)">Continue</button>
    </div>

    <div class="screen" id="screen3">
        <div class="valentine-box">
            <h2>harshita</h2>
            <p>You make my world brighter. There is no one else I'd rather piss off for the rest of my life.</p>
            <h2>Will you be my Valentine?</h2>
            
            <div class="choices">
                <button class="btn btn-yes" onclick="celebrate()">ABSOLUTELY YES</button>
                <button class="btn btn-no" id="noBtn" onmouseover="dodge()">NO</button>
            </div>
        </div>
    </div>

    <div class="screen" id="screen4">
        <h1>I KNEW YOU WERE THE SMARTEST LITTLE BABY EVER GOOD JOB GOOD JOB 😝😝😝</h1>
        <h2>💖 i love you so much so much so much. 💖</h2>
        <p>brace yourself for ALLL MY GIFTS AND ALL MY LOVE AND ATTENTION IM GONNA SHOWER YOU WITH.</p>
    </div>

    <script>
        function nextScreen(num) {
           
            document.querySelectorAll('.screen').forEach(s => {
                s.classList.remove('active');
                s.classList.add('exit');
            });

            
            const next = document.getElementById('screen' + num);
            next.classList.remove('exit');
            next.classList.add('active');

            
            if(num === 2) {
                setTimeout(() => {
                    document.querySelectorAll('.polaroid').forEach(p => p.classList.add('show'));
                }, 100);
            }
        }

        function dodge() {
            const btn = document.getElementById('noBtn');
            const x = (Math.random() - 0.5) * 300;
            const y = (Math.random() - 0.5) * 300;
            btn.style.transform = `translate(${x}px, ${y}px)`;
        }

        function celebrate() {
            nextScreen(4);
            
            
            var duration = 5 * 1000;
            var end = Date.now() + duration;

            (function frame() {
                confetti({
                    particleCount: 5,
                    angle: 60,
                    spread: 55,
                    origin: { x: 0 },
                    colors: ['#ff1493', '#ffd700', '#ffffff']
                });
                confetti({
                    particleCount: 5,
                    angle: 120,
                    spread: 55,
                    origin: { x: 1 },
                    colors: ['#ff1493', '#ffd700', '#ffffff']
                });

                if (Date.now() < end) {
                    requestAnimationFrame(frame);
                }
            }());
        }
    </script>
</body>
</html>
