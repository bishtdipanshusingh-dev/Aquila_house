<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CyberShield Pro | Enterprise Security Education</title>
    <style>
        :root {
            --primary: #00f2ff;
            --secondary: #7000ff;
            --dark: #050505;
            --card-bg: #111111;
            --text: #ffffff;
            --gray: #a0a0a0;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', -apple-system, sans-serif;
            background-color: var(--dark);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* --- NAVIGATION --- */
        nav {
            display: flex;
            justify-content: space-between; /* This pushes the logo and brand apart */
            align-items: center;
            padding: 15px 5%;
            background: rgba(0, 0, 0, 0.95);
            border-bottom: 1px solid #222;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .brand-name { 
            font-size: 1.5rem; 
            font-weight: 800; 
            color: var(--primary); 
            letter-spacing: -1px; 
        }

        /* LOGO STYLING */
        .logo-container img {
            height: 50px; /* Adjust height as needed */
            width: auto;
            display: block;
            border-radius: 5px;
            /* If you don't have a logo yet, this border helps you see where it is */
            border: 1px dashed var(--gray); 
        }

        /* --- HERO SECTION --- */
        .hero {
            height: 90vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&q=80&w=1500');
            background-size: cover;
            padding: 0 20px;
        }

        .hero h1 { font-size: clamp(2.5rem, 8vw, 4.5rem); margin-bottom: 10px; text-transform: uppercase; }
        .hero p { font-size: 1.2rem; color: var(--gray); max-width: 600px; margin-bottom: 30px; }

        /* --- STATS BAR --- */
        .stats-bar {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            background: var(--secondary);
            padding: 40px 10%;
            width: 100%;
            text-align: center;
        }
        .stat-item { margin: 10px; }
        .stat-item h2 { font-size: 2.5rem; }

        /* --- MAIN CONTENT --- */
        .section-padding { padding: 80px 10%; }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            color: var(--primary);
        }

        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--card-bg);
            padding: 40px;
            border-radius: 15px;
            border: 1px solid #222;
            transition: 0.4s;
        }

        .feature-card:hover {
            border-color: var(--primary);
            box-shadow: 0 0 20px rgba(0, 242, 255, 0.2);
            transform: translateY(-10px);
        }

        /* --- INTERACTIVE QUIZ --- */
        .quiz-container {
            background: var(--card-bg);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            border: 2px dashed var(--secondary);
        }

        .btn {
            padding: 15px 40px;
            font-size: 1rem;
            font-weight: bold;
            text-transform: uppercase;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
            margin: 10px;
        }

        .btn-primary { background: var(--primary); color: #000; }
        .btn-primary:hover { box-shadow: 0 0 30px var(--primary); }

        footer {
            text-align: center;
            padding: 50px;
            border-top: 1px solid #222;
            color: var(--gray);
        }

    </style>
</head>
<body>

    <nav>
        <div class="brand-name">AQUILA house</div>
    </nav>

    <section class="hero">
        <h1>Global Data Defense</h1>
        <p>Your digital security is our priority. Learn how to stay protected in an increasingly connected world.</p>
        <button class="btn btn-primary">Start Learning</button>
    </section>

    <div class="stats-bar">
        <div class="stat-item"><h2>2,200</h2><p>Attacks Daily</p></div>
        <div class="stat-item"><h2>$8.1M</h2><p>Avg Breach Cost</p></div>
        <div class="stat-item"><h2>95%</h2><p>Due to Human Error</p></div>
    </div>

    <section class="section-padding">
        <h2 class="section-title">Security Pillars</h2>
        <div class="grid-container">
            <div class="feature-card">
                <h3>Encryption</h3>
                <p>Ensuring your data is unreadable to anyone without the proper decryption key.</p>
            </div>
            <div class="feature-card">
                <h3>Multi-Factor Auth</h3>
                <p>Adding layers of protection beyond just a simple password.</p>
            </div>
            <div class="feature-card">
                <h3>Threat Detection</h3>
                <p>Identifying and neutralizing malicious behavior before it causes damage.</p>
            </div>
        </div>
    </section>

    <section class="section-padding">
        <div class="quiz-container">
            <h2>Instant Security Quiz</h2>
            <p>Is public Wi-Fi safe for banking?</p>
            <button class="btn" onclick="checkQuiz(false)" style="background:#333; color:white;">Yes</button>
            <button class="btn" onclick="checkQuiz(true)" style="background:#333; color:white;">No</button>
            <h3 id="quiz-result" style="margin-top:20px;"></h3>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 CyberShield Education. All rights reserved.BY DIPANSHU IN</p>
    </footer>

    <script>
        function checkQuiz(isCorrect) {
            const res = document.getElementById('quiz-result');
            if(isCorrect) {
                res.innerText = "Correct! Use a VPN on public networks.";
                res.style.color = "#00ff88";
            } else {
                res.innerText = "Incorrect! Public Wi-Fi is highly vulnerable.";
                res.style.color = "#ff4444";
            }
        }
    </script>
</body>
</html>
