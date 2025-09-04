<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abduraxmonov Baxodir - Junior HTML/CSS Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;900&family=Open+Sans:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Design tokens based on the brief */
            --background: #ffffff;
            --foreground: #475569;
            --card: #f1f5f9;
            --card-foreground: #475569;
            --primary: #059669;
            --primary-foreground: #ffffff;
            --secondary: #10b981;
            --secondary-foreground: #ffffff;
            --accent: #10b981;
            --accent-foreground: #ffffff;
            --border: #e5e7eb;
            --muted: #f1f5f9;
            --muted-foreground: #475569;
            --radius: 0.5rem;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.6;
            color: var(--foreground);
            background-color: var(--background);
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 900;
            line-height: 1.2;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid var(--border);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Montserrat', sans-serif;
            font-weight: 900;
            font-size: 1.5rem;
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--foreground);
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .language-selector {
            position: relative;
        }

        .language-btn {
            background: var(--primary);
            color: var(--primary-foreground);
            border: none;
            padding: 0.5rem 1rem;
            border-radius: var(--radius);
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .language-btn:hover {
            background: var(--secondary);
            transform: translateY(-2px);
        }

        .language-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background: var(--background);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            display: none;
            min-width: 120px;
            z-index: 1001;
        }

        .language-dropdown.active {
            display: block;
        }

        .language-dropdown button {
            width: 100%;
            padding: 0.75rem 1rem;
            border: none;
            background: none;
            text-align: left;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .language-dropdown button:hover {
            background: var(--muted);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, var(--background) 0%, var(--muted) 100%);
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="%23059669" stroke-width="0.5" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: var(--muted-foreground);
            margin-bottom: 2rem;
            font-weight: 500;
        }

        .hero-tagline {
            font-size: 1.5rem;
            color: var(--foreground);
            margin-bottom: 3rem;
            font-weight: 600;
        }

        .cta-button {
            display: inline-block;
            background: var(--primary);
            color: var(--primary-foreground);
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: var(--radius);
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(5, 150, 105, 0.3);
        }

        .cta-button:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(5, 150, 105, 0.4);
        }

        /* About Section */
        .about {
            padding: 5rem 0;
            background: var(--background);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .about-image {
            text-align: center;
        }

        .profile-image {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            margin: 0 auto;
            box-shadow: 0 20px 40px rgba(5, 150, 105, 0.3);
        }

        /* Skills Section */
        .skills {
            padding: 5rem 0;
            background: var(--muted);
        }

        .skills h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: var(--background);
            padding: 2rem;
            border-radius: var(--radius);
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .skill-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-size: 2rem;
            color: white;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .skill-progress {
            background: var(--border);
            height: 8px;
            border-radius: 4px;
            overflow: hidden;
            margin-top: 1rem;
        }

        .skill-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 4px;
            transition: width 2s ease;
        }

        /* Projects Section */
        .projects {
            padding: 5rem 0;
            background: var(--background);
        }

        .projects h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--card);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .project-content p {
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: var(--primary);
            color: var(--primary-foreground);
            padding: 0.25rem 0.75rem;
            border-radius: 1rem;
            font-size: 0.875rem;
            font-weight: 500;
        }

        .project-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s ease;
        }

        .project-link:hover {
            color: var(--secondary);
        }

        /* Contact Section */
        .contact {
            padding: 5rem 0;
            background: var(--muted);
        }

        .contact h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary);
        }

        .social-media {
            max-width: 600px;
            margin: 0 auto 3rem;
            background: var(--background);
            padding: 2rem;
            border-radius: var(--radius);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            text-align: center;
        }

        .social-media h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .social-links-contact {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            background: var(--primary);
            color: var(--primary-foreground);
            text-decoration: none;
            padding: 0.75rem 1.5rem;
            border-radius: var(--radius);
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(5, 150, 105, 0.2);
        }

        .social-link:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(5, 150, 105, 0.3);
        }

        .social-icon {
            width: 20px;
            height: 20px;
            fill: currentColor;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: var(--background);
            padding: 3rem;
            border-radius: var(--radius);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--foreground);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid var(--border);
            border-radius: var(--radius);
            font-size: 1rem;
            transition: border-color 0.3s ease;
            background: var(--background);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .submit-btn {
            width: 100%;
            background: var(--primary);
            color: var(--primary-foreground);
            border: none;
            padding: 1rem 2rem;
            border-radius: var(--radius);
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            background: var(--secondary);
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: var(--foreground);
            color: var(--background);
            text-align: center;
            padding: 2rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1rem;
        }

        .social-links a {
            color: var(--background);
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: var(--secondary);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-tagline {
                font-size: 1.25rem;
            }

            .social-links-contact {
                flex-direction: column;
                align-items: center;
            }

            .social-link {
                width: 100%;
                max-width: 250px;
                justify-content: center;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in-up {
            animation: fadeInUp 0.8s ease forwards;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">AB</div>
            <ul class="nav-links">
                <li><a href="#home" data-translate="nav-home">Bosh sahifa</a></li>
                <li><a href="#about" data-translate="nav-about">Men haqimda</a></li>
                <li><a href="#skills" data-translate="nav-skills">Ko'nikmalar</a></li>
                <li><a href="#projects" data-translate="nav-projects">Loyihalar</a></li>
                <li><a href="#contact" data-translate="nav-contact">Aloqa</a></li>
                <li class="language-selector">
                    <button class="language-btn" onclick="toggleLanguageDropdown()">
                        <span id="current-lang">O'Z</span> ▼
                    </button>
                    <div class="language-dropdown" id="language-dropdown">
                        <button onclick="changeLanguage('uz')">O'zbek</button>
                        <button onclick="changeLanguage('en')">English</button>
                        <button onclick="changeLanguage('ru')">Русский</button>
                        <button onclick="changeLanguage('ko')">한국어</button>
                    </div>
                </li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content fade-in-up">
                <h1 data-translate="hero-name">Abduraxmonov Baxodir</h1>
                <p class="hero-subtitle" data-translate="hero-title">Junior HTML/CSS Developer</p>
                <p class="hero-tagline" data-translate="hero-tagline">Chiroyli veb-tajribalar yaratish</p>
                <a href="#projects" class="cta-button" data-translate="hero-cta">Ishlarimni ko'ring</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text fade-in-up">
                    <h2 data-translate="about-title">Men haqimda</h2>
                    <p data-translate="about-text1">Salom! Men Abduraxmonov Baxodir, HTML va CSS sohasida ixtisoslashgan junior dasturchiman. Zamonaviy va foydalanuvchi-do'st veb-saytlar yaratishga ishtiyoqim bor.</p>
                    <p data-translate="about-text2">Men har bir loyihaga kreativlik va texnik bilimlarni olib kelaman. Mening maqsadim - har bir mijoz uchun mukammal raqamli tajriba yaratish.</p>
                    <p data-translate="about-text3">Doimiy o'rganish va rivojlanishga intilaman, yangi texnologiyalar va dizayn tendentsiyalarini kuzatib boraman.</p>
                </div>
                <div class="about-image fade-in-up">
                    <div class="profile-image">AB</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2 class="fade-in-up" data-translate="skills-title">Ko'nikmalarim</h2>
            <div class="skills-grid">
                <div class="skill-card fade-in-up">
                    <div class="skill-icon">🌐</div>
                    <h3>HTML5</h3>
                    <p data-translate="html-desc">Semantik va zamonaviy HTML strukturalar</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 90%"></div>
                    </div>
                </div>
                <div class="skill-card fade-in-up">
                    <div class="skill-icon">🎨</div>
                    <h3>CSS3</h3>
                    <p data-translate="css-desc">Responsive dizayn va animatsiyalar</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 85%"></div>
                    </div>
                </div>
                <div class="skill-card fade-in-up">
                    <div class="skill-icon">⚡</div>
                    <h3>JavaScript</h3>
                    <p data-translate="js-desc">Interaktiv veb-elementlar yaratish</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 75%"></div>
                    </div>
                </div>
                <div class="skill-card fade-in-up">
                    <div class="skill-icon">📱</div>
                    <h3 data-translate="responsive-title">Responsive Design</h3>
                    <p data-translate="responsive-desc">Barcha qurilmalarda mukammal ko'rinish</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 88%"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2 class="fade-in-up" data-translate="projects-title">Loyihalarim</h2>
            <div class="projects-grid">
                <div class="project-card fade-in-up">
                    <div class="project-image">🏪</div>
                    <div class="project-content">
                        <h3 data-translate="project1-title">E-commerce Sayt</h3>
                        <p data-translate="project1-desc">Zamonaviy onlayn do'kon interfeysi, to'liq responsive dizayn bilan.</p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML5</span>
                            <span class="tech-tag">CSS3</span>
                            <span class="tech-tag">JavaScript</span>
                        </div>
                        <a href="#" class="project-link" data-translate="view-project">Loyihani ko'rish →</a>
                    </div>
                </div>
                <div class="project-card fade-in-up">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3 data-translate="project2-title">Dashboard Interface</h3>
                        <p data-translate="project2-desc">Ma'lumotlarni vizualizatsiya qilish uchun zamonaviy dashboard.</p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML5</span>
                            <span class="tech-tag">CSS3</span>
                            <span class="tech-tag">Chart.js</span>
                        </div>
                        <a href="#" class="project-link" data-translate="view-project">Loyihani ko'rish →</a>
                    </div>
                </div>
                <div class="project-card fade-in-up">
                    <div class="project-image">🎯</div>
                    <div class="project-content">
                        <h3 data-translate="project3-title">Landing Page</h3>
                        <p data-translate="project3-desc">Yuqori konversiya darajasiga ega bo'lgan landing page.</p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML5</span>
                            <span class="tech-tag">CSS3</span>
                            <span class="tech-tag">SCSS</span>
                        </div>
                        <a href="#" class="project-link" data-translate="view-project">Loyihani ko'rish →</a>
                    </div>
                </div>
            </div>
            <div class="text-center" style="margin-top: 2rem;">
                <a href="Baxodi.html" class="cta-button" data-translate="view-all-projects">Barcha loyihalarni ko'rish</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="fade-in-up" data-translate="contact-title">Aloqa</h2>
            
            <div class="social-media fade-in-up">
                <h3 data-translate="social-title">Ijtimoiy tarmoqlar</h3>
                <div class="social-links-contact">
                    <a href="mailto:mnorlghtdream130  @gmail.com" class="social-link">
                        <svg class="social-icon" viewBox="0 0 24 24">
                            <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.89 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                        </svg>
                        <span data-translate="email-text">Email</span>
                    </a>
                    <a href="https://instagram.com/l1ghtdream_baxa03" class="social-link" target="_blank">
                        <svg class="social-icon" viewBox="0 0 24 24">
                            <path d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6 3.6 0 0 0 3.6-3.6V7.6C20 5.61 18.39 4 16.4 4H7.6m9.65 1.5a1.25 1.25 0 0 1 1.25 1.25A1.25 1.25 0 0 1 17.25 8A1.25 1.25 0 0 1 16 6.75a1.25 1.25 0 0 1 1.65-1.25M12 7a5 5 0 0 1 5 5a5 5 0 0 1-5 5a5 5 0 0 1-5-5a5 5 0 0 1 5-5m0 2a3 3 0 0 0-3 3a3 3 0 0 0 3 3a3 3 0 0 0 3-3a3 3 0 0 0-3-3z"/>
                        </svg>
                        <span>Instagram</span>
                    </a>
                    <a href="https://t.me/L1GHTDreaM_BaXa" class="social-link" target="_blank">
                        <svg class="social-icon" viewBox="0 0 24 24">
                            <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12a12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472c-.18 1.898-.962 6.502-1.36 8.627c-.168.9-.499 1.201-.82 1.23c-.696.065-1.225-.46-1.9-.902c-1.056-.693-1.653-1.124-2.678-1.8c-1.185-.78-.417-1.21.258-1.91c.177-.184 3.247-2.977 3.307-3.23c.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345c-.48.33-.913.49-1.302.48c-.428-.008-1.252-.241-1.865-.44c-.752-.245-1.349-.374-1.297-.789c.027-.216.325-.437.893-.663c3.498-1.524 5.83-2.529 6.998-3.014c3.332-1.386 4.025-1.627 4.476-1.635z"/>
                        </svg>
                        <span>Telegram</span>
                    </a>
                    <a href="https://www.facebook.com/share/1JfFKKuVif/" class="social-link" target="_blank">
                        <svg class="social-icon" viewBox="0 0 24 24">
                            <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669c1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                        </svg>
                        <span>Facebook</span>
                    </a>
                    <a href="https://www.threads.com/@l1ghtdream_baxa03" class="social-link" target="_blank">
                        <svg class="social-icon" viewBox="0 0 24 24">
                            <path d="M12.186 24h-.007c-3.581-.024-6.334-1.205-8.184-3.509C2.35 18.44 1.5 15.586 1.472 12.01v-.017c.03-3.579.879-6.43 2.525-8.482C5.845 1.205 8.6.024 12.18 0h.014c2.746.02 5.043.725 6.826 2.098c1.677 1.29 2.858 3.13 3.509 5.467l-2.04.569c-.584-2.043-1.496-3.467-2.713-4.237c-1.332-1.045-3.056-1.566-5.124-1.549c-3.06.021-5.424 1.068-7.028 3.11c-1.353 1.724-2.037 4.112-2.037 7.103c0 2.992.684 5.38 2.037 7.103c1.604 2.042 3.968 3.089 7.028 3.11c1.64.007 3.062-.39 4.226-1.177c1.179-.798 2.066-1.973 2.635-3.493l2.04.569c-.704 1.927-1.837 3.518-3.37 4.73C17.229 23.275 14.932 23.98 12.186 24z"/>
                            <path d="M17.637 8.88c-1.234-2.409-3.28-3.632-6.08-3.632c-1.378 0-2.6.35-3.63 1.04c-.906.61-1.617 1.48-2.113 2.583c-.464 1.03-.7 2.188-.7 3.44c0 1.252.236 2.41.7 3.44c.496 1.103 1.207 1.973 2.113 2.583c1.03.69 2.252 1.04 3.63 1.04c2.8 0 4.846-1.223 6.08-3.632c.464-1.03.7-2.188.7-3.44c0-1.252-.236-2.41-.7-3.44zm-1.354 6.229c-.464.906-1.11 1.617-1.92 2.113c-.81.496-1.73.744-2.743.744c-1.013 0-1.933-.248-2.743-.744c-.81-.496-1.456-1.207-1.92-2.113c-.464-.906-.696-1.933-.696-3.078c0-1.145.232-2.172.696-3.078c.464-.906 1.11-1.617 1.92-2.113c.81-.496 1.73-.744 2.743-.744c1.013 0 1.933.248 2.743.744c.81.496 1.456 1.207 1.92 2.113c.464.906.696 1.933.696 3.078c0 1.145-.232 2.172-.696 3.078z"/>
                        </svg>
                        <span>Threads</span>
                    </a>
                </div>
            </div>
            
            <form class="contact-form fade-in-up">
                <div class="form-group">
                    <label for="name" data-translate="form-name">Ismingiz</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email" data-translate="form-email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="message" data-translate="form-message">Xabar</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="submit-btn" data-translate="form-submit">Xabar yuborish</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#" title="GitHub">📧</a>
                <a href="#" title="LinkedIn">💼</a>
                <a href="#" title="Telegram">📱</a>
            </div>
            <p data-translate="footer-text">&copy; 2024 Abduraxmonov Baxodir. Barcha huquqlar himoyalangan.</p>
        </div>
    </footer>

    <script>
        // Language translations
        const translations = {
            uz: {
                'nav-home': 'Bosh sahifa',
                'nav-about': 'Men haqimda',
                'nav-skills': 'Ko\'nikmalar',
                'nav-projects': 'Loyihalar',
                'nav-contact': 'Aloqa',
                'hero-name': 'Abduraxmonov Baxodir',
                'hero-title': 'Junior HTML/CSS Developer',
                'hero-tagline': 'Chiroyli veb-tajribalar yaratish',
                'hero-cta': 'Ishlarimni ko\'ring',
                'about-title': 'Men haqimda',
                'about-text1': 'Salom! Men Abduraxmonov Baxodir, HTML va CSS sohasida ixtisoslashgan junior dasturchiman. Zamonaviy va foydalanuvchi-do\'st veb-saytlar yaratishga ishtiyoqim bor.',
                'about-text2': 'Men har bir loyihaga kreativlik va texnik bilimlarni olib kelaman. Mening maqsadim - har bir mijoz uchun mukammal raqamli tajriba yaratish.',
                'about-text3': 'Doimiy o\'rganish va rivojlanishga intilaman, yangi texnologiyalar va dizayn tendentsiyalarini kuzatib boraman.',
                'skills-title': 'Ko\'nikmalarim',
                'html-desc': 'Semantik va zamonaviy HTML strukturalar',
                'css-desc': 'Responsive dizayn va animatsiyalar',
                'js-desc': 'Interaktiv veb-elementlar yaratish',
                'responsive-title': 'Responsive Design',
                'responsive-desc': 'Barcha qurilmalarda mukammal ko\'rinish',
                'projects-title': 'Loyihalarim',
                'project1-title': 'E-commerce Sayt',
                'project1-desc': 'Zamonaviy onlayn do\'kon interfeysi, to\'liq responsive dizayn bilan.',
                'project2-title': 'Dashboard Interface',
                'project2-desc': 'Ma\'lumotlarni vizualizatsiya qilish uchun zamonaviy dashboard.',
                'project3-title': 'Landing Page',
                'project3-desc': 'Yuqori konversiya darajasiga ega bo\'lgan landing page.',
                'view-project': 'Loyihani ko\'rish →',
                'view-all-projects': 'Barcha loyihalarni ko\'rish →',
                'contact-title': 'Aloqa',
                'social-title': 'Ijtimoiy tarmoqlar',
                'email-text': 'Email',
                'form-name': 'Ismingiz',
                'form-email': 'Email',
                'form-message': 'Xabar',
                'form-submit': 'Xabar yuborish',
                'footer-text': '© 2024 Abduraxmonov Baxodir. Barcha huquqlar himoyalangan.'
            },
            en: {
                'nav-home': 'Home',
                'nav-about': 'About',
                'nav-skills': 'Skills',
                'nav-projects': 'Projects',
                'nav-contact': 'Contact',
                'hero-name': 'Abduraxmonov Baxodir',
                'hero-title': 'Junior HTML/CSS Developer',
                'hero-tagline': 'Crafting Beautiful Web Experiences',
                'hero-cta': 'View My Work',
                'about-title': 'About Me',
                'about-text1': 'Hello! I\'m Abduraxmonov Baxodir, a junior developer specializing in HTML and CSS. I\'m passionate about creating modern and user-friendly websites.',
                'about-text2': 'I bring creativity and technical knowledge to every project. My goal is to create perfect digital experiences for every client.',
                'about-text3': 'I strive for continuous learning and development, keeping up with new technologies and design trends.',
                'skills-title': 'My Skills',
                'html-desc': 'Semantic and modern HTML structures',
                'css-desc': 'Responsive design and animations',
                'js-desc': 'Creating interactive web elements',
                'responsive-title': 'Responsive Design',
                'responsive-desc': 'Perfect appearance on all devices',
                'projects-title': 'My Projects',
                'project1-title': 'E-commerce Site',
                'project1-desc': 'Modern online store interface with fully responsive design.',
                'project2-title': 'Dashboard Interface',
                'project2-desc': 'Modern dashboard for data visualization.',
                'project3-title': 'Landing Page',
                'project3-desc': 'Landing page with high conversion rate.',
                'view-project': 'View Project →',
                'view-all-projects': 'View All Projects →',
                'contact-title': 'Contact',
                'social-title': 'Social Media',
                'email-text': 'Email',
                'form-name': 'Your Name',
                'form-email': 'Email',
                'form-message': 'Message',
                'form-submit': 'Send Message',
                'footer-text': '© 2024 Abduraxmonov Baxodir. All rights reserved.'
            },
            ru: {
                'nav-home': 'Главная',
                'nav-about': 'Обо мне',
                'nav-skills': 'Навыки',
                'nav-projects': 'Проекты',
                'nav-contact': 'Контакты',
                'hero-name': 'Абдурахманов Баходир',
                'hero-title': 'Junior HTML/CSS Разработчик',
                'hero-tagline': 'Создание красивых веб-решений',
                'hero-cta': 'Посмотреть работы',
                'about-title': 'Обо мне',
                'about-text1': 'Привет! Я Абдурахманов Баходир, junior разработчик, специализирующийся на HTML и CSS. Увлечен созданием современных и удобных веб-сайтов.',
                'about-text2': 'Я привношу креативность и технические знания в каждый проект. Моя цель - создать идеальный цифровой опыт для каждого клиента.',
                'about-text3': 'Стремлюсь к постоянному обучению и развитию, слежу за новыми технологиями и трендами дизайна.',
                'skills-title': 'Мои навыки',
                'html-desc': 'Семантические и современные HTML структуры',
                'css-desc': 'Адаптивный дизайн и анимации',
                'js-desc': 'Создание интерактивных веб-элементов',
                'responsive-title': 'Адаптивный дизайн',
                'responsive-desc': 'Идеальный вид на всех устройствах',
                'projects-title': 'Мои проекты',
                'project1-title': 'E-commerce сайт',
                'project1-desc': 'Современный интерфейс интернет-магазина с полностью адаптивным дизайном.',
                'project2-title': 'Dashboard интерфейс',
                'project2-desc': 'Современная панель для визуализации данных.',
                'project3-title': 'Landing Page',
                'project3-desc': 'Посадочная страница с высоким коэффициентом конверсии.',
                'view-project': 'Посмотреть проект →',
                'view-all-projects': 'Посмотреть все проекты →',
                'contact-title': 'Контакты',
                'social-title': 'Социальные сети',
                'email-text': 'Электронная почта',
                'form-name': 'Ваше имя',
                'form-email': 'Email',
                'form-message': 'Сообщение',
                'form-submit': 'Отправить сообщение',
                'footer-text': '© 2024 Абдурахманов Баходир. Все права защищены.'
            },
            ko: {
                'nav-home': '홈',
                'nav-about': '소개',
                'nav-skills': '기술',
                'nav-projects': '프로젝트',
                'nav-contact': '연락처',
                'hero-name': '압두라흐모노프 바호디르',
                'hero-title': '주니어 HTML/CSS 개발자',
                'hero-tagline': '아름다운 웹 경험 창조',
                'hero-cta': '작업 보기',
                'about-title': '소개',
                'about-text1': '안녕하세요! 저는 HTML과 CSS를 전문으로 하는 주니어 개발자 압두라흐모노프 바호디르입니다. 현대적이고 사용자 친화적인 웹사이트 제작에 열정을 가지고 있습니다.',
                'about-text2': '모든 프로젝트에 창의성과 기술적 지식을 가져옵니다. 제 목표는 모든 고객을 위한 완벽한 디지털 경험을 만드는 것입니다.',
                'about-text3': '지속적인 학습과 발전을 추구하며, 새로운 기술과 디자인 트렌드를 따라갑니다.',
                'skills-title': '기술',
                'html-desc': '시맨틱하고 현대적인 HTML 구조',
                'css-desc': '반응형 디자인과 애니메이션',
                'js-desc': '인터랙티브 웹 요소 생성',
                'responsive-title': '반응형 디자인',
                'responsive-desc': '모든 기기에서 완벽한 모습',
                'projects-title': '프로젝트',
                'project1-title': '전자상거래 사이트',
                'project1-desc': '완전한 반응형 디자인을 갖춘 현대적인 온라인 상점 인터페이스.',
                'project2-title': '대시보드 인터페이스',
                'project2-desc': '데이터 시각화를 위한 현대적인 대시보드.',
                'project3-title': '랜딩 페이지',
                'project3-desc': '높은 전환율을 가진 랜딩 페이지.',
                'view-project': '프로젝트 보기 →',
                'view-all-projects': '모든 프로젝트 보기 →',
                'contact-title': '연락처',
                'social-title': '소셜 미디어',
                'email-text': '이메일',
                'form-name': '이름',
                'form-email': '이메일',
                'form-message': '메시지',
                'form-submit': '메시지 보내기',
                'footer-text': '© 2024 압두라흐모노프 바호디르. 모든 권리 보유.'
            }
        };

        let currentLanguage = 'uz';

        function toggleLanguageDropdown() {
            const dropdown = document.getElementById('language-dropdown');
            dropdown.classList.toggle('active');
        }

        function changeLanguage(lang) {
            currentLanguage = lang;
            const langMap = {
                'uz': 'O\'Z',
                'en': 'EN',
                'ru': 'RU',
                'ko': 'KO'
            };
            
            document.getElementById('current-lang').textContent = langMap[lang];
            document.getElementById('language-dropdown').classList.remove('active');
            
            // Update all translatable elements
            const elements = document.querySelectorAll('[data-translate]');
            elements.forEach(element => {
                const key = element.getAttribute('data-translate');
                if (translations[lang] && translations[lang][key]) {
                    element.textContent = translations[lang][key];
                }
            });
        }

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

        // Close language dropdown when clicking outside
        document.addEventListener('click', function(e) {
            const dropdown = document.getElementById('language-dropdown');
            const button = document.querySelector('.language-btn');
            
            if (!dropdown.contains(e.target) && !button.contains(e.target)) {
                dropdown.classList.remove('active');
            }
        });

        // Animate skill progress bars on scroll
        function animateSkillBars() {
            const skillBars = document.querySelectorAll('.skill-progress-bar');
            skillBars.forEach(bar => {
                const rect = bar.getBoundingClientRect();
                if (rect.top < window.innerHeight && rect.bottom > 0) {
                    bar.style.width = bar.style.width || '0%';
                }
            });
        }

        // Animate elements on scroll
        function animateOnScroll() {
            const elements = document.querySelectorAll('.fade-in-up');
            elements.forEach(element => {
                const rect = element.getBoundingClientRect();
                if (rect.top < window.innerHeight - 100) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        }

        // Initialize animations
        window.addEventListener('scroll', () => {
            animateOnScroll();
            animateSkillBars();
        });

        // Initial animation trigger
        document.addEventListener('DOMContentLoaded', () => {
            animateOnScroll();
            animateSkillBars();
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert(translations[currentLanguage]['form-submit'] || 'Xabar yuborildi!');
        });
    </script>
</body>
</html>
