<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Syed Saqueeb — MERN & UI/UX</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">

  <style>
    /* ========== Variables for themes ========== */
    :root{
      --bg: #060608;
      --card: rgba(255,255,255,0.04);
      --glass-border: rgba(255,255,255,0.06);
      --muted: rgba(255,255,255,0.65);
      --accent: #00eaff;
      --accent-2:#7d00ff;
      --neon-glow: 0 4px 22px rgba(0,230,255,0.12), 0 0 20px rgba(0,230,255,0.12);
      --glass-blur: 8px;
      --glass-shadow: 0 6px 18px rgba(0,0,0,0.6);
    }
    :root.light {
      --bg: linear-gradient(180deg,#f4f7fb,#eaf1ff);
      --card: rgba(255,255,255,0.65);
      --glass-border: rgba(255,255,255,0.9);
      --muted: rgba(32,41,58,0.75);
      --accent: #0b63ff;
      --accent-2:#ff0066;
      --neon-glow: 0 8px 40px rgba(11,99,255,0.08);
      --glass-blur: 10px;
      --glass-shadow: 0 10px 30px rgba(14,30,80,0.08);
    }

    /* ========== Base styles ========== */
    * { box-sizing: border-box; }
    html,body { height:100%; }
    body{
      margin:0;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: var(--bg);
      color: white;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      transition: background 350ms ease, color 350ms ease;
      overflow-x:hidden;
    }

    /* Container */
    .wrap{
      max-width:1100px;
      margin:40px auto;
      padding:28px;
      position:relative;
    }

    /* Header */
    header {
      display:flex;
      align-items:center;
      gap:20px;
      justify-content:space-between;
      margin-bottom:20px;
    }
    .left {
      display:flex;
      gap:18px;
      align-items:center;
    }

    /* Profile frame - animated neon ring */
    .avatar-wrap{
      width:106px;
      height:106px;
      border-radius:50%;
      display:grid;
      place-items:center;
      position:relative;
      padding:6px;
      background: linear-gradient(135deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid var(--glass-border);
      backdrop-filter: blur(var(--glass-blur));
      box-shadow: var(--glass-shadow);
      overflow:visible;
    }

    .avatar {
      width:88px;
      height:88px;
      border-radius:50%;
      overflow:hidden;
      display:block;
      border: 3px solid rgba(255,255,255,0.06);
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.06));
      transition: transform .45s ease;
    }
    .avatar img { width:100%; height:100%; object-fit:cover; display:block; }

    /* neon animated ring */
    .neon-ring {
      position:absolute;
      left:50%;
      top:50%;
      transform:translate(-50%,-50%);
      width:118px;
      height:118px;
      border-radius:50%;
      pointer-events:none;
      filter: blur(6px);
      opacity:0.95;
      animation: spin 8s linear infinite;
      mix-blend-mode:screen;
      background:
        radial-gradient(circle at 20% 20%, rgba(0,255,217,0.35), transparent 10%),
        conic-gradient(from 120deg, rgba(0,255,217,0.45), rgba(125,0,255,0.35), rgba(0,255,217,0.25), rgba(125,0,255,0.25));
    }

    @keyframes spin { to { transform: translate(-50%,-50%) rotate(360deg); } }

    .avatar-wrap:hover .avatar { transform: scale(1.04); }

    /* Title */
    .title {
      line-height:1;
    }
    .title h1 { margin:0; font-size:20px; letter-spacing:0.2px; text-shadow: 0 4px 18px rgba(0,0,0,0.6); }
    .title p { margin:6px 0 0; color:var(--muted); font-size:13px; }

    /* Controls */
    .controls { display:flex; gap:10px; align-items:center; }
    .btn {
      background: linear-gradient(90deg,var(--accent),var(--accent-2));
      color:#081124;
      padding:8px 12px;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      border:none;
      box-shadow: var(--neon-glow);
      transition: transform .18s ease, box-shadow .18s ease, opacity .18s;
    }
    .btn:active{ transform: translateY(1px) scale(.995); }
    .icon-btn{
      width:44px; height:44px; display:grid; place-items:center; background:transparent; border-radius:9px;
      border:1px solid rgba(255,255,255,0.04); cursor:pointer;
    }

    /* ========== Grid of cards ========== */
    .grid {
      display:grid;
      grid-template-columns: repeat(3,1fr);
      gap:18px;
      margin-top:28px;
      align-items:start;
    }
    @media (max-width:980px){ .grid{ grid-template-columns: repeat(2,1fr);} }
    @media (max-width:620px){ .grid{ grid-template-columns: 1fr; } header{flex-direction:column;align-items:flex-start} .controls{margin-top:12px} }

    /* Glass cards */
    .card {
      background: var(--card);
      border-radius:14px;
      padding:18px;
      border: 1px solid var(--glass-border);
      box-shadow: var(--glass-shadow);
      backdrop-filter: blur(var(--glass-blur));
      transition: transform .28s cubic-bezier(.2,.9,.2,1), box-shadow .28s ease, border-color .28s;
      position:relative;
      overflow:hidden;
    }
    .card:hover { transform: translateY(-8px) scale(1.01); border-color: rgba(255,255,255,0.12); }

    .card h3 { margin:0 0 8px 0; color:var(--accent); letter-spacing:0.4px; }
    .card p { margin:0; color:var(--muted); font-size:13px; }

    /* Neon title */
    .neon {
      font-weight:800;
      font-size:28px;
      background: linear-gradient(90deg,var(--accent),var(--accent-2));
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      filter: drop-shadow(0 6px 18px rgba(0,230,255,0.08));
    }

    /* Hover animated accent bar */
    .card .accent-bar {
      position:absolute;
      left:-30%;
      top:-40%;
      width:200%;
      height:200%;
      transform: rotate(12deg);
      background: linear-gradient(120deg, rgba(0,255,217,0.06), rgba(125,0,255,0.04));
      transition: opacity .45s ease, transform .45s ease;
      pointer-events:none;
    }
    .card:hover .accent-bar { transform: rotate(12deg) translateY(-6px); opacity:1; }

    /* Project links */
    .link {
      display:inline-block;
      margin-top:10px;
      color:var(--accent);
      text-decoration:none;
      font-weight:600;
    }
    .link:hover { text-decoration:underline; text-decoration-thickness:2px; }

    /* Footer */
    footer { text-align:center; margin-top:28px; color:var(--muted); font-size:13px; }

    /* SVG waves */
    .wave {
      margin-top:28px;
      height:120px;
      overflow:hidden;
    }
    .wave svg { display:block; width:100%; height:100%; }

    /* Collapsible details styling */
    details summary {
      cursor:pointer;
      list-style:none;
      font-weight:600;
      padding:8px 0;
      outline:none;
    }
    details[open] summary::after{ content:'▲'; float:right; color:var(--accent); }
    details summary::after{ content:'▼'; float:right; color:var(--muted); }
    details div { padding:10px 0 4px; color:var(--muted); font-size:14px; }

    /* GitHub stats mock placeholder */
    .github-stats { display:flex; gap:12px; align-items:center; flex-wrap:wrap; margin-top:12px; }
    .stat-box { min-width:150px; flex:1; padding:12px; border-radius:10px; background:rgba(255,255,255,0.02); border:1px solid rgba(255,255,255,0.03); }

    /* Loader overlay */
    .loader-wrap{
      position:fixed; inset:0; display:grid; place-items:center; background: linear-gradient(0deg, rgba(0,0,0,0.65), rgba(0,0,0,0.7));
      z-index:9999; transition:opacity .45s ease, visibility .45s;
    }
    .loader {
      width:92px; height:92px; border-radius:50%;
      display:grid; place-items:center; position:relative;
    }
    .loader .ring {
      position:absolute; inset:0;
      border-radius:50%;
      border:6px solid rgba(255,255,255,0.06);
      box-shadow: 0 6px 22px rgba(0,0,0,0.6);
    }
    .loader .neon-dot {
      width:20px; height:20px; border-radius:50%;
      background: linear-gradient(180deg,var(--accent),var(--accent-2));
      box-shadow: 0 6px 30px rgba(0,230,255,0.16);
      animation: bounce 1.05s ease-in-out infinite;
    }
    @keyframes bounce {
      0%{ transform: translateY(0) scale(1); }
      50%{ transform: translateY(-12px) scale(1.12); }
      100%{ transform: translateY(0) scale(1); }
    }

    /* Small helpers */
    .muted{ color:var(--muted); font-size:14px; }
    .row { display:flex; gap:12px; align-items:center; flex-wrap:wrap; }
    .big { font-size:14px; font-weight:700; color:var(--muted); }

    /* subtle glowing text highlight for callouts */
    .glow {
      text-shadow: 0 6px 22px rgba(0,230,255,0.06), 0 0 12px rgba(125,0,255,0.03);
    }

  </style>
