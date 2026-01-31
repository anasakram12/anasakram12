<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anas Akram - Applied AI Engineer</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Rajdhani:wght@300;400;500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #0a0a0a;
            --bg-secondary: #1a1a1a;
            --glass-bg: rgba(20, 20, 20, 0.4);
            --glass-border: rgba(255, 0, 50, 0.2);
            --text-primary: #ffffff;
            --text-secondary: #b8b8b8;
            --accent-red: #ff0033;
            --accent-red-glow: rgba(255, 0, 51, 0.4);
            --accent-black: #000000;
            --gradient-red: linear-gradient(135deg, #ff0033 0%, #cc0029 100%);
            --gradient-dark: linear-gradient(135deg, #1a1a1a 0%, #0a0a0a 100%);
            --shadow-red: 0 0 40px rgba(255, 0, 51, 0.3);
            --shadow-glass: 0 8px 32px 0 rgba(0, 0, 0, 0.5);
        }

        [data-theme="light"] {
            --bg-primary: #f5f5f5;
            --bg-secondary: #ffffff;
            --glass-bg: rgba(255, 255, 255, 0.6);
            --glass-border: rgba(255, 0, 50, 0.3);
            --text-primary: #0a0a0a;
            --text-secondary: #444444;
            --accent-red: #cc0029;
            --accent-red-glow: rgba(204, 0, 41, 0.3);
            --gradient-dark: linear-gradient(135deg, #ffffff 0%, #f0f0f0 100%);
            --shadow-glass: 0 8px 32px 0 rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Rajdhani', sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
            transition: all 0.3s ease;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(255, 0, 51, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 50%, rgba(255, 0, 51, 0.03) 0%, transparent 50%);
            pointer-events: none;
            z-index: 0;
        }

        .cyber-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(255, 0, 51, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255, 0, 51, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: 0;
            opacity: 0.5;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .glass-panel {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: var(--shadow-glass);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .glass-panel::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 0, 51, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .glass-panel:hover::before {
            left: 100%;
        }

        .glass-panel:hover {
            border-color: var(--accent-red);
            box-shadow: var(--shadow-red), var(--shadow-glass);
            transform: translateY(-2px);
        }

        .theme-toggle {
            position: fixed;
            top: 30px;
            right: 30px;
            z-index: 1000;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 50px;
            padding: 12px 24px;
            cursor: pointer;
            font-family: 'Orbitron', monospace;
            color: var(--accent-red);
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s ease;
            box-shadow: var(--shadow-glass);
        }

        .theme-toggle:hover {
            background: var(--accent-red);
            color: #fff;
            box-shadow: var(--shadow-red);
            transform: scale(1.05);
        }

        .header {
            text-align: center;
            padding: 60px 0 40px;
        }

        .banner-container {
            width: 100%;
            margin-bottom: 40px;
            border-radius: 16px;
            overflow: hidden;
            border: 2px solid var(--glass-border);
            box-shadow: var(--shadow-red);
        }

        .banner-container img {
            width: 100%;
            display: block;
        }

        .cyber-title {
            font-family: 'Orbitron', monospace;
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 900;
            background: var(--gradient-red);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-transform: uppercase;
            letter-spacing: 4px;
            margin: 30px 0;
            text-shadow: 0 0 30px var(--accent-red-glow);
            animation: glitchTitle 3s infinite;
        }

        @keyframes glitchTitle {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
        }

        .typing-svg {
            margin: 20px auto;
            max-width: 900px;
        }

        .typing-svg img {
            width: 100%;
            filter: drop-shadow(0 0 20px var(--accent-red-glow));
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .stat-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 25px;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .stat-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--gradient-red);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .stat-card:hover::after {
            transform: scaleX(1);
        }

        .stat-card:hover {
            border-color: var(--accent-red);
            transform: translateY(-5px);
            box-shadow: var(--shadow-red);
        }

        .stat-card pre {
            font-family: 'Share Tech Mono', monospace;
            color: var(--text-primary);
            font-size: 14px;
            line-height: 1.8;
            margin: 0;
            background: transparent;
            border: none;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .social-links a {
            transition: all 0.3s ease;
            filter: drop-shadow(0 0 10px var(--accent-red-glow));
        }

        .social-links a:hover {
            transform: scale(1.1) translateY(-3px);
            filter: drop-shadow(0 0 20px var(--accent-red));
        }

        .section-title {
            font-family: 'Orbitron', monospace;
            font-size: clamp(1.8rem, 4vw, 2.5rem);
            font-weight: 800;
            text-align: center;
            color: var(--accent-red);
            text-transform: uppercase;
            letter-spacing: 3px;
            margin: 60px 0 40px;
            position: relative;
            padding-bottom: 20px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: var(--gradient-red);
            box-shadow: 0 0 20px var(--accent-red-glow);
        }

        .subsection-title {
            font-family: 'Orbitron', monospace;
            font-size: clamp(1.2rem, 3vw, 1.5rem);
            font-weight: 700;
            text-align: center;
            color: var(--text-primary);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin: 40px 0 30px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .tech-item {
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 20px 10px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: radial-gradient(circle, var(--accent-red-glow) 0%, transparent 70%);
            transform: translate(-50%, -50%);
            transition: all 0.3s ease;
            border-radius: 50%;
        }

        .tech-item:hover::before {
            width: 200px;
            height: 200px;
        }

        .tech-item:hover {
            border-color: var(--accent-red);
            transform: translateY(-5px) scale(1.05);
            box-shadow: var(--shadow-red);
        }

        .tech-item img {
            width: 48px;
            height: 48px;
            margin-bottom: 10px;
            transition: all 0.3s ease;
            position: relative;
            z-index: 1;
        }

        .tech-item:hover img {
            transform: scale(1.2) rotate(5deg);
        }

        .tech-item br + text,
        .tech-item img + br + text {
            font-family: 'Rajdhani', sans-serif;
            font-size: 14px;
            font-weight: 600;
            color: var(--text-primary);
            display: block;
            margin-top: 8px;
            position: relative;
            z-index: 1;
        }

        .tech-note {
            font-family: 'Share Tech Mono', monospace;
            text-align: center;
            color: var(--text-secondary);
            margin: 20px 0;
            font-size: 14px;
            line-height: 1.8;
        }

        .tech-note strong {
            color: var(--accent-red);
            font-weight: 700;
        }

        .divider {
            margin: 60px auto;
            text-align: center;
        }

        .divider img {
            width: 100%;
            max-width: 900px;
            opacity: 0.7;
            filter: hue-rotate(330deg) saturate(2);
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        @media (max-width: 768px) {
            .project-grid {
                grid-template-columns: 1fr;
            }
        }

        .project-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 30px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: var(--gradient-red);
            border-radius: 16px;
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }

        .project-card:hover::before {
            opacity: 0.3;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-red);
        }

        .project-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--accent-red);
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .project-subtitle {
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .code-block {
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid var(--glass-border);
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
            font-family: 'Share Tech Mono', monospace;
            font-size: 13px;
            line-height: 1.8;
            overflow-x: auto;
        }

        .code-block pre {
            margin: 0;
            color: var(--text-primary);
        }

        .project-section {
            margin: 25px 0;
        }

        .project-section h4 {
            font-family: 'Orbitron', monospace;
            font-size: 1rem;
            font-weight: 600;
            color: var(--accent-red);
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .project-section ul {
            list-style: none;
            padding: 0;
        }

        .project-section li {
            padding: 8px 0 8px 25px;
            position: relative;
            color: var(--text-primary);
            font-size: 15px;
        }

        .project-section li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: var(--accent-red);
            font-weight: bold;
        }

        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .metric-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .metric-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--gradient-red);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .metric-card:hover::after {
            transform: scaleX(1);
        }

        .metric-card:hover {
            border-color: var(--accent-red);
            transform: translateY(-5px);
            box-shadow: var(--shadow-red);
        }

        .metric-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--accent-red);
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .metric-card pre {
            font-family: 'Share Tech Mono', monospace;
            font-size: 13px;
            line-height: 1.8;
            color: var(--text-primary);
            margin: 0;
        }

        .education-block {
            text-align: center;
            margin: 40px 0;
        }

        .education-block p {
            font-size: 1.2rem;
            line-height: 1.8;
            margin: 15px 0;
        }

        .education-block strong {
            color: var(--accent-red);
            font-family: 'Orbitron', monospace;
            font-weight: 700;
        }

        .focus-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        @media (max-width: 768px) {
            .focus-grid {
                grid-template-columns: 1fr;
            }
        }

        .philosophy-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .philosophy-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .philosophy-card:hover {
            border-color: var(--accent-red);
            transform: translateY(-5px);
            box-shadow: var(--shadow-red);
        }

        .philosophy-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--accent-red);
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        .philosophy-card p {
            font-size: 1rem;
            line-height: 1.8;
            color: var(--text-primary);
            margin: 10px 0;
        }

        .quote-block {
            text-align: center;
            margin: 60px 0;
            padding: 40px;
        }

        .quote-block blockquote {
            font-family: 'Orbitron', monospace;
            font-size: 1.3rem;
            font-style: italic;
            color: var(--text-primary);
            margin: 20px 0;
            position: relative;
        }

        .quote-block blockquote::before {
            content: '"';
            font-size: 4rem;
            color: var(--accent-red);
            position: absolute;
            left: -40px;
            top: -20px;
            opacity: 0.3;
        }

        .quote-author {
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--accent-red);
            margin-top: 20px;
        }

        .profile-views {
            text-align: center;
            margin: 30px 0;
        }

        .profile-views img {
            filter: drop-shadow(0 0 10px var(--accent-red-glow));
        }

        .footer-wave {
            width: 100%;
            margin-top: 60px;
            opacity: 0.8;
        }

        @media (max-width: 768px) {
            .theme-toggle {
                top: 20px;
                right: 20px;
                padding: 10px 20px;
                font-size: 12px;
            }

            .cyber-title {
                letter-spacing: 2px;
            }

            .section-title {
                letter-spacing: 2px;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }

            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
                gap: 15px;
            }

            .glass-panel {
                padding: 20px;
            }

            .focus-grid,
            .philosophy-grid {
                grid-template-columns: 1fr;
            }
        }

        .scan-line {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--accent-red), transparent);
            animation: scan 4s linear infinite;
            pointer-events: none;
            z-index: 9999;
            opacity: 0.3;
        }

        @keyframes scan {
            0% { transform: translateY(0); }
            100% { transform: translateY(100vh); }
        }

        .glitch {
            animation: glitch 1s infinite;
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            25% { transform: translate(-2px, 2px); }
            50% { transform: translate(2px, -2px); }
            75% { transform: translate(-2px, -2px); }
        }

        .pulse-glow {
            animation: pulseGlow 2s ease-in-out infinite;
        }

        @keyframes pulseGlow {
            0%, 100% { box-shadow: 0 0 20px var(--accent-red-glow); }
            50% { box-shadow: 0 0 40px var(--accent-red); }
        }
    </style>
