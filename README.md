<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syed Saqueeb - Full Stack Web Developer Portfolio</title>
    <!-- Poppins Font from Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- Bootstrap 5 CDN -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

    <style>
        /* ====================================
           CSS Variables & Global Styles (Dark Mode Default: Navy/Gold)
           ==================================== */
        :root {
            /* Dark Theme Colors */
            --bg-dark: #121212; /* True Dark */
            --text-dark: #e0e0e0; /* Off-White Text */
            --card-bg-dark: #1e1e1e; /* Card Background */
            --primary-accent: #FFD700; /* Gold */
            --secondary-accent: #1E3A8A; /* Deep Navy */
            --border-color: rgba(255, 255, 255, 0.08); /* Subtle Dark Border */

            /* Light Theme Colors */
            --bg-light: #F8F9FA; /* Soft Light Gray */
            --text-light: #212529; /* Dark Text */
            --card-bg-light: #FFFFFF; /* White Card */

            /* General Theme Application */
            --main-bg: var(--bg-dark);
            --main-text: var(--text-dark);
            --card-bg: var(--card-bg-dark);
        }

        /* Light Mode Overrides */
        body.light-mode {
            --main-bg: var(--bg-light);
            --main-text: var(--text-light);
            --card-bg: var(--card-bg-light);
            --border-color: rgba(0, 0, 0, 0.1);
            --primary-accent: #1E3A8A; /* Navy Accent in Light Mode */
            --secondary-accent: #FFD700; /* Gold Accent in Light Mode */
        }

        /* Apply variables to body and main elements */
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--main-bg);
            color: var(--main-text);
            transition: background-color 0.5s, color 0.5s;
            scroll-behavior: smooth;
        }

        /* Typography and Headings */
        h1, h2, h3, h4 {
            font-weight: 700;
        }
        h2 {
            color: var(--primary-accent);
            padding-bottom: 10px;
            margin-bottom: 30px;
            border-bottom: 2px solid var(--border-color);
            display: inline-block;
        }

        /* Card Styling */
        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: background-color 0.5s, border-color 0.5s, transform 0.3s, box-shadow 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        .light-mode .card:hover {
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.08);
        }

        /* Custom Button Accent (Primary: Gold in Dark, Navy in Light) */
        .btn-accent {
            background-color: var(--primary-accent);
            border: 2px solid var(--primary-accent);
            color: var(--bg-dark); /* Dark text on bright/accent button */
            font-weight: 600;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        .btn-accent:hover {
            background-color: transparent;
            color: var(--primary-accent);
            border-color: var(--primary-accent);
        }
        /* Secondary Outline Button */
        .btn-secondary-outline {
            color: var(--secondary-accent);
            border: 2px solid var(--secondary-accent);
            background-color: transparent;
            font-weight: 600;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        .btn-secondary-outline:hover {
            background-color: var(--secondary-accent);
            color: var(--bg-light); /* Light text on secondary hover */
            border-color: var(--secondary-accent);
        }

        /* Text Utilities */
        .text-primary-accent { color: var(--primary-accent) !important; }
        .text-secondary-accent { color: var(--secondary-accent) !important; }

        /* ====================================
           Navigation and Hero
           ==================================== */
        .navbar {
            background-color: var(--bg-dark);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }
        .light-mode .navbar {
            background-color: var(--card-bg-light);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }
        .nav-link {
            color: var(--main-text) !important;
            transition: color 0.3s;
        }
        .nav-link:hover, .nav-link.active {
            color: var(--primary-accent) !important;
        }
        /* Hero Styling */
        #hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            padding-top: 56px;
        }
        /* Fade-in animation definitions remain the same */
        #hero h1, #hero .lead, #hero .btn { opacity: 0; }
        #hero h1 { animation: hero-fade-in 1s forwards; animation-delay: 0.5s; }
        #hero .lead { animation: hero-fade-in 1s forwards; animation-delay: 1s; }
        #hero .btn { animation: hero-fade-in 1s forwards; animation-delay: 1.5s; }
        @keyframes hero-fade-in {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .scroll-down {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--primary-accent);
            animation: bounce 2s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        /* ====================================
           Animations (AOS-like)
           ==================================== */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .fade-in-up.animate {
            opacity: 1;
            transform: translateY(0);
        }

        /* Experience Timeline */
        .timeline-item {
            position: relative;
            padding-left: 40px;
            margin-bottom: 50px;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 2px;
            height: 100%;
            background-color: var(--border-color);
        }
        .timeline-item-icon {
            position: absolute;
            top: 0;
            left: -8px;
            width: 18px;
            height: 18px;
            background-color: var(--primary-accent);
            border-radius: 50%;
            z-index: 10;
        }

        /* Theme Toggle Button */
        #theme-toggle {
            cursor: pointer;
            margin-left: 1rem;
            border: none;
            background: none;
            color: var(--primary-accent);
            font-size: 1.25rem;
            transition: color 0.3s;
        }
        #theme-toggle:hover {
            color: var(--secondary-accent);
        }

        /* Scroll to Top Button */
        #scroll-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            display: none;
            z-index: 1000;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background-color: var(--primary-accent);
            color: var(--bg-dark);
            border: none;
            opacity: 0.9;
            transition: opacity 0.3s, background-color 0.3s;
        }
        #scroll-to-top:hover {
            opacity: 1;
        }
    </style>
