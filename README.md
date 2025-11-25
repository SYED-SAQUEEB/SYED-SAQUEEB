<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syed Saqueeb | MERN Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Orbitron:wght@400;700;900&display=swap');
        
        :root {
            --primary: #6C63FF;
            --secondary: #4A44C6;
            --accent: #FF6584;
            --neon-primary: #00f3ff;
            --neon-secondary: #ff00c8;
            --dark: #0f0f1e;
            --darker: #070710;
            --light: #F5F5F7;
            --text: #e0e0ff;
            --text-light: #a0a0c0;
            --glass: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }
        
        .light-theme {
            --dark: #f0f0ff;
            --darker: #e0e0f0;
            --light: #0f0f1e;
            --text: #1a1a2e;
            --text-light: #4a4a6e;
            --glass: rgba(255, 255, 255, 0.7);
            --glass-border: rgba(255, 255, 255, 0.3);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.5s ease, color 0.3s ease;
        }
        
        body {
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: var(--text);
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 80%, rgba(108, 99, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 101, 132, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(0, 243, 255, 0.05) 0%, transparent 50%);
            z-index: -1;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Theme Toggle */
        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        
        .toggle-btn {
            background: var(--glass);
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            color: var(--text);
            border-radius: 50px;
            padding: 10px 20px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 500;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
        }
        
        .toggle-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        /* Loader */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--darker);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease, visibility 0.5s ease;
        }
        
        .loader.hidden {
            opacity: 0;
            visibility: hidden;
        }
        
        .neon-loader {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            position: relative;
            animation: rotate 1.5s linear infinite;
        }
        
        .neon-loader::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 3px solid transparent;
            border-top: 3px solid var(--neon-primary);
            border-bottom: 3px solid var(--neon-secondary);
            animation: spin 1s linear infinite;
            filter: drop-shadow(0 0 8px var(--neon-primary));
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            padding: 100px 20px 80px;
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
            opacity: 0.3;
            z-index: -1;
        }
        
        .profile-frame {
            width: 200px;
            height: 200px;
            margin: 0 auto 30px;
            position: relative;
            border-radius: 50%;
            padding: 10px;
            background: linear-gradient(135deg, var(--neon-primary), var(--neon-secondary), var(--primary));
            animation: rotate 8s linear infinite, glow 3s ease-in-out infinite alternate;
            box-shadow: 0 0 20px var(--neon-primary), 0 0 40px rgba(0, 243, 255, 0.3);
        }
        
        @keyframes glow {
            0% { box-shadow: 0 0 20px var(--neon-primary), 0 0 40px rgba(0, 243, 255, 0.3); }
            100% { box-shadow: 0 0 30px var(--neon-secondary), 0 0 60px rgba(255, 0, 200, 0.4); }
        }
        
        .profile-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
        }
        
        .name {
            font-size: 3.5rem;
            font-weight: 900;
            margin-bottom: 10px;
            font-family: 'Orbitron', sans-serif;
            background: linear-gradient(135deg, var(--neon-primary), var(--neon-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 10px rgba(0, 243, 255, 0.5);
            animation: textGlow 2s ease-in-out infinite alternate;
        }
        
        @keyframes textGlow {
            0% { text-shadow: 0 0 10px rgba(0, 243, 255, 0.5); }
            100% { text-shadow: 0 0 20px rgba(255, 0, 200, 0.7); }
        }
        
        .tagline {
            font-size: 1.5rem;
            color: var(--text-light);
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--glass);
            color: var(--text);
            font-size: 1.5rem;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .social-icons a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s ease;
        }
        
        .social-icons a:hover {
            transform: translateY(-5px);
            color: var(--neon-primary);
            box-shadow: 0 5px 15px rgba(0, 243, 255, 0.4);
            border-color: var(--neon-primary);
        }
        
        .social-icons a:hover::before {
            left: 100%;
        }
        
        /* Section Styles */
        .section {
            background: var(--glass);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 40px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--neon-primary), var(--neon-secondary));
        }
        
        .section:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }
        
        .section-title {
            font-size: 2.2rem;
            margin-bottom: 25px;
            position: relative;
            display: inline-block;
            color: var(--text);
            font-family: 'Orbitron', sans-serif;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--neon-primary), var(--neon-secondary));
            border-radius: 2px;
            box-shadow: 0 0 10px var(--neon-primary);
        }
        
        /* About Section */
        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-light);
        }
        
        .highlight {
            color: var(--neon-primary);
            font-weight: 600;
            text-shadow: 0 0 5px rgba(0, 243, 255, 0.5);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }
        
        .project-card {
            background: var(--glass);
            border-radius: 15px;
            overflow: hidden;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            position: relative;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 243, 255, 0.1), rgba(255, 0, 200, 0.1));
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5), 0 0 20px rgba(0, 243, 255, 0.2);
        }
        
        .project-card:hover::before {
            opacity: 1;
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
            position: relative;
            overflow: hidden;
        }
        
        .project-img::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: translateX(-100%);
        }
        
        .project-card:hover .project-img::after {
            transform: translateX(100%);
            transition: transform 0.6s ease;
        }
        
        .project-content {
            padding: 25px;
            position: relative;
            z-index: 1;
        }
        
        .project-title {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--text);
            font-weight: 600;
        }
        
        .project-description {
            color: var(--text-light);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }
        
        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            color: var(--neon-primary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--neon-primary);
            transform: translateX(-100%);
            transition: transform 0.3s ease;
        }
        
        .project-link:hover {
            gap: 12px;
            text-shadow: 0 0 8px var(--neon-primary);
        }
        
        .project-link:hover::after {
            transform: translateX(0);
        }
        
        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }
        
        .skill-category {
            background: var(--glass);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }
        
        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: linear-gradient(to bottom, var(--neon-primary), var(--neon-secondary));
        }
        
        .skill-category:hover {
            transform: translateY(-5px) translateX(5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3), 0 0 15px rgba(0, 243, 255, 0.2);
        }
        
        .skill-category h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--text);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .skill-category h3 i {
            color: var(--neon-primary);
            text-shadow: 0 0 8px var(--neon-primary);
        }
        
        .skill-list {
            list-style: none;
        }
        
        .skill-list li {
            padding: 10px 0;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-light);
            transition: color 0.3s ease;
            position: relative;
            padding-left: 20px;
        }
        
        .skill-list li::before {
            content: '▹';
            color: var(--neon-primary);
            position: absolute;
            left: 0;
            text-shadow: 0 0 5px var(--neon-primary);
        }
        
        .skill-list li:hover {
            color: var(--neon-primary);
            text-shadow: 0 0 5px rgba(0, 243, 255, 0.5);
        }
        
        /* SVG Wave Separator */
        .wave-separator {
            width: 100%;
            height: 150px;
            margin: 40px 0;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z' fill='%236C63FF' fill-opacity='0.1'%3E%3C/path%3E%3C/svg%3E");
            background-size: cover;
            background-position: center;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-light);
            font-size: 1rem;
            position: relative;
            overflow: hidden;
        }
        
        .footer::before {
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
        
        .footer-heart {
            color: var(--accent);
            animation: heartbeat 1.5s ease infinite;
            text-shadow: 0 0 10px rgba(255, 101, 132, 0.7);
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.2); }
            10% { transform: scale(1); }
            15% { transform: scale(1.3); }
            50% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .neon-text {
            color: var(--neon-primary);
            text-shadow: 0 0 10px var(--neon-primary);
            font-family: 'Orbitron', sans-serif;
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
            
            .skills-container {
                grid-template-columns: 1fr;
            }
            
            .profile-frame {
                width: 180px;
                height: 180px;
            }
        }
    </style>
