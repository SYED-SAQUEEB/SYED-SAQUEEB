<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syed Saqueeb - Developer Profile</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* Custom styles and font application */
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom Keyframe for the subtle glow */
        @keyframes glow {
            0% { box-shadow: 0 0 5px #00eaff; }
            50% { box-shadow: 0 0 15px #00eaff, 0 0 20px #00eaff; }
            100% { box-shadow: 0 0 5px #00eaff; }
        }
        .glow-border {
            border: 1px solid theme('colors.primary.DEFAULT');
        }
        /* Optional: Apply the glow on a card hover */
        .project-card:hover {
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1), 0 0 20px rgba(0, 234, 255, 0.4);
        }
        /* Custom wave divider for modern look */
        .wave-divider path {
            fill: theme('colors.slate.800'); /* Matches the card background for depth */
        }
    </style>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: {
                            DEFAULT: '#00eaff', /* The bright accent color */
                        },
                        'slate-950': '#0d1117', /* Darker background, like GitHub */
                    },
                    boxShadow: {
                        'accent-sm': '0 0 5px rgba(0, 234, 255, 0.5)',
                        'accent-lg': '0 0 20px rgba(0, 234, 255, 0.8)',
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-slate-950 min-h-screen text-gray-100 p-4 md:p-8">

    <div class="max-w-4xl mx-auto py-10">

        <!-- Header -->
        <header class="text-center mb-12">
            <h1 class="text-5xl md:text-7xl font-extrabold leading-tight">
                👋 Hi, I'm 
                <span class="text-primary tracking-tighter shadow-accent-lg transition-all duration-300">
                    Syed Saqueeb
                </span>
            </h1>
            <p class="text-xl md:text-2xl text-gray-400 mt-2 font-medium">
                MERN Stack Developer • UI/UX Enthusiast
            </p>
        </header>

        <!-- Divider Wave SVG (Simplified/Stylized) -->
        <div class="mb-10">
            <svg class="wave-divider" viewBox="0 0 1440 120" width="100%" height="40">
                <path fill="#0f172a" d="M0,64L1440,0L1440,120L0,120Z"></path>
            </svg>
            <div class="h-1 bg-primary rounded-full shadow-accent-sm"></div>
        </div>

        <!-- About Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold mb-6 border-l-4 border-primary pl-4 text-primary">🚀 About Me</h2>
            <p class="text-lg text-gray-300 leading-relaxed bg-slate-900 p-6 rounded-xl shadow-inner border border-slate-800">
                I build fast, modern, mobile-first web apps with clean UI and smooth user experiences. 
                My focus is on building scalable MERN applications with high-quality front-end design, always prioritizing performance and developer ergonomics.
            </p>
        </section>

        <!-- Projects Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold mb-6 border-l-4 border-primary pl-4 text-primary">🌟 Featured Projects</h2>

            <!-- Project Card 1 -->
            <div class="project-card p-6 rounded-xl bg-slate-800 border border-slate-700 hover:border-primary transition-all duration-300 mb-4 shadow-xl">
                <h3 class="text-2xl font-semibold text-white mb-2">Genuine Hospital</h3>
                <p class="text-gray-400 mb-3">Responsive medical website with modern UI and accessibility considerations.</p>
                <a href="https://genuinehospital.netlify.app/" target="_blank" class="text-primary font-medium hover:text-white transition-colors duration-200 flex items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 20 20" fill="currentColor">
                        <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z" />
                        <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z" />
                    </svg>
                    View Live Project
                </a>
            </div>

            <!-- Project Card 2 -->
            <div class="project-card p-6 rounded-xl bg-slate-800 border border-slate-700 hover:border-primary transition-all duration-300 mb-4 shadow-xl">
                <h3 class="text-2xl font-semibold text-white mb-2">Almannan Decor</h3>
                <p class="text-gray-400 mb-3">Minimal, mobile-first decor website, focusing on clean product presentation and fast loading times.</p>
                <a href="https://almannandecor.netlify.app/" target="_blank" class="text-primary font-medium hover:text-white transition-colors duration-200 flex items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 20 20" fill="currentColor">
                        <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z" />
                        <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z" />
                    </svg>
                    View Live Project
                </a>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold mb-6 border-l-4 border-primary pl-4 text-primary">🛠 Tech Stack</h2>

            <div class="p-6 rounded-xl bg-slate-800 border border-slate-700 shadow-lg">
                <p class="text-lg text-gray-200 leading-snug">
                    <b class="text-primary block mb-1">Core MERN:</b> <span class="text-white">MongoDB • Express • React • Node.js</span> <br>
                    <b class="text-primary block mt-3 mb-1">Frontend Focus:</b> <span class="text-white">Tailwind CSS (Expert) • JavaScript (ES6+) • Modern Component Architectures</span> <br>
                    <b class="text-primary block mt-3 mb-1">Dev Tools:</b> <span class="text-white">Git/GitHub • VS Code • Chrome DevTools • Agile Methodologies</span>
                </p>
            </div>
        </section>

        <!-- Social Buttons -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold mb-6 border-l-4 border-primary pl-4 text-primary">📫 Connect With Me</h2>

            <div class="flex flex-wrap justify-center gap-4">

                <a href="https://github.com/saqueeb07" target="_blank"
                    class="transition duration-300 ease-in-out bg-primary text-slate-900 font-bold py-3 px-8 rounded-full shadow-lg hover:shadow-accent-sm hover:bg-white transform hover:scale-105">
                    GitHub
                </a>

                <a href="#" target="_blank"
                    class="transition duration-300 ease-in-out bg-primary text-slate-900 font-bold py-3 px-8 rounded-full shadow-lg hover:shadow-accent-sm hover:bg-white transform hover:scale-105">
                    LinkedIn
                </a>

                <a href="mailto:you@example.com"
                    class="transition duration-300 ease-in-out bg-primary text-slate-900 font-bold py-3 px-8 rounded-full shadow-lg hover:shadow-accent-sm hover:bg-white transform hover:scale-105">
                    Email
                </a>
            </div>
        </section>

        <!-- Footer -->
        <footer class="text-center mt-16 pt-8 border-t border-slate-800">
            <p class="text-sm text-gray-500">
                &copy; 2024 Syed Saqueeb. All Rights Reserved.
            </p>
            <p class="text-xs text-gray-600 mt-1">
                Made with <span class="text-red-500">❤️</span> by <b class="text-white">Syed Saqueeb</b>
            </p>
        </footer>

    </div>

</body>
</html>