</head>
<body data-theme="dark">
    <div class="scan-line"></div>
    <div class="cyber-grid"></div>
    
    <button class="theme-toggle" onclick="toggleTheme()">
        <span id="theme-text">LIGHT MODE</span>
    </button>

    <div class="container">
        <div class="header">
            <div class="banner-container">
                <img src="assets/banner.png" alt="Header">
            </div>

            <div class="typing-svg">
                <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=800&color=FF0033&background=FFFFFF00&center=true&vCenter=true&multiline=true&repeat=true&random=false&width=900&height=120&lines=Production-Grade+Computer+Vision+Systems;Face+Recognition+%E2%86%92+250%2C000%2B+Identities+%7C+%3C50ms+Latency;YOLO+Detection+%7C+TensorRT+Optimization+%7C+CUDA+Acceleration;Edge+AI+%7C+Jetson+Orin+NX+%7C+Multi-GPU+Infrastructure;High-Performance+APIs+%7C+100%2B+Requests%2FSec+%7C+Distributed+Systems" alt="Typing SVG" />
            </div>

            <div class="stats-grid">
                <div class="stat-card">
                    <pre>ROLE: Applied AI Engineer
FOCUS: Computer Vision
EXPERIENCE: 3+ Years
LOCATION: Colombo, Sri Lanka</pre>
                </div>
                <div class="stat-card">
                    <pre>SPECIALIZATION: Face Recognition
