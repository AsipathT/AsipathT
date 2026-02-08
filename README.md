<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Niduka Vikum Asipath | Portfolio Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #7c3aed;
            --dark: #1e293b;
            --light: #f8fafc;
            --gray: #64748b;
            --gray-light: #e2e8f0;
            --success: #10b981;
            --warning: #f59e0b;
            --danger: #ef4444;
            --shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --shadow-light: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);
            --radius: 12px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4edf5 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            animation: fadeIn 1s ease-out;
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            margin-bottom: 40px;
            padding-top: 20px;
            animation: slideDown 0.8s ease-out;
        }
        
        .profile-name {
            font-family: 'Poppins', sans-serif;
            font-size: 2.8rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 10px;
            letter-spacing: -0.5px;
        }
        
        .title-container {
            margin-bottom: 30px;
            height: 60px;
            overflow: hidden;
            position: relative;
        }
        
        .typing-text {
            font-size: 1.4rem;
            font-weight: 500;
            color: var(--gray);
            display: inline-block;
            position: relative;
        }
        
        .typing-text::after {
            content: '|';
            animation: blink 1s infinite;
            color: var(--primary);
            font-weight: bold;
        }
        
        .title-list {
            list-style: none;
            animation: slideUp 15s infinite;
        }
        
        .title-item {
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            font-weight: 500;
            color: var(--primary);
        }
        
        /* Card Styles */
        .card {
            background: white;
            border-radius: var(--radius);
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: var(--shadow-light);
            transition: var(--transition);
            opacity: 0;
            animation: fadeInUp 0.8s ease-out forwards;
            animation-delay: calc(var(--animation-order) * 0.1s);
            border: 1px solid var(--gray-light);
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }
        
        .card-title {
            font-family: 'Poppins', sans-serif;
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card-title i {
            color: var(--primary);
        }
        
        .section-divider {
            height: 4px;
            width: 60px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 2px;
            margin-bottom: 15px;
        }
        
        /* About Section */
        .about-content {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .about-item {
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }
        
        .about-icon {
            color: var(--primary);
            font-size: 1.2rem;
            margin-top: 3px;
        }
        
        .highlight {
            background: linear-gradient(120deg, rgba(37, 99, 235, 0.1) 0%, rgba(124, 58, 237, 0.1) 100%);
            padding: 2px 8px;
            border-radius: 4px;
            font-weight: 500;
            color: var(--primary-dark);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 15px;
        }
        
        .project-card {
            background: var(--light);
            border-radius: var(--radius);
            padding: 20px;
            transition: var(--transition);
            border-left: 4px solid var(--primary);
            animation: fadeIn 0.8s ease-out;
        }
        
        .project-card:hover {
            transform: translateX(5px);
            background: white;
        }
        
        .project-title {
            font-weight: 600;
            font-size: 1.2rem;
            color: var(--dark);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .project-title i {
            color: var(--secondary);
        }
        
        .project-desc {
            color: var(--gray);
            font-size: 0.95rem;
            margin-bottom: 15px;
        }
        
        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .tech-tag {
            background: var(--gray-light);
            color: var(--dark);
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .skill-category {
            background: var(--light);
            padding: 20px;
            border-radius: var(--radius);
            transition: var(--transition);
        }
        
        .skill-category:hover {
            background: white;
        }
        
        .skill-category-title {
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.1rem;
        }
        
        .skill-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }
        
        .skill-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background: white;
            border-radius: 10px;
            box-shadow: var(--shadow-light);
            transition: var(--transition);
        }
        
        .skill-icon:hover {
            transform: scale(1.1);
            box-shadow: var(--shadow);
        }
        
        .skill-icon i {
            font-size: 1.8rem;
            margin-bottom: 5px;
        }
        
        .skill-name {
            font-size: 0.7rem;
            font-weight: 500;
            color: var(--gray);
        }
        
        /* Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 15px;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #f6f8ff 0%, #f0f4ff 100%);
            border-radius: var(--radius);
            padding: 20px;
            text-align: center;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            border: 1px solid var(--gray-light);
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 5px;
        }
        
        .stat-label {
            color: var(--gray);
            font-weight: 500;
            font-size: 0.95rem;
        }
        
        /* Graph Animation */
        .graph-container {
            background: var(--light);
            border-radius: var(--radius);
            padding: 20px;
            margin-top: 15px;
            height: 200px;
            position: relative;
            overflow: hidden;
        }
        
        .graph-bars {
            display: flex;
            align-items: flex-end;
            justify-content: space-around;
            height: 150px;
            position: absolute;
            bottom: 30px;
            width: 90%;
            left: 5%;
        }
        
        .graph-bar {
            width: 40px;
            background: linear-gradient(to top, var(--primary), var(--secondary));
            border-radius: 4px 4px 0 0;
            position: relative;
            animation: growBar 1.5s ease-out forwards;
            transform-origin: bottom;
        }
        
        .graph-bar:nth-child(1) { height: 40%; animation-delay: 0.2s; }
        .graph-bar:nth-child(2) { height: 70%; animation-delay: 0.4s; }
        .graph-bar:nth-child(3) { height: 60%; animation-delay: 0.6s; }
        .graph-bar:nth-child(4) { height: 90%; animation-delay: 0.8s; }
        .graph-bar:nth-child(5) { height: 50%; animation-delay: 1s; }
        .graph-bar:nth-child(6) { height: 80%; animation-delay: 1.2s; }
        .graph-bar:nth-child(7) { height: 65%; animation-delay: 1.4s; }
        
        .graph-labels {
            display: flex;
            justify-content: space-around;
            position: absolute;
            bottom: 0;
            width: 90%;
            left: 5%;
            font-size: 0.8rem;
            color: var(--gray);
            font-weight: 500;
        }
        
        /* Trophies Section */
        .trophies-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 15px;
        }
        
        .trophy {
            display: flex;
            flex-direction: column;
            align-items: center;
            animation: float 3s ease-in-out infinite;
            animation-delay: calc(var(--trophy-order) * 0.2s);
        }
        
        .trophy i {
            font-size: 2.5rem;
            color: #FFD700;
            margin-bottom: 5px;
            filter: drop-shadow(0 3px 5px rgba(255, 215, 0, 0.3));
        }
        
        .trophy-label {
            font-size: 0.8rem;
            font-weight: 500;
            color: var(--gray);
        }
        
        /* Connect Section */
        .connect-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 15px;
        }
        
        .connect-button {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 24px;
            border-radius: 50px;
            font-weight: 500;
            text-decoration: none;
            transition: var(--transition);
            background: white;
            color: var(--dark);
            box-shadow: var(--shadow-light);
            border: 1px solid var(--gray-light);
        }
        
        .connect-button:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow);
        }
        
        .linkedin:hover {
            background: #0077b5;
            color: white;
            border-color: #0077b5;
        }
        
        .email:hover {
            background: #D14836;
            color: white;
            border-color: #D14836;
        }
        
        .github:hover {
            background: #333;
            color: white;
            border-color: #333;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 40px;
            color: var(--gray);
            font-size: 0.9rem;
            border-top: 1px solid var(--gray-light);
            animation: fadeIn 1s ease-out;
        }
        
        .footer-highlight {
            color: var(--primary);
            font-weight: 500;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideUp {
            0%, 20% { transform: translateY(0); }
            25%, 45% { transform: translateY(-60px); }
            50%, 70% { transform: translateY(-120px); }
            75%, 95% { transform: translateY(-180px); }
            100% { transform: translateY(-240px); }
        }
        
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }
        
        @keyframes growBar {
            from { transform: scaleY(0); }
            to { transform: scaleY(1); }
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .profile-name {
                font-size: 2.2rem;
            }
            
            .title-item {
                font-size: 1.2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .connect-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .connect-button {
                width: 100%;
                max-width: 250px;
                justify-content: center;
            }
        }
        
        @media (max-width: 480px) {
            .profile-name {
                font-size: 1.8rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .card {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <h1 class="profile-name">Niduka Vikum Asipath</h1>
            <div class="title-container">
                <div class="typing-text"></div>
                <ul class="title-list">
                    <li class="title-item"><i class="fas fa-code"></i> Associate Software Engineer</li>
                    <li class="title-item"><i class="fas fa-layer-group"></i> Full Stack Developer</li>
                    <li class="title-item"><i class="fas fa-brain"></i> ERP & AI/ML Enthusiast</li>
                    <li class="title-item"><i class="fas fa-graduation-cap"></i> Software Engineering Undergraduate</li>
                    <li class="title-item"><i class="fas fa-rocket"></i> Passionate about Scalable Architectures</li>
                </ul>
            </div>
        </header>

        <!-- About Me Section -->
        <section class="card" style="--animation-order: 1">
            <div class="card-title">
                <i class="fas fa-user"></i> About Me
            </div>
            <div class="section-divider"></div>
            <div class="about-content">
                <div class="about-item">
                    <i class="fas fa-graduation-cap about-icon"></i>
                    <p>🎓 Undergraduate at <span class="highlight">SLIIT</span>, specializing in Software Engineering</p>
                </div>
                <div class="about-item">
                    <i class="fas fa-briefcase about-icon"></i>
                    <p>💼 Currently working as an <span class="highlight">Associate Software Engineer</span></p>
                </div>
                <div class="about-item">
                    <i class="fas fa-book about-icon"></i>
                    <p>🌱 Currently learning <span class="highlight">ERP Systems and AI/ML</span></p>
                </div>
                <div class="about-item">
                    <i class="fas fa-lightbulb about-icon"></i>
                    <p>💡 Passionate Full Stack Developer with hands-on experience in ERP systems, web platforms, and scalable backend architectures</p>
                </div>
                <div class="about-item">
                    <i class="fas fa-envelope about-icon"></i>
                    <p>📫 Reach me at: <span class="highlight">nidukavikumasipath@gmail.com</span></p>
                </div>
                <div class="about-item">
                    <i class="fas fa-comment-dots about-icon"></i>
                    <p>💬 Ask me about <span class="highlight">Web Development, ERP Systems, React, and Backend Architecture</span></p>
                </div>
            </div>
        </section>

        <!-- Featured Projects Section -->
        <section class="card" style="--animation-order: 2">
            <div class="card-title">
                <i class="fas fa-star"></i> Featured Projects
            </div>
            <div class="section-divider"></div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">
                        <i class="fas fa-film"></i> Online Movie & TV Series Browsing System
                    </div>
                    <p class="project-desc">
                        Full-stack web application with authentication, payment processing, and content management.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">Java</span>
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">JSP</span>
                        <span class="tech-tag">Tomcat</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-title">
                        <i class="fas fa-hotel"></i> Hotel Management System
                    </div>
                    <p class="project-desc">
                        ERP-style system with payment modules, reporting, and admin dashboards.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">Java</span>
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">MVC Architecture</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-title">
                        <i class="fas fa-robot"></i> AI-Powered Resume Analyzer
                    </div>
                    <p class="project-desc">
                        ML-based system to evaluate resumes and match job roles.
                    </p>
                    <div class="tech-tags">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">Flask</span>
                        <span class="tech-tag">NLP</span>
                        <span class="tech-tag">Machine Learning</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Technologies Section -->
        <section class="card" style="--animation-order: 3">
            <div class="card-title">
                <i class="fas fa-code"></i> Technologies I Know
            </div>
            <div class="section-divider"></div>
            <div class="skills-container">
                <div class="skill-category">
                    <div class="skill-category-title">
                        <i class="fas fa-paint-brush"></i> Frontend Development
                    </div>
                    <div class="skill-icons">
                        <div class="skill-icon">
                            <i class="fab fa-html5" style="color: #E34F26;"></i>
                            <span class="skill-name">HTML5</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-css3-alt" style="color: #1572B6;"></i>
                            <span class="skill-name">CSS3</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-js" style="color: #F7DF1E;"></i>
                            <span class="skill-name">JavaScript</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-react" style="color: #61DAFB;"></i>
                            <span class="skill-name">React</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-vuejs" style="color: #4FC08D;"></i>
                            <span class="skill-name">Vue.js</span>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <div class="skill-category-title">
                        <i class="fas fa-server"></i> Backend Development
                    </div>
                    <div class="skill-icons">
                        <div class="skill-icon">
                            <i class="fab fa-node-js" style="color: #339933;"></i>
                            <span class="skill-name">Node.js</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-python" style="color: #3776AB;"></i>
                            <span class="skill-name">Python</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fas fa-database" style="color: #4479A1;"></i>
                            <span class="skill-name">MySQL</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fas fa-fire" style="color: #FFCA28;"></i>
                            <span class="skill-name">Firebase</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fas fa-leaf" style="color: #339933;"></i>
                            <span class="skill-name">MongoDB</span>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <div class="skill-category-title">
                        <i class="fas fa-tools"></i> Tools & Others
                    </div>
                    <div class="skill-icons">
                        <div class="skill-icon">
                            <i class="fab fa-git-alt" style="color: #F05032;"></i>
                            <span class="skill-name">Git</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-docker" style="color: #2496ED;"></i>
                            <span class="skill-name">Docker</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fab fa-figma" style="color: #F24E1E;"></i>
                            <span class="skill-name">Figma</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fas fa-terminal" style="color: #4D4D4D;"></i>
                            <span class="skill-name">Linux</span>
                        </div>
                        <div class="skill-icon">
                            <i class="fas fa-code-branch" style="color: #FF6B6B;"></i>
                            <span class="skill-name">Postman</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats Section -->
        <section class="card" style="--animation-order: 4">
            <div class="card-title">
                <i class="fas fa-chart-line"></i> GitHub Stats
            </div>
            <div class="section-divider"></div>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number" id="repos">24</div>
                    <div class="stat-label">Public Repositories</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="commits">1,248</div>
                    <div class="stat-label">Total Commits</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="pr">47</div>
                    <div class="stat-label">Pull Requests</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="issues">18</div>
                    <div class="stat-label">Issues Resolved</div>
                </div>
            </div>
            
            <div class="graph-container">
                <div class="graph-bars">
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                    <div class="graph-bar"></div>
                </div>
                <div class="graph-labels">
                    <span>Mon</span>
                    <span>Tue</span>
                    <span>Wed</span>
                    <span>Thu</span>
                    <span>Fri</span>
                    <span>Sat</span>
                    <span>Sun</span>
                </div>
            </div>
        </section>

        <!-- GitHub Trophies Section -->
        <section class="card" style="--animation-order: 5">
            <div class="card-title">
                <i class="fas fa-trophy"></i> GitHub Trophies
            </div>
            <div class="section-divider"></div>
            <div class="trophies-container">
                <div class="trophy" style="--trophy-order: 1">
                    <i class="fas fa-star"></i>
                    <div class="trophy-label">Arctic Code Vault</div>
                </div>
                <div class="trophy" style="--trophy-order: 2">
                    <i class="fas fa-code-commit"></i>
                    <div class="trophy-label">Commit Leader</div>
                </div>
                <div class="trophy" style="--trophy-order: 3">
                    <i class="fas fa-code-branch"></i>
                    <div class="trophy-label">Pull Request Hero</div>
                </div>
                <div class="trophy" style="--trophy-order: 4">
                    <i class="fas fa-bug"></i>
                    <div class="trophy-label">Issue Hunter</div>
                </div>
                <div class="trophy" style="--trophy-order: 5">
                    <i class="fas fa-infinity"></i>
                    <div class="trophy-label">Longevity</div>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section class="card" style="--animation-order: 6">
            <div class="card-title">
                <i class="fas fa-handshake"></i> Connect With Me
            </div>
            <div class="section-divider"></div>
            <div class="connect-buttons">
                <a href="https://linkedin.com/in/niduka-thennakoon" target="_blank" class="connect-button linkedin">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="mailto:nidukavikumasipath@gmail.com" class="connect-button email">
                    <i class="fas fa-envelope"></i> Email
                </a>
                <a href="https://github.com/AsipathT" target="_blank" class="connect-button github">
                    <i class="fab fa-github"></i> GitHub
                </a>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>⭐️ From <span class="footer-highlight">AsipathT</span></p>
            <p style="margin-top: 10px; font-size: 0.8rem;">
                <span id="profile-views">1,245</span> Profile Views | Last Updated: <span id="current-date"></span>
            </p>
        </footer>
    </div>

    <script>
        // Set current date
        document.getElementById('current-date').textContent = new Date().toLocaleDateString('en-US', {
            year: 'numeric',
            month: 'long',
            day: 'numeric'
        });
        
        // Animate stat numbers
        function animateValue(id, start, end, duration) {
            let obj = document.getElementById(id);
            let startTime = null;
            
            function step(timestamp) {
                if (!startTime) startTime = timestamp;
                const progress = Math.min((timestamp - startTime) / duration, 1);
                const value = Math.floor(progress * (end - start) + start);
                obj.textContent = value;
                
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            }
            
            window.requestAnimationFrame(step);
        }
        
        // Start animations after page loads
        window.addEventListener('load', function() {
            // Animate the stat numbers
            animateValue('repos', 0, 24, 1500);
            animateValue('commits', 0, 1248, 2000);
            animateValue('pr', 0, 47, 1500);
            animateValue('issues', 0, 18, 1500);
            
            // Simulate profile views animation
            setTimeout(() => {
                animateValue('profile-views', 1200, 1245, 1000);
            }, 500);
            
            // Add hover effects to skill icons
            const skillIcons = document.querySelectorAll('.skill-icon');
            skillIcons.forEach(icon => {
                icon.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.1)';
                });
                
                icon.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1)';
                });
            });
        });
        
        // Dynamic typing effect for the title
        const titles = [
            "Associate Software Engineer",
            "Full Stack Developer", 
            "ERP & AI/ML Enthusiast",
            "Software Engineering Undergraduate",
            "Passionate about Scalable Architectures"
        ];
        
        let titleIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.querySelector('.typing-text');
        
        function typeEffect() {
            const currentTitle = titles[titleIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentTitle.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentTitle.substring(0, charIndex + 1);
                charIndex++;
            }
            
            if (!isDeleting && charIndex === currentTitle.length) {
                isDeleting = true;
                setTimeout(typeEffect, 1500);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                titleIndex = (titleIndex + 1) % titles.length;
                setTimeout(typeEffect, 500);
            } else {
                setTimeout(typeEffect, isDeleting ? 50 : 100);
            }
        }
        
        // Start typing effect
        setTimeout(typeEffect, 1000);
    </script>
</body>
</html>