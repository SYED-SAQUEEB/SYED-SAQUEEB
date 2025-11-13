<!-- README.md - Next-gen Combined Design (Glassmorphism + Minimal + Futuristic + Dark + Compact) -->

<div align="center">

<!-- =========================
     Animated Neon SVG Header
     ========================= -->
<svg width="760" height="140" viewBox="0 0 760 140" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
  <defs>
    <linearGradient id="neonGrad" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0%" stop-color="#38BDF8"/>
      <stop offset="35%" stop-color="#7C3AED"/>
      <stop offset="65%" stop-color="#FB7185"/>
      <stop offset="100%" stop-color="#06B6D4"/>
    </linearGradient>
    <filter id="glow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="6" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <rect rx="14" width="760" height="140" fill="transparent" />
  <text x="50%" y="40%" text-anchor="middle" font-family="Fira Code, monospace" font-size="20" fill="#C7D2FE" opacity="0.7">Hi 👋 I'm</text>

  <text id="name" x="50%" y="75%" text-anchor="middle" font-family="Fira Code, monospace" font-weight="800" font-size="36" fill="url(#neonGrad)" filter="url(#glow)">
    SYED SAQUEEB
  </text>

  <!-- subtle animated underline -->
  <rect x="140" y="88" width="480" height="3" rx="2" fill="url(#neonGrad)">
    <animate attributeName="x" values="140;140;140" dur="6s" repeatCount="indefinite" />
    <animate attributeName="opacity" values="0.6;1;0.6" dur="3s" repeatCount="indefinite" />
  </rect>
</svg>

<!-- Typing SVG (externally hosted service) -->
<div style="margin-top:10px;">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=20&duration=3000&pause=900&color=38BDF8&center=true&vCenter=true&width=700&lines=Frontend+Developer;UI%2FUX+Enthusiast;Building+Modern+Web+Experiences;Continuous+Learner" alt="Typing SVG">
</div>

</div>

<!-- =======
   Styles
   ======= -->
<style>
/* Root: dark glass + compact */
:root{
  --bg: #0b1020;
  --card-bg: rgba(255,255,255,0.04);
  --glass-blur: 8px;
  --accent1: #38BDF8;
  --accent2: #7C3AED;
  --accent3: #FB7185;
  --glass-border: rgba(255,255,255,0.06);
  --muted: rgba(255,255,255,0.6);
  --compact-gap: 12px;
  --radius: 12px;
  font-family: 'Inter', 'Fira Code', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
}

/* Container */
body, html {
  background: var(--bg);
  color: #E6EEF8;
  -webkit-font-smoothing: antialiased;
  font-size: 14px;
}