SCALE: 250,000+ Identities
LATENCY: <50ms Real-Time
ACCURACY: 99.7% Recognition</pre>
                </div>
                <div class="stat-card">
                    <pre>DEPLOYMENT: Production-Grade
GPU: TensorRT Optimized
EDGE: Jetson Orin NX
UPTIME: 99.9% Availability</pre>
                </div>
                <div class="stat-card">
                    <pre>API: 100+ Requests/Sec
DATABASES: PostgreSQL, Redis
FRAMEWORK: Flask, FastAPI
MODE: 24/7 Operations</pre>
                </div>
            </div>

            <div class="social-links">
                <a href="https://linkedin.com/in/anasakram">
                    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
                </a>
                <a href="https://github.com/anasakram">
                    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
                </a>
                <a href="https://anasakram.com">
                    <img src="https://img.shields.io/badge/Portfolio-FF0033?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Portfolio"/>
                </a>
                <a href="mailto:anasakram1245@gmail.com">
                    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
                </a>
            </div>

            <div class="divider">
                <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
            </div>
        </div>

        <h2 class="section-title">TECHNICAL STACK</h2>

        <div class="glass-panel">
            <h3 class="subsection-title">ARTIFICIAL INTELLIGENCE & DEEP LEARNING</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=pytorch" alt="PyTorch">
                    <br>PyTorch
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=tensorflow" alt="TensorFlow">
                    <br>TensorFlow
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" alt="OpenCV">
                    <br>OpenCV
                </div>
                <div class="tech-item">
                    <img src="https://github.com/ultralytics/assets/raw/main/logo/Ultralytics_Logotype_Original.svg" alt="Ultralytics">
                    <br>Ultralytics
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" alt="NumPy">
                    <br>NumPy
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg" alt="Pandas">
                    <br>Pandas
                </div>
                <div class="tech-item">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" alt="Scikit-learn">
                    <br>Scikit-learn
                </div>
            </div>
            <p class="tech-note"><strong>Advanced:</strong> TensorRT • ONNX • YOLO (v5/v8/v11) • InsightFace • Stable Diffusion • Hugging Face Transformers</p>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">HARDWARE & EDGE AI PLATFORMS</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nvidia/nvidia-original.svg" alt="NVIDIA">
                    <br>Jetson Orin
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/raspberrypi/raspberrypi-original.svg" alt="Raspberry Pi">
                    <br>Raspberry Pi
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nvidia/nvidia-original.svg" alt="CUDA">
                    <br>CUDA
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/nvidia/nvidia-icon.svg" alt="TensorRT">
                    <br>TensorRT
                </div>
            </div>
            <p class="tech-note"><strong>Platforms:</strong> NVIDIA Jetson Orin NX • Raspberry Pi 5 • CUDA Servers • L4T/JetPack • Multi-GPU Infrastructure</p>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">BACKEND & API DEVELOPMENT</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=fastapi" alt="FastAPI">
                    <br>FastAPI
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=flask" alt="Flask">
                    <br>Flask
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=redis" alt="Redis">
                    <br>Redis
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=postgres" alt="PostgreSQL">
                    <br>PostgreSQL
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=mysql" alt="MySQL">
                    <br>MySQL
                </div>
                <div class="tech-item">
                    <img src="https://cdn.worldvectorlogo.com/logos/clickhouse.svg" alt="ClickHouse">
                    <br>ClickHouse
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/socketio/socketio-original.svg" alt="WebSocket">
                    <br>WebSocket
                </div>
            </div>
            <p class="tech-note"><strong>Architecture:</strong> RESTful APIs • WebSocket Real-Time • Redis Pub/Sub • Database Optimization • Distributed Systems</p>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">FRONTEND & WEB DEVELOPMENT</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=react" alt="React">
                    <br>React
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=ts" alt="TypeScript">
                    <br>TypeScript
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=js" alt="JavaScript">
                    <br>JavaScript
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=html" alt="HTML5">
                    <br>HTML5
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=css" alt="CSS3">
                    <br>CSS3
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=bootstrap" alt="Bootstrap">
                    <br>Bootstrap
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=tailwind" alt="Tailwind">
                    <br>Tailwind
                </div>
            </div>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">DEVOPS & INFRASTRUCTURE</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=docker" alt="Docker">
                    <br>Docker
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=linux" alt="Linux">
                    <br>Linux
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=ubuntu" alt="Ubuntu">
                    <br>Ubuntu
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=bash" alt="Bash">
                    <br>Bash
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=git" alt="Git">
                    <br>Git
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=github" alt="GitHub">
                    <br>GitHub
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=vscode" alt="VSCode">
                    <br>VSCode
                </div>
            </div>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">AI AUTOMATION & INTEGRATION</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://avatars.githubusercontent.com/u/45487711?s=200&v=4" alt="n8n">
                    <br>n8n
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/openai/openai-original.svg" alt="OpenAI" style="filter: invert(1);">
                    <br>OpenAI API
                </div>
                <div class="tech-item">
                    <img src="https://static-00.iconduck.com/assets.00/hugging-face-icon-512x512-v2b00jz7.png" alt="Hugging Face">
                    <br>Hugging Face
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/twilio/twilio-icon.svg" alt="Twilio">
                    <br>Twilio
                </div>
            </div>
            <p class="tech-note"><strong>Tools:</strong> Deepgram (STT) • ElevenLabs (TTS) • LangChain • Vector Databases</p>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">PROGRAMMING LANGUAGES</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=python" alt="Python">
                    <br>Python
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=typescript" alt="TypeScript">
                    <br>TypeScript
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=javascript" alt="JavaScript">
                    <br>JavaScript
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++">
                    <br>C++
                </div>
                <div class="tech-item">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="SQL">
                    <br>SQL
                </div>
                <div class="tech-item">
                    <img src="https://skillicons.dev/icons?i=bash" alt="Bash">
                    <br>Bash
                </div>
            </div>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">FEATURED PROJECTS</h2>

        <div class="project-grid">
            <div class="project-card">
                <h3 class="project-title">Enterprise Face Recognition System</h3>
                <p class="project-subtitle">Large-Scale Biometric Authentication</p>
                
                <div class="code-block">
                    <pre>Scale: 250,000+ Identities