</head>

<body data-bs-spy="scroll" data-bs-target="#main-nav" data-bs-offset="50">

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg sticky-top" id="main-nav">
        <div class="container">
            <a class="navbar-brand text-primary-accent fw-bold" href="#hero">Syed Saqueeb</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"><i class="fas fa-bars text-primary-accent"></i></span>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item"><a class="nav-link active" href="#hero">Home</a></li>
                    <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
                    <li class="nav-item"><a class="nav-link" href="#skills">Skills</a></li>
                    <li class="nav-item"><a class="nav-link" href="#experience">Experience</a></li>
                    <li class="nav-item"><a class="nav-link" href="#projects">Projects</a></li>
                    <li class="nav-item"><a class="nav-link" href="#achievements">Achievements</a></li>
                    <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
                </ul>
                <button id="theme-toggle" title="Toggle theme">
                    <i class="fas fa-sun" id="theme-icon"></i>
                </button>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main>
        <!-- 1. Hero / Intro Section -->
        <section id="hero" class="d-flex align-items-center">
            <div class="container py-5">
                <div class="row justify-content-center">
                    <div class="col-lg-10 text-center">
                        <h1 class="display-3 fw-bold mb-3">
                            Hello, I'm <span class="text-primary-accent">Syed Saqueeb</span>.
                        </h1>
                        <p class="lead text-secondary-accent fs-4 mb-4">
                            Full Stack Web Developer | ASP.NET & MERN Stack Enthusiast
                        </p>
                        <p class="mb-5 mx-auto" style="max-width: 600px;">
                            Passionate and detail-oriented Full Stack Web Developer with experience in building dynamic, user-focused web applications using C#, ASP.NET, MVC, SQL Server, and the MERN stack. Skilled in both frontend and backend technologies, database integration, and responsive design.
                        </p>
                        <div class="d-grid gap-3 d-sm-flex justify-content-sm-center">
                            <a href="#" class="btn btn-accent btn-lg px-4 me-sm-3" role="button">
                                <i class="fas fa-file-alt me-2"></i> View Resume
                            </a>
                            <a href="https://github.com/SYED-SAQUEEB" class="btn btn-secondary-outline btn-lg px-4 me-sm-3" target="_blank" role="button">
                                <i class="fab fa-github me-2"></i> GitHub Profile
                            </a>
                            <a href="https://linkedin.com/in/syed-saqueeb085" class="btn btn-secondary-outline btn-lg px-4" target="_blank" role="button">
                                <i class="fab fa-linkedin me-2"></i> LinkedIn Profile
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Scroll Down Indicator -->
            <a href="#about" class="scroll-down position-absolute bottom-0 text-decoration-none p-3">
                <i class="fas fa-chevron-down fa-2x"></i>
            </a>
        </section>

        <!-- 2. About / Professional Summary -->
        <section id="about" class="py-5">
            <div class="container py-5">
                <h2 class="fade-in-up">About Me</h2>
                <div class="row fade-in-up">
                    <div class="col-12">
                        <p class="fs-5">
                            Passionate and detail-oriented Full Stack Web Developer with 6 months of hands-on experience in building dynamic, user-focused web applications using **C#, ASP.NET, MVC, SQL Server**, and the **MERN stack** (MongoDB, Express.js, React.js, Node.js).
                        </p>
                        <p class="fs-5">
                            Skilled in both front-end and back-end development, database integration, and responsive UI/UX design.
                        </p>
                        <p class="fs-5">
                            Enthusiastic about modern technologies, AI-assisted tools, and automation. Eager to contribute to fast-paced development teams to deliver scalable, real-world solutions.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. Skills Section -->
        <section id="skills" class="py-5" style="background-color: var(--card-bg);">
            <div class="container py-5">
                <h2 class="fade-in-up">Technical Skills</h2>
                <div class="row fade-in-up">
                    <!-- Skills Group 1: Languages & Frameworks -->
                    <div class="col-md-6 mb-4">
                        <h4 class="text-primary-accent mb-3"><i class="fas fa-code me-2"></i>Languages & Frameworks</h4>
                        <ul class="list-group list-group-flush">
                            <li class="list-group-item d-flex justify-content-between align-items-center" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                Java, C#, JavaScript, HTML5, CSS3
                            </li>
                            <li class="list-group-item d-flex justify-content-between align-items-center" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                ASP.NET (Core & MVC), MERN Stack (React, Node, Express), Bootstrap
                            </li>
                        </ul>
                    </div>

                    <!-- Skills Group 2: Databases & Tools -->
                    <div class="col-md-6 mb-4">
                        <h4 class="text-primary-accent mb-3"><i class="fas fa-tools me-2"></i>Databases & Tools</h4>
                        <ul class="list-group list-group-flush">
                            <li class="list-group-item d-flex justify-content-between align-items-center" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                SQL Server, ADO.NET, MongoDB
                            </li>
                            <li class="list-group-item d-flex justify-content-between align-items-center" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                Visual Studio, VS Code, Git, GitHub
                            </li>
                        </ul>
                    </div>
                </div>

                <div class="row mt-4 fade-in-up">
                    <!-- Skills Group 3: Concepts & Soft Skills -->
                    <div class="col-12">
                        <h4 class="text-primary-accent mb-3"><i class="fas fa-brain me-2"></i>Concepts & Soft Skills</h4>
                        <div class="d-flex flex-wrap gap-2">
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">OOP</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">Responsive Design</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">CRUD Operations</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">DBMS</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">RESTful APIs</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">Communication</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">Collaboration</span>
                            <span class="badge rounded-pill p-3" style="background-color: var(--secondary-accent); color: var(--bg-light);">Problem-Solving</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. Experience Section -->
        <section id="experience" class="py-5">
            <div class="container py-5">
                <h2 class="fade-in-up">Professional Experience</h2>
                <div class="row fade-in-up">
                    <div class="col-lg-8 mx-auto">
                        <div class="timeline-item">
                            <span class="timeline-item-icon"></span>
                            <div class="card p-4">
                                <h4 class="card-title text-primary-accent fw-bold">Full Stack Developer Intern</h4>
                                <h5 class="card-subtitle mb-2" style="color: var(--main-text);">Wainfo Technologies</h5>
                                <p class="mb-3" style="color: var(--secondary-accent);"><i class="far fa-calendar-alt me-2"></i>May 2025 – Present</p>
                                <ul class="list-unstyled mb-0">
                                    <li class="mb-2"><i class="fas fa-check-circle me-2 text-primary-accent"></i>Developed and maintained full-stack web applications using **ASP.NET** and **MERN stack**.</li>
                                    <li class="mb-2"><i class="fas fa-check-circle me-2 text-primary-accent"></i>Designed responsive, user-friendly interfaces with HTML, CSS, Bootstrap, and JS.</li>
                                    <li class="mb-2"><i class="fas fa-check-circle me-2 text-primary-accent"></i>Built and integrated **RESTful APIs** for seamless frontend-backend communication.</li>
                                    <li class="mb-2"><i class="fas fa-check-circle me-2 text-primary-accent"></i>Collaborated in agile sprints and participated in code reviews.</li>
                                    <li class="mb-0"><i class="fas fa-check-circle me-2 text-primary-accent"></i>Ensured high-performance, secure, and maintainable code.</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. Projects Showcase -->
        <section id="projects" class="py-5" style="background-color: var(--card-bg);">
            <div class="container py-5">
                <h2 class="fade-in-up">Projects Showcase</h2>
                <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">

                    <!-- Project Card 1: Genuine Hospital -->
                    <div class="col fade-in-up" style="--delay: 0.1s;">
                        <div class="card h-100">
                            <img src="https://placehold.co/600x400/1E3A8A/FFD700?text=Genuine+Hospital" class="card-img-top" alt="Genuine Hospital Placeholder" style="border-radius: 12px 12px 0 0;">
                            <div class="card-body">
                                <h5 class="card-title fw-bold" style="color: var(--secondary-accent);">Genuine Hospital</h5>
                                <p class="card-text" style="color: var(--main-text);">Responsive hospital website built using HTML5, Tailwind CSS, Bootstrap, and JavaScript. Modern UI, smooth animations, and optimized layouts.</p>
                                <div class="d-flex flex-wrap gap-2 mb-3">
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">HTML5</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">Bootstrap</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">JS</span>
                                </div>
                                <div class="d-grid gap-2 d-md-flex justify-content-md-start">
                                    <a href="#" class="btn btn-accent btn-sm" role="button"><i class="fas fa-external-link-alt me-1"></i> Live Demo</a>
                                    <a href="#" class="btn btn-secondary-outline btn-sm" role="button"><i class="fab fa-github me-1"></i> View Code</a>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Project Card 2: Almannan Decor -->
                    <div class="col fade-in-up" style="--delay: 0.2s;">
                        <div class="card h-100">
                            <img src="https://placehold.co/600x400/1E3A8A/FFD700?text=Almannan+Decor" class="card-img-top" alt="Almannan Decor Placeholder" style="border-radius: 12px 12px 0 0;">
                            <div class="card-body">
                                <h5 class="card-title fw-bold" style="color: var(--secondary-accent);">Almannan Decor</h5>
                                <p class="card-text" style="color: var(--main-text);">Responsive, user-friendly decor website with Tailwind and Bootstrap. Enhanced interactivity with dynamic JS components.</p>
                                <div class="d-flex flex-wrap gap-2 mb-3">
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">Tailwind</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">Bootstrap</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">JS</span>
                                </div>
                                <div class="d-grid gap-2 d-md-flex justify-content-md-start">
                                    <a href="#" class="btn btn-accent btn-sm" role="button"><i class="fas fa-external-link-alt me-1"></i> Live Demo</a>
                                    <a href="#" class="btn btn-secondary-outline btn-sm" role="button"><i class="fab fa-github me-1"></i> View Code</a>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Project Card 3: AIT Academy Website -->
                    <div class="col fade-in-up" style="--delay: 0.3s;">
                        <div class="card h-100">
                            <img src="https://placehold.co/600x400/1E3A8A/FFD700?text=AIT+Academy" class="card-img-top" alt="AIT Academy Placeholder" style="border-radius: 12px 12px 0 0;">
                            <div class="card-body">
                                <h5 class="card-title fw-bold" style="color: var(--secondary-accent);">AIT Academy Website</h5>
                                <p class="card-text" style="color: var(--main-text);">Educational portal designed with HTML5, Bootstrap, and JavaScript. Interactive and responsive for all devices.</p>
                                <div class="d-flex flex-wrap gap-2 mb-3">
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">HTML5</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">Bootstrap</span>
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">JS</span>
                                </div>
                                <div class="d-grid gap-2 d-md-flex justify-content-md-start">
                                    <a href="#" class="btn btn-accent btn-sm" role="button"><i class="fas fa-external-link-alt me-1"></i> Live Demo</a>
                                    <a href="#" class="btn btn-secondary-outline btn-sm" role="button"><i class="fab fa-github me-1"></i> View Code</a>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Project Card 4: A Perfume Website (Under Development) -->
                    <div class="col fade-in-up" style="--delay: 0.4s;">
                        <div class="card h-100">
                            <img src="https://placehold.co/600x400/1E3A8A/FFD700?text=Perfume+Website" class="card-img-top" alt="Perfume Website Placeholder" style="border-radius: 12px 12px 0 0;">
                            <div class="card-body">
                                <h5 class="card-title fw-bold" style="color: var(--secondary-accent);">A Perfume Website <span class="badge p-2" style="background-color: var(--secondary-accent); color: var(--bg-light);">WIP</span></h5>
                                <p class="card-text" style="color: var(--main-text);">Elegant brand website built with modern UI techniques. Currently under development.</p>
                                <div class="d-flex flex-wrap gap-2 mb-3">
                                    <span class="badge p-2" style="background-color: var(--primary-accent); color: var(--bg-dark);">Modern UI</span>
                                </div>
                                <div class="d-grid gap-2 d-md-flex justify-content-md-start">
                                    <a href="#" class="btn btn-accent btn-sm disabled" role="button"><i class="fas fa-external-link-alt me-1"></i> Live Demo</a>
                                    <a href="#" class="btn btn-secondary-outline btn-sm disabled" role="button"><i class="fab fa-github me-1"></i> View Code</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 6. Achievements Section -->
        <section id="achievements" class="py-5">
            <div class="container py-5">
                <h2 class="fade-in-up">Key Achievements</h2>
                <div class="row fade-in-up">
                    <div class="col-lg-8 mx-auto">
                        <ul class="list-group list-group-flush shadow">
                            <li class="list-group-item d-flex align-items-center card-bg py-3 px-4 rounded-3 mb-2" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                <i class="fas fa-certificate fa-lg me-3 text-primary-accent"></i>
                                Completed **.NET Web Development Internship** at Wainfo Technologies
                            </li>
                            <li class="list-group-item d-flex align-items-center card-bg py-3 px-4 rounded-3 mb-2" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                <i class="fas fa-laptop-code fa-lg me-3 text-primary-accent"></i>
                                Built and deployed live **full-stack projects** (ASP.NET & MERN)
                            </li>
                            <li class="list-group-item d-flex align-items-center card-bg py-3 px-4 rounded-3 mb-2" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                <i class="fab fa-github fa-lg me-3 text-primary-accent"></i>
                                Active **GitHub contributor** with strong project documentation
                            </li>
                            <li class="list-group-item d-flex align-items-center card-bg py-3 px-4 rounded-3" style="background-color: var(--card-bg); border-color: var(--border-color);">
                                <i class="fas fa-robot fa-lg me-3 text-primary-accent"></i>
                                Developed **AI-based layout builder** (“AI Prompter Web Builder”)
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- 7. Contact Section -->
        <section id="contact" class="py-5" style="background-color: var(--card-bg);">
            <div class="container py-5">
                <h2 class="fade-in-up">Get In Touch</h2>
                <div class="row fade-in-up">
                    <div class="col-lg-4 mb-4 mb-lg-0">
                        <h4 class="text-primary-accent mb-3">Contact Details</h4>
                        <ul class="list-unstyled">
                            <li class="mb-3">
                                <i class="fas fa-envelope me-3 text-secondary-accent"></i>
                                syedsaqueeb085@gmail.com
                            </li>
                            <li class="mb-3">
                                <i class="fab fa-github me-3 text-secondary-accent"></i>
                                <a href="https://github.com/SYED-SAQUEEB" target="_blank" class="text-decoration-none" style="color: var(--main-text);">
                                    github.com/SYED-SAQUEEB
                                </a>
                            </li>
                            <li class="mb-3">
                                <i class="fab fa-linkedin me-3 text-secondary-accent"></i>
                                <a href="https://linkedin.com/in/syed-saqueeb085" target="_blank" class="text-decoration-none" style="color: var(--main-text);">
                                    linkedin.com/in/syed-saqueeb085
                                </a>
                            </li>
                        </ul>
                    </div>

                    <div class="col-lg-8">
                        <h4 class="text-primary-accent mb-3">Send a Message</h4>
                        <form id="contact-form">
                            <div class="row">
                                <div class="col-md-6 mb-3">
                                    <input type="text" class="form-control" id="name" placeholder="Your Name" required>
                                    <div class="invalid-feedback">Please enter your name.</div>
                                </div>
                                <div class="col-md-6 mb-3">
                                    <input type="email" class="form-control" id="email" placeholder="Your Email" required>
                                    <div class="invalid-feedback">Please enter a valid email address.</div>
                                </div>
                            </div>
                            <div class="mb-3">
                                <textarea class="form-control" id="message" rows="5" placeholder="Your Message" required></textarea>
                                <div class="invalid-feedback">Please enter a message.</div>
                            </div>
                            <div class="d-grid">
                                <button type="submit" class="btn btn-accent btn-lg" id="submit-button">
                                    <i class="fas fa-paper-plane me-2"></i> Send Message
                                </button>
                            </div>
                            <!-- Custom Message Box for Success/Error -->
                            <div id="form-message" class="mt-3 p-3 rounded-3 text-center d-none"></div>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- 8. Footer -->
    <footer class="py-4 border-top" style="border-color: var(--border-color) !important;">
        <div class="container text-center" style="color: var(--main-text);">
            <p class="mb-0 fs-6">&copy; 2025 Syed Saqueeb | Built with <span style="color: var(--primary-accent);"><i class="fas fa-heart"></i></span> using HTML, CSS, JS, and Bootstrap</p>
        </div>
    </footer>

    <!-- Scroll to Top Button -->
    <button id="scroll-to-top" title="Go to top"><i class="fas fa-chevron-up"></i></button>

    <!-- Bootstrap 5 JS Bundle -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

    <script>
        // ====================================
        // JavaScript Functions
        // ====================================

        document.addEventListener('DOMContentLoaded', () => {
            const body = document.body;
            const themeToggle = document.getElementById('theme-toggle');
            const themeIcon = document.getElementById('theme-icon');
            const sections = document.querySelectorAll('.fade-in-up');
            const scrollToTopButton = document.getElementById('scroll-to-top');
            const contactForm = document.getElementById('contact-form');
            const formMessage = document.getElementById('form-message');

            // --- Theme Toggle ---
            const currentTheme = localStorage.getItem('theme') || 'dark';

            // Function to apply the theme
            function applyTheme(theme) {
                if (theme === 'light') {
                    body.classList.add('light-mode');
                    themeIcon.classList.remove('fa-sun');
                    themeIcon.classList.add('fa-moon');
                } else {
                    body.classList.remove('light-mode');
                    themeIcon.classList.remove('fa-moon');
                    themeIcon.classList.add('fa-sun');
                }
            }

            // Apply initial theme
            applyTheme(currentTheme);

            themeToggle.addEventListener('click', () => {
                const isLight = body.classList.contains('light-mode');
                const newTheme = isLight ? 'dark' : 'light';

                localStorage.setItem('theme', newTheme);
                applyTheme(newTheme);
            });

            // --- Scroll Fade-In Animation (Intersection Observer) ---
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate');
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            sections.forEach(section => {
                observer.observe(section);
            });

            // --- Scroll to Top Button Visibility ---
            window.onscroll = function() { scrollFunction() };

            function scrollFunction() {
                if (document.body.scrollTop > 200 || document.documentElement.scrollTop > 200) {
                    scrollToTopButton.style.display = "block";
                } else {
                    scrollToTopButton.style.display = "none";
                }
            }

            scrollToTopButton.addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // --- Contact Form Validation and Submission ---
            contactForm.addEventListener('submit', function(event) {
                event.preventDefault();
                event.stopPropagation();

                const nameInput = document.getElementById('name');
                const emailInput = document.getElementById('email');
                const messageInput = document.getElementById('message');
                let valid = true;

                // Simple client-side validation
                if (nameInput.value.trim() === "") {
                    nameInput.classList.add('is-invalid');
                    valid = false;
                } else {
                    nameInput.classList.remove('is-invalid');
                }

                if (!validateEmail(emailInput.value)) {
                    emailInput.classList.add('is-invalid');
                    valid = false;
                } else {
                    emailInput.classList.remove('is-invalid');
                }

                if (messageInput.value.trim() === "") {
                    messageInput.classList.add('is-invalid');
                    valid = false;
                } else {
                    messageInput.classList.remove('is-invalid');
                }

                if (valid) {
                    // Simulate form submission success
                    const nameVal = nameInput.value.trim();
                    const message = `Thank you, ${nameVal.split(' ')[0]}! Your message has been received. I will be in touch shortly.`;

                    formMessage.textContent = message;
                    formMessage.style.backgroundColor = 'var(--secondary-accent)';
                    formMessage.style.color = 'var(--bg-light)';
                    formMessage.classList.remove('d-none');
                    formMessage.classList.add('d-block');

                    // Clear the form
                    contactForm.reset();
                    // Remove is-invalid classes
                    [nameInput, emailInput, messageInput].forEach(el => el.classList.remove('is-invalid'));

                    // Hide message after 5 seconds
                    setTimeout(() => {
                        formMessage.classList.add('d-none');
                    }, 5000);

                } else {
                    // Display error message
                    formMessage.textContent = 'Please correct the errors in the form before submitting.';
                    formMessage.style.backgroundColor = '#dc3545';
                    formMessage.style.color = '#fff';
                    formMessage.classList.remove('d-none');
                    formMessage.classList.add('d-block');
                }
            });

            function validateEmail(email) {
                // Regex for basic email format validation
                const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                return re.test(String(email).toLowerCase());
            }
        });
    </script>
</body>
</html>