</head>
<body>

  <!-- Loader -->
  <div class="loader-wrap" id="loader">
    <div class="loader" role="status" aria-live="polite" aria-label="Loading profile">
      <div class="ring"></div>
      <div class="neon-dot" style="position:relative; z-index:2;"></div>
    </div>
  </div>

  <div class="wrap" id="app">
    <header>
      <div class="left">
        <div class="avatar-wrap" title="Syed Saqueeb — MERN Developer">
          <div class="neon-ring" aria-hidden="true"></div>
          <a class="avatar" href="https://github.com/saqueeb07" target="_blank" rel="noopener noreferrer">
            <!-- Use your GitHub avatar in production -->
            <img alt="Syed Saqueeb" src="https://avatars.githubusercontent.com/saqueeb07?s=200" onerror="this.src='https://via.placeholder.com/200?text=SS'">
          </a>
        </div>

        <div class="title">
          <h1 class="neon">Syed Saqueeb</h1>
          <p class="muted">MERN Stack Developer • UI/UX Enthusiast — Mobile-first, animation-driven interfaces</p>
          <div class="row" style="margin-top:8px;">
            <span class="big glow">Pixel-perfect UIs</span>
            <span class="muted">•</span>
            <span class="big glow">Performance-first</span>
          </div>
        </div>
      </div>

      <div class="controls">
        <button class="btn" id="themeToggle" aria-pressed="false" title="Toggle dark / light theme">Toggle Theme</button>
        <a class="btn" href="#projects" title="View projects">Projects</a>
        <a class="icon-btn" href="mailto:you@example.com" title="Email">
          ✉
        </a>
      </div>
    </header>

    <!-- top glass intro -->
    <section class="card" aria-labelledby="about">
      <div class="accent-bar" aria-hidden="true"></div>
      <h3 id="about">About me</h3>
      <p class="muted">Mobile-first MERN developer focused on pixel-perfect responsive interfaces, modern UI/UX, and performance optimized applications. I build clean frontends and scalable backends.</p>

      <div style="margin-top:12px;" class="row">
        <a class="link" href="https://genuinehospital.netlify.app" target="_blank" rel="noopener">Genuine Hospital (live)</a>
        <a class="link" href="https://almannandecor.netlify.app" target="_blank" rel="noopener">Almannan Decor (live)</a>
      </div>
    </section>

    <!-- SVG wave -->
    <div class="wave" aria-hidden="true">
      <svg viewBox="0 0 1440 120" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0 60 C 200 0, 400 120, 720 60 C 1040 0, 1240 120, 1440 60 L1440 120 L0 120 Z" fill="rgba(0,230,255,0.06)"></path>
        <path d="M0 80 C 250 20, 500 140, 720 80 C 940 20, 1180 140, 1440 80 L1440 120 L0 120 Z" fill="rgba(125,0,255,0.03)"></path>
      </svg>
    </div>

    <!-- grid -->
    <div class="grid" role="list">
      <article class="card" role="listitem" aria-labelledby="skills">
        <div class="accent-bar" aria-hidden="true"></div>
        <h3 id="skills">Core Skills</h3>
        <p class="muted">MongoDB · Express · React · Node</p>
        <div class="github-stats" aria-hidden="true">
          <div class="stat-box">React • Node</div>
          <div class="stat-box">APIs • Auth</div>
        </div>
      </article>

      <article class="card" role="listitem" aria-labelledby="frontend">
        <h3 id="frontend">Frontend & UI</h3>
        <p class="muted">Tailwind CSS · JavaScript (ES6+) · Responsive & animated UIs</p>
        <p style="margin-top:10px;"><a class="link" href="#" aria-hidden="true">See UI experiments →</a></p>
      </article>

      <article class="card" role="listitem" aria-labelledby="tools">
        <h3 id="tools">Tools & Workflow</h3>
        <p class="muted">Git · VS Code · Chrome DevTools · Postman · CI/CD</p>
      </article>

      <!-- Projects / big card -->
      <article class="card" style="grid-column: span 2;" role="listitem" aria-labelledby="projects" id="projects">
        <h3 id="projects">Featured Projects</h3>
        <div style="display:flex; gap:14px; align-items:flex-start; flex-wrap:wrap; margin-top:8px;">
          <div style="flex:1; min-width:220px;">
            <strong>Genuine Hospital</strong>
            <p class="muted">Responsive medical website with modern UI and accessibility considerations.</p>
            <a class="link" href="https://genuinehospital.netlify.app" target="_blank" rel="noopener">Live preview</a>
          </div>
          <div style="flex:1; min-width:220px;">
            <strong>Almannan Decor</strong>
            <p class="muted">Clean semantic layout with mobile-first responsive UI.</p>
            <a class="link" href="https://almannandecor.netlify.app" target="_blank" rel="noopener">Live preview</a>
          </div>
        </div>
      </article>

      <article class="card" role="listitem" aria-labelledby="contact">
        <h3 id="contact">Contact</h3>
        <p class="muted">Open to collaborations, freelance projects, and full-time roles.</p>
        <p style="margin-top:10px"><a class="link" href="mailto:you@example.com">you@example.com</a></p>
      </article>

      <article class="card" role="listitem" aria-labelledby="more">
        <h3 id="more">More</h3>
        <details>
          <summary>Core list</summary>
          <div>
            MongoDB · Express · React · Node · Tailwind · JavaScript · Figma
          </div>
        </details>

        <details style="margin-top:6px;">
          <summary>Tools</summary>
          <div>Git, GitHub Actions, VS Code, Postman</div>
        </details>
      </article>

    </div>

    <!-- SVG wave separator -->
    <div class="wave" style="margin-top:30px;" aria-hidden="true">
      <svg viewBox="0 0 1440 120" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0 30 C 200 90, 400 0, 720 40 C 1040 80, 1240 0, 1440 40 L1440 120 L0 120 Z" fill="rgba(0,230,255,0.04)"></path>
      </svg>
    </div>

    <footer>
      <p class="muted">Made with ❤️ by <strong>Syed Saqueeb</strong> — <span class="muted">MERN & UI/UX</span></p>
      <p style="margin-top:8px;" class="muted">Tip: hover any card to see the glassmorphism elevation & neon accents ✨</p>
    </footer>
  </div>

  <script>
    // ---------- Loader ----------
    window.addEventListener('load', ()=> {
      const loader = document.getElementById('loader');
      // animate out
      loader.style.opacity = '0';
      loader.style.visibility = 'hidden';
      setTimeout(()=> loader.remove(), 600);
    });

    // ---------- Theme toggle ----------
    const root = document.documentElement;
    const themeToggle = document.getElementById('themeToggle');

    function applyTheme(theme){
      if(theme === 'light'){
        root.classList.add('light');
        themeToggle.setAttribute('aria-pressed','true');
        themeToggle.textContent = 'Light';
      } else {
        root.classList.remove('light');
        themeToggle.setAttribute('aria-pressed','false');
        themeToggle.textContent = 'Dark';
      }
    }

    // Read saved theme
    const saved = localStorage.getItem('profile-theme') || 'dark';
    applyTheme(saved);

    themeToggle.addEventListener('click', ()=>{
      const isLight = root.classList.contains('light');
      const next = isLight ? 'dark' : 'light';
      localStorage.setItem('profile-theme', next);
      applyTheme(next);
    });

    // Small accessibility improvement: focus styles for keyboard users
    document.addEventListener('keydown', (e)=> {
      if(e.key === 'Tab') {
        document.body.classList.add('show-focus');
      }
    });
  </script>
</body>
</html>
