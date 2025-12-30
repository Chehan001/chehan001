<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chehan Lasindu - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
            color: #e0e0e0;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Header */
        .header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, #134e4a 0%, #065f46 50%, #047857 100%);
            border-radius: 20px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(16, 185, 129, 0.3);
            animation: slideDown 1s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(16, 185, 129, 0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .header h1 {
            font-size: 3.5rem;
            color: #10b981;
            text-shadow: 0 0 20px rgba(16, 185, 129, 0.5);
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
            animation: glow 2s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { text-shadow: 0 0 20px rgba(16, 185, 129, 0.5); }
            50% { text-shadow: 0 0 30px rgba(16, 185, 129, 0.8), 0 0 40px rgba(16, 185, 129, 0.6); }
        }

        .header .subtitle {
            font-size: 1.5rem;
            color: #6ee7b7;
            position: relative;
            z-index: 1;
        }

        /* Typing Animation */
        .typing-container {
            text-align: center;
            margin: 30px 0;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .typing-text {
            font-size: 1.8rem;
            font-weight: 600;
            color: #10b981;
            border-right: 3px solid #10b981;
            padding-right: 5px;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: #10b981; }
            51%, 100% { border-color: transparent; }
        }

        /* About Section */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 380px;
            gap: 40px;
            margin-bottom: 50px;
            animation: fadeIn 1s ease-out 0.3s both;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .about-content {
            background: rgba(31, 41, 55, 0.8);
            padding: 40px;
            border-radius: 15px;
            border: 1px solid rgba(16, 185, 129, 0.3);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .about-content:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(16, 185, 129, 0.4);
            border-color: rgba(16, 185, 129, 0.6);
        }

        .about-image {
            text-align: center;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .about-image img {
            max-width: 100%;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(16, 185, 129, 0.3);
        }

        h2 {
            font-size: 2rem;
            color: #10b981;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, #10b981, #34d399);
            animation: expand 1s ease-out 0.5s forwards;
        }

        @keyframes expand {
            to { width: 100%; }
        }

        h3 {
            color: #6ee7b7;
            margin: 25px 0 15px;
            font-size: 1.4rem;
        }

        /* Skills Cards */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .skill-card {
            background: rgba(31, 41, 55, 0.8);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(16, 185, 129, 0.3);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            animation: fadeIn 1s ease-out;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(16, 185, 129, 0.2), transparent);
            transition: left 0.6s ease;
        }

        .skill-card:hover::before {
            left: 100%;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 15px 50px rgba(16, 185, 129, 0.5);
            border-color: rgba(16, 185, 129, 0.8);
        }

        .skill-card h3 {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 0;
        }

        .skill-icon {
            font-size: 1.8rem;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        ul {
            list-style: none;
            margin: 15px 0;
        }

        li {
            padding: 10px 0;
            padding-left: 25px;
            position: relative;
            transition: all 0.3s ease;
        }

        li:hover {
            padding-left: 35px;
            color: #6ee7b7;
        }

        li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: #10b981;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }

        li:hover::before {
            transform: translateX(5px);
        }

        /* Code Block */
        .code-block {
            background: #1a1a2e;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            border-left: 4px solid #10b981;
            font-family: 'Courier New', monospace;
            color: #6ee7b7;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.5);
            overflow-x: auto;
            animation: slideIn 0.8s ease-out;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px;
            margin-top: 60px;
            background: rgba(31, 41, 55, 0.8);
            border-radius: 15px;
            border: 1px solid rgba(16, 185, 129, 0.3);
            animation: fadeIn 1s ease-out 0.6s both;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .social-btn {
            padding: 12px 30px;
            background: linear-gradient(135deg, #065f46, #047857);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
        }

        .social-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 25px rgba(16, 185, 129, 0.5);
            background: linear-gradient(135deg, #047857, #10b981);
        }

        /* Particles Effect */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            background: rgba(16, 185, 129, 0.3);
            border-radius: 50%;
            animation: rise 15s infinite ease-in;
        }

        @keyframes rise {
            0% {
                bottom: -10%;
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                bottom: 110%;
                opacity: 0;
            }
        }

        @media (max-width: 768px) {
            .about-section {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 2.5rem;
            }
            
            .typing-text {
                font-size: 1.3rem;
            }
        }
    </style>
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>Chehan Lasindu</h1>
            <p class="subtitle">Software Engineer | Data Scientist</p>
        </div>

        <!-- Typing Animation -->
        <div class="typing-container">
            <div class="typing-text" id="typingText"></div>
        </div>

        <!-- About Section -->
        <div class="about-section">
            <div class="about-content">
                <h2>👨‍💻 About Me</h2>
                
                <h3>🎓 Background</h3>
                <p>I'm an undergraduate at <strong>Sabar aguwa University of Sri Lanka</strong>, pursuing a <strong>BSc (Hons) in Computer Science & Technology</strong>.</p>
                <p style="margin-top: 15px;">🌱 Passionate about transforming data into actionable insights and building innovative solutions that make a difference.</p>
                <p style="margin-top: 10px;">🎯 Always learning, always growing, always coding!</p>
            </div>
            
            <div class="about-image">
                <img src="https://user-images.githubusercontent.com/74038190/235224431-e8c8c12e-6826-47f1-89fb-2ddad83b3abf.gif" alt="Coding Animation">
            </div>
        </div>

        <!-- Skills Section -->
        <h2 style="text-align: center; font-size: 2.5rem; margin: 60px 0 40px;">💡 Expertise</h2>
        
        <div class="skills-grid">
            <!-- Data Science Card -->
            <div class="skill-card">
                <h3><span class="skill-icon">🔬</span> Data Science & Analytics</h3>
                <div class="code-block">
skills = {<br>
&nbsp;&nbsp;"ML": ["Scikit-learn", "TensorFlow"],<br>
&nbsp;&nbsp;"Analysis": ["Pandas", "NumPy"],<br>
&nbsp;&nbsp;"Viz": ["Matplotlib", "Seaborn"],<br>
&nbsp;&nbsp;"Tools": ["Jupyter", "Streamlit"]<br>
}
                </div>
                <ul>
                    <li>Machine Learning & Model Training</li>
                    <li>Statistical Analysis & Data Mining</li>
                    <li>Interactive Visualizations</li>
                </ul>
            </div>

            <!-- Full-Stack Card -->
            <div class="skill-card">
                <h3><span class="skill-icon">💻</span> Full-Stack Development</h3>
                <p><strong>Frontend Magic ✨</strong></p>
                <ul>
                    <li>ReactJS & React Native</li>
                    <li>Modern UI/UX Design</li>
                    <li>Responsive Applications</li>
                </ul>
                <p style="margin-top: 20px;"><strong>Backend Power 🚀</strong></p>
                <ul>
                    <li>NodeJS | ExpressJS</li>
                    <li>Java | JavaFX | C | C#</li>
                    <li>Database Management</li>
                    <li>ElectronJS Applications</li>
                </ul>
            </div>

            <!-- Creative Design Card -->
            <div class="skill-card">
                <h3><span class="skill-icon">🎨</span> Creative Design</h3>
                <ul>
                    <li>UI/UX Design & Prototyping</li>
                    <li>Video Editing (Part-time)</li>
                    <li>Graphic Design & Branding</li>
                    <li>Motion Graphics</li>
                </ul>
                <p style="margin-top: 20px; color: #6ee7b7; font-style: italic;">Combining technical skills with creative vision to deliver exceptional user experiences.</p>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <h2>💚 Let's Connect and Build Something Amazing!</h2>
            <div class="social-links">
                <a href="#" class="social-btn">GitHub</a>
                <a href="#" class="social-btn">LinkedIn</a>
                <a href="#" class="social-btn">Portfolio</a>
            </div>
        </div>
    </div>

    <script>
        // Typing Animation
        const phrases = [
            "Full-Stack Developer 🚀",
            "Data Scientist 📊",
            "Creative Designer 🎨",
            "Problem Solver 💡"
        ];
        
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingText = document.getElementById('typingText');
        
        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingText.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingText.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }
            
            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }
            
            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }
        
        type();
        
        // Create Particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.width = particle.style.height = Math.random() * 10 + 5 + 'px';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = Math.random() * 10 + 10 + 's';
            particlesContainer.appendChild(particle);
        }
    </script>
</body>
</html>