Latency: <50ms Real-Time
Recognition: 99.7% Accuracy
Performance: 30+ FPS Live
Infrastructure: Multi-GPU Production</pre>
                </div>

                <div class="project-section">
                    <h4>Core Technologies</h4>
                    <ul>
                        <li>InsightFace Recognition Engine</li>
                        <li>Redis In-Memory Caching</li>
                        <li>PostgreSQL Database</li>
                        <li>FastAPI Production APIs</li>
                        <li>TensorRT GPU Optimization</li>
                        <li>Multi-GPU Distribution</li>
                    </ul>
                </div>

                <div class="project-section">
                    <h4>System Architecture</h4>
                    <ul>
                        <li>Sub-50ms end-to-end latency</li>
                        <li>Distributed GPU infrastructure</li>
                        <li>Real-time face detection</li>
                        <li>Advanced anti-spoofing</li>
                        <li>99.9% system uptime</li>
                    </ul>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">Casino Vision Analytics System</h3>
                <p class="project-subtitle">Multi-Table Computer Vision Monitoring</p>
                
                <div class="code-block">
                    <pre>Deployment: Jetson Orin NX
Tables: 8+ Concurrent
FPS: 30+ Real-Time
Detection: YOLO v8/v11
Optimization: TensorRT 5x Speedup</pre>
                </div>

                <div class="project-section">
                    <h4>Technical Stack</h4>
                    <ul>
                        <li>YOLO Object Detection</li>
                        <li>TensorRT Model Optimization</li>
                        <li>NVIDIA Jetson Orin NX</li>
                        <li>Multi-Stream Processing</li>
                        <li>Real-Time Analytics</li>
                        <li>Edge AI Deployment</li>
                    </ul>
                </div>

                <div class="project-section">
                    <h4>Key Features</h4>
                    <ul>
                        <li>8+ concurrent table monitoring</li>
                        <li>Real-time chip detection</li>
                        <li>Card recognition accuracy</li>
                        <li>Player tracking system</li>
                        <li>30+ FPS performance</li>
                    </ul>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">Production YOLO Inference API</h3>
                <p class="project-subtitle">High-Performance Object Detection Service</p>
                
                <div class="code-block">
                    <pre>Model: YOLO v8 Custom
