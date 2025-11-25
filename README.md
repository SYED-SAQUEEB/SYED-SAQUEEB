<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syed Saqueeb | MERN Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        :root {
            --primary: #6C63FF;
            --secondary: #4A44C6;
            --accent: #FF6584;
            --dark: #2D2B55;
            --light: #F5F5F7;
            --text: #333333;
            --text-light: #777777;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%236C63FF' fill-opacity='0.05' fill-rule='evenodd'/%3E%3C/svg%3E");
            opacity: 0.5;
            z-index: -1;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid var(--primary);
            box-shadow: 0 10px 30px rgba(108, 99, 255, 0.3);
            margin-bottom: 20px;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
        
        .name {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .tagline {
            font-size: 1.5rem;
            color: var(--text-light);
            margin-bottom: 20px;
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: white;
            color: var(--primary);
            font-size: 1.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .social-icons a:hover {
            transform: translateY(-5px);
            background: var(--primary);
            color: white;
        }
        
        /* Section Styles */
        .section {
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }
        
        .section:hover {
            transform: translateY(-5px);
        }
        
        .section-title {
            font-size: 2rem;
            margin-bottom: 25px;
            position: relative;
            display: inline-block;
            color: var(--dark);
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        /* About Section */
        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-light);
        }
        
        .highlight {
            color: var(--primary);
            font-weight: 600;
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }
        
        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            border: 1px solid #f0f0f0;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .project-content {
            padding: 20px;
        }
        
        .project-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--dark);
        }
        
        .project-description {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.95rem;
        }
        
        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .project-link:hover {
            gap: 10px;
        }
        
        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .skill-category {
            background: #f9f9ff;
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            border-left: 4px solid var(--primary);
        }
        
        .skill-category:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.1);
        }
        
        .skill-category h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .skill-category h3 i {
            color: var(--primary);
        }
        
        .skill-list {
            list-style: none;
        }
        
        .skill-list li {
            padding: 8px 0;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-light);
        }
        
        .skill-list li::before {
            content: '▹';
            color: var(--primary);
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-light);
            font-size: 1rem;
        }
        
        .footer-heart {
            color: var(--accent);
            animation: heartbeat 1.5s ease infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.2); }
            10% { transform: scale(1); }
            15% { transform: scale(1.3); }
            50% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
            
            .section {
                padding: 30px 20px;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-img-container">
                <!-- Placeholder for profile image - replace with actual image -->
                <div class="profile-img">
                    <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                        <circle cx="50" cy="50" r="45" fill="#6C63FF" />
                        <circle cx="35" cy="40" r="5" fill="white" />
                        <circle cx="65" cy="40" r="5" fill="white" />
                        <path d="M 30 65 Q 50 80 70 65" stroke="white" stroke-width="3" fill="transparent" />
                    </svg>
                </div>
            </div>
            <h1 class="name">Syed Saqueeb</h1>
            <p class="tagline">MERN Stack Developer • UI/UX Enthusiast</p>
            <div class="social-icons">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fas fa-envelope"></i></a>
            </div>
        </header>

        <!-- About Section -->
        <section class="section">
            <h2 class="section-title">About Me</h2>
            <p class="about-text">
                I'm a passionate <span class="highlight">MERN Stack Developer</span> with a keen eye for modern UI/UX design. 
                I specialize in creating <span class="highlight">mobile-first, responsive web applications</span> that deliver 
                exceptional user experiences. My focus is on building <span class="highlight">pixel-perfect interfaces</span> 
                and <span class="highlight">performance-optimized</span> solutions using clean, scalable architecture.
            </p>
        </section>

        <!-- Projects Section -->
        <section class="section">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-hospital"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Genuine Hospital Website</h3>
                        <p class="project-description">A responsive medical website with modern UI design, focusing on user experience and accessibility.</p>
                        <a href="https://genuinehospital.netlify.app/" class="project-link" target="_blank">
                            View Live <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-paint-roller"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Almannan Decor</h3>
                        <p class="project-description">A clean, semantic layout with responsive mobile UI for a home decor business.</p>
                        <a href="https://almannandecor.netlify.app/" class="project-link" target="_blank">
                            View Live <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Portfolio Website</h3>
                        <p class="project-description">A modern, animated portfolio website showcasing projects with interactive elements.</p>
                        <a href="#" class="project-link">
                            View Project <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section class="section">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3><i class="fas fa-server"></i> Backend</h3>
                    <ul class="skill-list">
                        <li>Node.js</li>
                        <li>Express.js</li>
                        <li>MongoDB</li>
                        <li>RESTful APIs</li>
                        <li>Authentication & Authorization</li>
                    </ul>
                </div>
                
                <div class="skill-category">
                    <h3><i class="fas fa-laptop-code"></i> Frontend</h3>
                    <ul class="skill-list">
                        <li>React.js</li>
                        <li>JavaScript (ES6+)</li>
                        <li>Tailwind CSS</li>
                        <li>HTML5 & CSS3</li>
                        <li>Responsive Design</li>
                    </ul>
                </div>
                
                <div class="skill-category">
                    <h3><i class="fas fa-tools"></i> Tools & Others</h3>
                    <ul class="skill-list">
                        <li>Git & GitHub</li>
                        <li>VS Code</li>
                        <li>Chrome DevTools</li>
                        <li>Netlify & Heroku</li>
                        <li>UI/UX Principles</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>Made with <span class="footer-heart">❤️</span> by <strong>Syed Saqueeb</strong></p>
        </footer>
    </div>

    <script>
        // Simple animation on scroll
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                section.style.opacity = 0;
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