/* Glass card base */
.glass {
  background: linear-gradient(135deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
  border: 1px solid var(--glass-border);
  backdrop-filter: blur(var(--glass-blur));
  -webkit-backdrop-filter: blur(var(--glass-blur));
  border-radius: var(--radius);
  padding: 16px;
  box-shadow: 0 6px 20px rgba(2,6,23,0.6);
}

/* Container for the top row of contact badges and social links */
.top-row {
  display:flex;
  gap:var(--compact-gap);
  justify-content:center;
  align-items:center;
  margin-top:18px;
  flex-wrap:wrap;
}

/* Compact, neon-styled badges */
.badge {
  display:inline-flex;
  align-items:center;
  gap:8px;
  padding:8px 12px;
  border-radius:999px;
  font-weight:600;
  font-size:13px;
  background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  border: 1px solid rgba(255,255,255,0.04);
  transition: transform .18s ease, box-shadow .18s ease;
}
.badge:hover{ transform: translateY(-4px) scale(1.02); box-shadow: 0 10px 30px rgba(124,58,237,0.12); }

/* Projects grid */
.projects {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap:14px;
  margin:18px auto;
  width:100%;
  max-width:1100px;
}

/* Project card specific */
.project {
  position:relative;
  overflow:hidden;
  padding:14px;
  display:flex;
  flex-direction:column;
  gap:10px;
  min-height:120px;
  transition: transform .22s ease, box-shadow .22s ease;
}
.project:hover{ transform: translateY(-8px); box-shadow: 0 18px 40px rgba(2,6,23,0.7); }

/* Neon ribbon accent */
.ribbon {
  position:absolute;
  right:-60px;
  top:12px;
  transform: rotate(30deg);
  padding:6px 110px;
  text-align:center;
  font-weight:700;
  font-size:12px;
  color:#050712;
  background: linear-gradient(90deg, var(--accent1), var(--accent2), var(--accent3));
  box-shadow: 0 6px 20px rgba(124,58,237,0.12);
  opacity:0.95;
}

/* Project title & description compact */
.project h3 { margin:0; font-size:16px; letter-spacing:0.2px; }
.project p { margin:0; color:var(--muted); font-size:13px; line-height:1.35; }

/* Links row - flat badges */
.links { display:flex; gap:8px; align-items:center; flex-wrap:wrap; margin-top:8px; }

/* Stats cards area */
.stats {
  display:flex;
  gap:12px;
  justify-content:center;
  margin:18px auto 10px;
  flex-wrap:wrap;
}

/* Visitor + signature */
.signature {
  text-align:center;
  color: #B6C7E8;
  margin-top:18px;
  font-style:italic;
  opacity:0.95;
  font-size:13px;
}

/* compact responsive adjustments */
@media (max-width:640px) {
  .ribbon { display:none; }
  .glass { padding:12px; border-radius:10px; }
}
</style>

---

# Overview
<div align="center" class="glass" style="max-width:1100px; margin:18px auto;">
  <div style="display:flex; gap:12px; align-items:center; justify-content:center; flex-wrap:wrap;">
    <div style="text-align:left; min-width:200px;">
      <h2 style="margin:0 0 6px 0; font-size:18px;">Syed Saqueeb</h2>
      <div style="color:var(--muted); font-size:13px; margin-bottom:6px;">Frontend Developer · UI/UX Enthusiast · React & Tailwind</div>
      <div style="display:flex; gap:8px; flex-wrap:wrap;">
        <a class="badge" href="https://www.linkedin.com/in/syed-saqueeb085/" target="_blank">LinkedIn<img src="https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin" alt="lnk" style="height:18px; border-radius:6px;"></a>
        <a class="badge" href="https://github.com/SYED-SAQUEEB" target="_blank">GitHub<img src="https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github" alt="gh" style="height:18px; border-radius:6px;"></a>
        <a class="badge" href="mailto:syedsaqueeb085@gmail.com">Email<img src="https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail" alt="mail" style="height:18px; border-radius:6px;"></a>
      </div>
    </div>

    <div style="margin-left:auto; display:flex; gap:8px; align-items:center;">
      <div style="text-align:right;">
        <div style="font-weight:700; font-size:14px;">Current Focus</div>
        <div style="color:var(--muted); font-size:13px; margin-top:4px;">Component architecture · Scalable UIs · TypeScript</div>
      </div>
    </div>
  </div>
</div>

---

# Featured Projects
<div class="projects" role="list">
  <!-- Project 1 -->
  <div class="glass project" role="listitem">
    <div class="ribbon">Live</div>
    <h3>🏥 Genuine Hospital Website</h3>
    <p class="project-description">A fully responsive, mobile-first hospital site built with semantic HTML, Tailwind, and accessible UI patterns.</p>
    <div class="links">
      <a href="https://genuinehospital.netlify.app/" target="_blank"><img src="https://img.shields.io/badge/Live_Demo-4facfe?style=flat-square&logo=netlify" alt="live"></a>
      <a href="https://github.com/SYED-SAQUEEB" target="_blank"><img src="https://img.shields.io/badge/View_Code-181717?style=flat-square&logo=github" alt="code"></a>
    </div>
  </div>

  <!-- Project 2 -->
  <div class="glass project" role="listitem">
    <div class="ribbon" style="background:linear-gradient(90deg,#43e97b,#38f9d7);">Case Study</div>
    <h3>🏠 Almannan Decor Website</h3>
    <p class="project-description">User-focused UI for decor services with clean layouts and image-first presentation.</p>
    <div class="links">
      <a href="https://almannandecor.netlify.app/" target="_blank"><img src="https://img.shields.io/badge/Live_Demo-4facfe?style=flat-square&logo=netlify" alt="live"></a>
      <a href="https://github.com/SYED-SAQUEEB" target="_blank"><img src="https://img.shields.io/badge/View_Code-181717?style=flat-square&logo=github" alt="code"></a>
    </div>
  </div>

  <!-- Project 3 -->
  <div class="glass project" role="listitem">
    <div class="ribbon" style="background:linear-gradient(90deg,#f093fb,#f5576c);">Edu</div>
    <h3>🎓 AIT Academy Website</h3>
    <p class="project-description">Educational portal with interactive modules, accessible markup, and progressive enhancement.</p>
    <div class="links">
      <a href="https://aitaurangabad.com/" target="_blank"><img src="https://img.shields.io/badge/Live_Project-4facfe?style=flat-square&logo=netlify" alt="live"></a>
      <a href="https://github.com/SYED-SAQUEEB" target="_blank"><img src="https://img.shields.io/badge/View_Code-181717?style=flat-square&logo=github" alt="code"></a>
    </div>
  </div>

  <!-- Project 4 -->
  <div class="glass project" role="listitem">
    <div class="ribbon" style="background:linear-gradient(90deg,#667eea,#764ba2);">Brand</div>
    <h3>🌸 A Perfume Website</h3>
    <p class="project-description">Elegant brand-aligned e-commerce UI showcasing product detail flows and responsive grids.</p>
    <div class="links">
      <a href="https://aperfume.netlify.app/" target="_blank"><img src="https://img.shields.io/badge/Live_Demo-4facfe?style=flat-square&logo=netlify" alt="live"></a>
      <a href="https://github.com/SYED-SAQUEEB" target="_blank"><img src="https://img.shields.io/badge/View_Code-181717?style=flat-square&logo=github" alt="code"></a>
    </div>
  </div>
</div>

---

# GitHub Metrics & Quick Stats
<div class="stats" role="region" aria-label="GitHub statistics">
  <div class="glass" style="padding:10px 12px; display:flex; align-items:center; gap:10px;">
    <img src="https://github-readme-stats.vercel.app/api?username=SYED-SAQUEEB&show_icons=true&theme=gotham&include_all_commits=true&count_private=true&hide_border=true" alt="github stats" style="height:72px;">
  </div>

  <div class="glass" style="padding:10px 12px; display:flex; align-items:center; gap:10px;">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=SYED-SAQUEEB&layout=compact&langs_count=7&theme=gotham&hide_border=true" alt="top langs" style="height:72px;">
  </div>

  <div class="glass" style="padding:10px 12px; display:flex; align-items:center; gap:10px;">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=SYED-SAQUEEB&theme=gotham&hide_border=true" alt="streak" style="height:72px;">
  </div>
</div>

---

# Contact & Quick Links
<div align="center" class="top-row" role="navigation" aria-label="contact links">
  <a class="badge" href="https://github.com/SYED-SAQUEEB">GitHub</a>
  <a class="badge" href="https://www.linkedin.com/in/syed-saqueeb085/">LinkedIn</a>
  <a class="badge" href="mailto:syedsaqueeb085@gmail.com">Email</a>
  <a class="badge" href="https://genuinehospital.netlify.app/" target="_blank">Genuine Hospital (Live)</a>
  <a class="badge" href="https://almannandecor.netlify.app/" target="_blank">Almannan Decor (Live)</a>
</div>

---

<div class="signature">
  &lt;/&gt; With passion and precision. · <span style="color:var(--muted)">Syed Saqueeb</span>
</div>