Throughput: 100+ Requests/Sec
Latency: <50ms Average
GPU: TensorRT Optimized
Deployment: 24/7 Production</pre>
                </div>

                <div class="project-section">
                    <h4>Implementation</h4>
                    <ul>
                        <li>Custom YOLO Training Pipeline</li>
                        <li>TensorRT GPU Acceleration</li>
                        <li>FastAPI Framework</li>
                        <li>Redis Request Caching</li>
                        <li>Auto-scaling Infrastructure</li>
                        <li>Prometheus Monitoring</li>
                    </ul>
                </div>

                <div class="project-section">
                    <h4>Production Features</h4>
                    <ul>
                        <li>High-throughput API serving</li>
                        <li>Batch processing support</li>
                        <li>Real-time model updates</li>
                        <li>Comprehensive logging</li>
                        <li>99.9% uptime guarantee</li>
                    </ul>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">Stable Diffusion Fine-Tuning</h3>
                <p class="project-subtitle">Custom Generative AI Models</p>
                
                <div class="code-block">
                    <pre>Framework: Diffusers Library
Models: SD 1.5 / SDXL
Training: LoRA Fine-Tuning
Techniques: DreamBooth, ControlNet
Inference: 8-bit Quantization</pre>
                </div>

                <div class="project-section">
                    <h4>Technical Implementation</h4>
                    <ul>
                        <li>Hugging Face Transformers</li>
                        <li>PyTorch Training Pipeline</li>
                        <li>Dataset Preparation</li>
                        <li>Model Quantization (8-bit)</li>
                        <li>FastAPI Deployment</li>
                        <li>Redis Caching</li>
                    </ul>
                </div>

                <div class="project-section">
                    <h4>Production Features</h4>
                    <ul>
                        <li>Domain-specific tuning</li>
                        <li>Cloud API deployment</li>
                        <li>REST integration</li>
                        <li>Performance monitoring</li>
                    </ul>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">Facebook Message Automation</h3>
                <p class="project-subtitle">n8n + OpenAI Integration</p>
                
                <div class="code-block">
                    <pre>Platform: n8n Automation
