<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hidden Leaf Village - Shinobi Academy</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #FF6B35 0%, #F7931E 25%, #FFD700 50%, #FF4500 75%, #FF6B35 100%);
            background-size: 400% 400%;
            animation: gradientShift 10s ease infinite;
            min-height: 100vh;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="25" cy="25" r="2" fill="rgba(255,255,255,0.1)"/><circle cx="75" cy="75" r="1.5" fill="rgba(255,255,255,0.1)"/><circle cx="50" cy="10" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="10" cy="60" r="1.5" fill="rgba(255,255,255,0.1)"/><circle cx="90" cy="30" r="1" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: 200px 200px;
            animation: twinkle 3s ease-in-out infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.8; }
        }

        /* Header */
        header {
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 3px solid #FF6B35;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #FF6B35;
            text-decoration: none;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            position: relative;
        }

        .logo::before {
            content: '🍥';
            margin-right: 0.5rem;
            font-size: 1.5rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #FFD700;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            position: relative;
        }

        .nav-links a:hover {
            background: linear-gradient(45deg, #FF6B35, #F7931E);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.5);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="rgba(0,0,0,0.3)" points="0,0 1000,300 1000,1000 0,700"/></svg>');
            animation: float 8s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(2deg); }
        }

        .hero-content {
            max-width: 800px;
            z-index: 2;
            position: relative;
            animation: fadeInUp 1.5s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(100px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #FFD700, #FF6B35, #FFD700);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 3s ease-in-out infinite;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
        }

        @keyframes shimmer {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            opacity: 0.95;
        }

        .jutsu-button {
            display: inline-block;
            background: linear-gradient(45deg, #FF6B35, #F7931E, #FF4500);
            color: white;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.4);
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            position: relative;
            overflow: hidden;
        }

        .jutsu-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .jutsu-button:hover::before {
            left: 100%;
        }

        .jutsu-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.6);
        }

        /* Sections */
        .section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .village-info {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 20px;
            margin: 2rem;
            backdrop-filter: blur(10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border: 2px solid #FF6B35;
            position: relative;
            overflow: hidden;
        }

        .village-info::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            animation: scan 4s linear infinite;
        }

        @keyframes scan {
            0% { transform: translateX(-100%) translateY(-100%); }
            100% { transform: translateX(100%) translateY(100%); }
        }

        .village-info h2 {
            font-size: 3rem;
            margin-bottom: 2rem;
            text-align: center;
            background: linear-gradient(45deg, #FFD700, #FF6B35);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.3);
            position: relative;
            z-index: 2;
        }

        .village-info p {
            color: #FFD700;
            font-size: 1.1rem;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
            z-index: 2;
        }

        .jutsu-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .jutsu-card {
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.9), rgba(255, 107, 53, 0.1));
            padding: 2rem;
            border-radius: 15px;
            border: 2px solid #FF6B35;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.3);
            transition: all 0.3s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .jutsu-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 215, 0, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .jutsu-card:hover::before {
            transform: translateX(100%);
        }

        .jutsu-card:hover {
            transform: translateY(-15px) scale(1.05);
            box-shadow: 0 25px 50px rgba(255, 107, 53, 0.5);
            border-color: #FFD700;
        }

        .jutsu-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, #FF6B35, #FFD700);
            border-radius: 50%;
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            position: relative;
            z-index: 2;
            box-shadow: 0 0 20px rgba(255, 107, 53, 0.5);
        }

        .jutsu-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #FFD700;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            position: relative;
            z-index: 2;
        }

        .jutsu-card p {
            color: #FFF;
            line-height: 1.8;
            position: relative;
            z-index: 2;
        }

        /* Mission Section */
        .mission {
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin: 2rem;
            color: white;
            text-align: center;
            border: 2px solid #FFD700;
            position: relative;
            overflow: hidden;
        }

        .mission::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 50% 50%, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        .mission h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: #FFD700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            position: relative;
            z-index: 2;
        }

        .mission-form {
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #FF6B35;
            border-radius: 10px;
            background: rgba(0, 0, 0, 0.7);
            color: #FFD700;
            backdrop-filter: blur(5px);
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #FFD700;
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(255, 215, 0, 0.7);
        }

        .mission-btn {
            background: linear-gradient(45deg, #FF6B35, #F7931E);
            color: white;
            padding: 1.2rem 2.5rem;
            border: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.4);
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            position: relative;
            overflow: hidden;
        }

        .mission-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .mission-btn:hover::before {
            left: 100%;
        }

        .mission-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.6);
        }

        /* Footer */
        footer {
            background: rgba(0, 0, 0, 0.9);
            color: #FFD700;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            border-top: 3px solid #FF6B35;
            position: relative;
            z-index: 2;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .section {
                padding: 3rem 1rem;
            }

            .jutsu-cards {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease-out forwards;
        }

        .fade-in:nth-child(1) { animation-delay: 0.2s; }
        .fade-in:nth-child(2) { animation-delay: 0.4s; }
        .fade-in:nth-child(3) { animation-delay: 0.6s; }

        /* Ninja stars animation */
        .ninja-star {
            position: absolute;
            width: 20px;
            height: 20px;
            background: #FFD700;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
            animation: spin 3s linear infinite;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .ninja-star:nth-child(1) {
            top: 10%;
            left: 10%;
            animation-delay: 0s;
        }

        .ninja-star:nth-child(2) {
            top: 20%;
            right: 15%;
            animation-delay: 1s;
        }

        .ninja-star:nth-child(3) {
            bottom: 30%;
            left: 5%;
            animation-delay: 2s;
        }
    </style>
</head>
<body>
    <!-- Animated ninja stars -->
    <div class="ninja-star"></div>
    <div class="ninja-star"></div>
    <div class="ninja-star"></div>

    <!-- Header -->
    <header>
        <nav>
            <a href="#" class="logo">Hidden Leaf Village</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#village">Village</a></li>
                <li><a href="#jutsu">Jutsu</a></li>
                <li><a href="#mission">Mission</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Welcome to the Hidden Leaf Village</h1>
            <p>Become the strongest ninja and protect the village with your powerful jutsu techniques. Train hard, believe in yourself, and never give up on your ninja way!</p>
            <a href="https://in.pinterest.com/pin/775182154652596312/" class="jutsu-button" target="_blank">Start Your Ninja Journey</a>
        </div>
    </section>

    <!-- Village Info Section -->
    <section class="village-info section" id="village">
        <h2>About the Hidden Leaf Village</h2>
        <p>
            The Hidden Leaf Village is home to the strongest ninjas in the world. Here, young shinobi train under the guidance of legendary masters to unlock their true potential and protect their precious bonds.
        </p>
        
        <div class="jutsu-cards">
            <div class="jutsu-card fade-in">
                <div class="jutsu-icon">🔥</div>
                <h3>Fire Style Jutsu</h3>
                <p>Master the power of flames and unleash devastating fire techniques that can turn the tide of any battle.</p>
            </div>
            <div class="jutsu-card fade-in">
                <div class="jutsu-icon">⚡</div>
                <h3>Lightning Style</h3>
                <p>Harness the speed and power of lightning to strike with incredible precision and overwhelming force.</p>
            </div>
            <div class="jutsu-card fade-in">
                <div class="jutsu-icon">🌪️</div>
                <h3>Wind Style</h3>
                <p>Control the wind itself to create powerful gusts and razor-sharp attacks that cut through anything.</p>
            </div>
        </div>
    </section>

    <!-- Mission Section -->
    <section class="mission section" id="mission">
        <h2>Accept Your Mission</h2>
        <p style="margin-bottom: 2rem; font-size: 1.1rem; position: relative; z-index: 2;">Ready to prove yourself as a true ninja? Submit your mission request below!</p>
        
        <form class="mission-form" id="missionForm">
            <div class="form-group">
                <label for="ninjaName">Ninja Name</label>
                <input type="text" id="ninjaName" name="ninjaName" placeholder="Enter your ninja name" required>
            </div>
            <div class="form-group">
                <label for="village">Village</label>
                <input type="text" id="village" name="village" placeholder="Hidden Leaf Village" required>
            </div>
            <div class="form-group">
                <label for="mission">Mission Details</label>
                <textarea id="mission" name="mission" rows="5" placeholder="Describe your mission objective..." required></textarea>
            </div>
            <button type="submit" class="mission-btn">Accept Mission</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Hidden Leaf Village Shinobi Academy. All rights reserved. | Believe it! 🍥</p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
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

        // Mission form submission handler
        document.getElementById('missionForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = new FormData(this);
            const ninjaName = formData.get('ninjaName');
            const village = formData.get('village');
            const mission = formData.get('mission');
            
            const submitBtn = this.querySelector('.mission-btn');
            const originalText = submitBtn.textContent;
            
            submitBtn.textContent = 'Accepting Mission...';
            submitBtn.disabled = true;
            
            setTimeout(() => {
                alert(`Mission accepted, ${ninjaName} from ${village}! Your dedication to the ninja way is admirable. Good luck on your mission!`);
                this.reset();
                submitBtn.textContent = originalText;
                submitBtn.disabled = false;
            }, 2000);
        });

        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(0, 0, 0, 0.95)';
                header.style.boxShadow = '0 5px 20px rgba(255, 107, 53, 0.5)';
            } else {
                header.style.background = 'rgba(0, 0, 0, 0.8)';
                header.style.boxShadow = '0 5px 20px rgba(0, 0, 0, 0.5)';
            }
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Create floating leaves effect
        function createLeaf() {
            const leaf = document.createElement('div');
            leaf.innerHTML = '🍃';
            leaf.style.position = 'fixed';
            leaf.style.fontSize = Math.random() * 20 + 15 + 'px';
            leaf.style.left = Math.random() * 100 + 'vw';
            leaf.style.top = '-50px';
            leaf.style.opacity = Math.random() * 0.8 + 0.2;
            leaf.style.pointerEvents = 'none';
            leaf.style.zIndex = '1';
            leaf.style.animation = `fall ${Math.random() * 3 + 4}s linear forwards`;
            
            document.body.appendChild(leaf);
            
            setTimeout(() => {
                leaf.remove();
            }, 7000);
        }

        // Add CSS for falling leaves
        const style = document.createElement('style');
        style.textContent = `
            @keyframes fall {
                0% {
                    transform: translateY(-50px) rotate(0deg);
                }
                100% {
                    transform: translateY(100vh) rotate(360deg);
                }
            }
        `;
        document.head.appendChild(style);

        // Create leaves periodically
        setInterval(createLeaf, 2000);
    </script>
</body>
</html>