</head>
<body>
    <!-- Loader -->
    <div class="loader">
        <div class="neon-loader"></div>
    </div>

    <!-- Theme Toggle -->
    <div class="theme-toggle">
        <label class="toggle-btn" for="theme-switch">
            <i class="fas fa-moon"></i>
            <span>Dark Mode</span>
        </label>
        <input type="checkbox" id="theme-switch" style="display: none;">
    </div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-frame">
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

        <!-- SVG Wave Separator -->
        <div class="wave-separator"></div>

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
            <p>Made with <span class="footer-heart">❤️</span> by <strong class="neon-text">Syed Saqueeb</strong></p>
        </footer>
    </div>

    <!-- CSS-only Theme Toggle and Loader -->
    <style>
        /* Theme toggle functionality */
        #theme-switch:checked ~ .container .toggle-btn .fa-moon::before {
            content: "\f185";
        }
        
        #theme-switch:checked ~ .container .toggle-btn span::after {
            content: "Light Mode";
        }
        
        #theme-switch:checked ~ .container {
            filter: none;
        }
        
        #theme-switch:checked ~ .container .header,
        #theme-switch:checked ~ .container .section,
        #theme-switch:checked ~ .container .footer {
            filter: none;
        }
        
        #theme-switch:checked ~ .container body {
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
        }
        
        /* Apply light theme when checkbox is checked */
        #theme-switch:checked ~ .container {
            --dark: #f0f0ff;
            --darker: #e0e0f0;
            --light: #0f0f1e;
            --text: #1a1a2e;
            --text-light: #4a4a6e;
            --glass: rgba(255, 255, 255, 0.7);
            --glass-border: rgba(255, 255, 255, 0.3);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        /* Loader animation */
        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }
        
        /* Simulate loader disappearing after page load */
        .loader {
            animation: fadeOut 0.5s ease 2s forwards;
        }
        
        /* Theme toggle button text change */
        .toggle-btn span::after {
            content: "Dark Mode";
        }
        
        #theme-switch:checked ~ .container .toggle-btn span::after {
            content: "Light Mode";
        }
    </style>
</body>
</html>