AI: OpenAI GPT-4 API
Server: Custom Ubuntu
Uptime: 24/7 Operation
Efficiency: 90% Reduction</pre>
                </div>

                <div class="project-section">
                    <h4>Technical Implementation</h4>
                    <ul>
                        <li>n8n Workflow Engine</li>
                        <li>OpenAI GPT-4 API</li>
                        <li>Facebook Graph API</li>
                        <li>Custom Ubuntu Server</li>
                        <li>Redis Message Queue</li>
                        <li>MySQL Database</li>
                    </ul>
                </div>

                <div class="project-section">
                    <h4>System Performance</h4>
                    <ul>
                        <li>24/7 autonomous operation</li>
                        <li><2s response time</li>
                        <li>90% manual work reduction</li>
                        <li>99.8% uptime</li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">PERFORMANCE METRICS</h2>

        <div class="metrics-grid">
            <div class="metric-card pulse-glow">
                <div class="metric-title">FACE RECOGNITION</div>
                <pre>Identities: 250,000+
Latency: <50ms
Accuracy: 99.7%
FPS: 30+
Uptime: 99.9%</pre>
            </div>

            <div class="metric-card pulse-glow">
                <div class="metric-title">API PERFORMANCE</div>
                <pre>Requests/Sec: 100+
Avg Response: 45ms
Concurrent: 200+
WebSocket: Real-Time
Availability: 24/7</pre>
            </div>

            <div class="metric-card pulse-glow">
                <div class="metric-title">EDGE DEPLOYMENT</div>
                <pre>Platform: Jetson Orin
GPU: TensorRT
Speedup: 5x
Power: 15W-60W
Latency: <30ms</pre>
            </div>

            <div class="metric-card pulse-glow">
                <div class="metric-title">VISION SYSTEMS</div>
                <pre>Tables: 8+ Concurrent
FPS: 30+
Accuracy: 98.5%
Detection: YOLO
Mode: Real-Time</pre>
            </div>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">EDUCATION</h2>

        <div class="glass-panel education-block">
            <p><strong>BSc (Hons) Computer Science with Artificial Intelligence</strong></p>
            <p>Coventry University, United Kingdom | Completed 2025</p>
            <p><strong>First-Class Honours (80%)</strong></p>
            <br>
            <p>Key Modules: Machine Learning (83%) • Artificial Neural Networks (75.5%) • Intelligent Agents (79%)</p>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">TECHNICAL FOCUS AREAS</h2>

        <div class="focus-grid">
            <div class="glass-panel">
                <h3 class="project-title">PRIMARY RESEARCH</h3>
                <div class="code-block">
                    <pre>focus_areas = {
    "Computer Vision": [
        "Large-Scale Face Recognition",
        "Real-Time Object Detection",
        "Instance Segmentation",
        "Video Analytics",
        "Multi-Camera Fusion"
    ],
    
    "Edge AI": [
        "NVIDIA Jetson Optimization",
        "Model Quantization",
        "Hardware-Accelerated Inference",
        "Power-Efficient AI",
        "Embedded Vision Systems"
    ],
    
    "AI Optimization": [
        "TensorRT GPU Acceleration",
        "ONNX Model Conversion",
        "Multi-GPU Distribution",
        "CUDA Kernel Optimization",
        "Low-Latency Inference"
    ]
}</pre>
                </div>
            </div>

            <div class="glass-panel">
                <h3 class="project-title">EMERGING TECHNOLOGIES</h3>
                <div class="code-block">
                    <pre>exploring = {
    "Generative AI": [
        "Stable Diffusion Fine-Tuning",
        "ControlNet & IP-Adapter",
        "Text-to-Image Generation",
        "Face-Guided Synthesis",
        "Custom Model Training"
    ],
    
    "LLM Integration": [
        "GPT-4 API Integration",
        "Custom LLM Fine-Tuning",
        "RAG Architectures",
        "Voice AI (STT/TTS)",
        "Conversational Systems"
    ],
    
    "Production AI": [
        "System Architecture",
        "High-Throughput APIs",
        "Distributed Computing",
        "MLOps & Deployment",
        "Performance Optimization"
    ]
}</pre>
                </div>
            </div>
        </div>

        <div class="glass-panel">
            <h3 class="subsection-title">TECHNICAL PHILOSOPHY</h3>
            <div class="philosophy-grid">
                <div class="philosophy-card">
                    <div class="philosophy-title">PERFORMANCE</div>
                    <p>Low-latency inference</p>
                    <p>High-throughput APIs</p>
                    <p>GPU acceleration</p>
                    <p>Edge optimization</p>
                </div>

                <div class="philosophy-card">
                    <div class="philosophy-title">SCALABILITY</div>
                    <p>Distributed computing</p>
                    <p>Microservices design</p>
                    <p>Database optimization</p>
                    <p>System resilience</p>
                </div>

                <div class="philosophy-card">
                    <div class="philosophy-title">PRODUCTION</div>
                    <p>Operational reliability</p>
                    <p>System monitoring</p>
                    <p>Continuous improvement</p>
                    <p>24/7 availability</p>
                </div>
            </div>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">PROFESSIONAL OPPORTUNITIES</h2>

        <div class="glass-panel">
            <div class="code-block">
                <pre>Open For:
  - Full-Time Positions: Senior AI Engineer / Computer Vision Engineer
  - Consulting Projects: AI System Architecture & Implementation
  - Research Collaboration: Computer Vision & Edge AI
  - Technical Leadership: AI Engineering & Production Deployment

Expertise:
  - Computer Vision Systems (Face Recognition, Object Detection)
  - Edge AI Deployment (NVIDIA Jetson, TensorRT Optimization)
  - Production AI Architecture (High-Performance APIs, Distributed Systems)
  - AI Automation & Integration (LLM Deployment, Voice AI)

Location:
  - Remote (Global)
  - On-Site (Colombo, Sri Lanka)
  - Hybrid Opportunities</pre>
            </div>
        </div>

        <div class="divider">
            <img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif">
        </div>

        <h2 class="section-title">CONTACT</h2>

        <div class="social-links">
            <a href="https://linkedin.com/in/anasakram">
                <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
            </a>
            <a href="https://github.com/anasakram">
                <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
            </a>
            <a href="https://anasakram.com">
                <img src="https://img.shields.io/badge/Portfolio-FF0033?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Portfolio"/>
            </a>
            <a href="mailto:anasakram1245@gmail.com">
                <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
            </a>
        </div>

        <div class="quote-block glass-panel">
            <blockquote>Architecting production-grade AI systems that operate at scale with millisecond precision</blockquote>
            <p class="quote-author">— Anas Akram, Applied AI Engineer</p>
        </div>

        <div class="profile-views">
            <img src="https://komarev.com/ghpvc/?username=anasakram&color=FF0033&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile Views"/>
        </div>

        <div class="footer-wave">
            <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,3,4,6&height=120&section=footer" width="100%"/>
        </div>
    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const themeText = document.getElementById('theme-text');
            const currentTheme = body.getAttribute('data-theme');
            
            if (currentTheme === 'dark') {
                body.setAttribute('data-theme', 'light');
                themeText.textContent = 'DARK MODE';
            } else {
                body.setAttribute('data-theme', 'dark');
                themeText.textContent = 'LIGHT MODE';
            }
        }

        // Add smooth scroll behavior
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add intersection observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all glass panels
        document.querySelectorAll('.glass-panel, .stat-card, .tech-item, .project-card, .metric-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });

        // Add parallax effect to background
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const grid = document.querySelector('.cyber-grid');
            if (grid) {
                grid.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>