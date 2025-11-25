<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Syed Saqueeb — MERN & UI/UX (No-JS)</title>

  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
  <style>
    /* =======================
       Theme variables
       ======================= */
    :root{
      --bg: #060608;
      --page-bg: linear-gradient(180deg,#05050a,#0a0a12);
      --card: rgba(255,255,255,0.03);
      --glass-border: rgba(255,255,255,0.06);
      --muted: rgba(255,255,255,0.72);
      --accent: #00eaff;
      --accent-2:#7d00ff;
      --neon: rgba(0,230,255,0.14);
      --glass-blur: 8px;
      --glass-shadow: 0 10px 30px rgba(0,0,0,0.6);
      --text: #e9f6ff;
    }

    /* Light theme (applied when toggle is checked) */
    input#theme-toggle:checked ~ .page {
      --bg: #f4f7fb;
      --page-bg: linear-gradient(180deg,#f4f7fb,#eaf1ff);
      --card: rgba(255,255,255,0.75);
      --glass-border: rgba(255,255,255,0.95);
      --muted: rgba(32,41,58,0.78);
      --accent: #0b63ff;
      --accent-2: #ff0066;
      --neon: rgba(11,99,255,0.08);
      --glass-blur: 10px;
      --glass-shadow: 0 8px 28px rgba(20,30,80,0.06);
      --text: #0f1724;
    }

    /* =======================
       Basic page layout
       ======================= */
    * { box-sizing: border-box; }
    html,body { height:100%; margin:0; font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial; }
    body {
      background: var(--page-bg);
      color: var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* Hidden input for CSS-only theme toggle */
    #theme-toggle { position: absolute; left:-9999px; top:auto; width:1px; height:1px; overflow:hidden; }

    .wrap {
      max-width:1100px;
      margin:44px auto;
      padding:28px;
      position:relative;
    }

    header {
      display:flex;
      align-items:center;
      gap:20px;
      justify-content:space-between;
      margin-bottom:18px;
    }
    .left { display:flex; gap:18px; align-items:center; }
    .title h1 { margin:0; font-size:22px; letter-spacing:0.2px; }
    .title p { margin:6px 0 0; color:var(--muted); font-size:13px; }

    /* =======================
       Avatar & neon ring
       ======================= */
    .avatar-wrap{
      width:110px;
      height:110px;
      border-radius:50%;
      display:grid;
      place-items:center;
      position:relative;
      padding:6px;
      background: linear-gradient(135deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
      border:1px solid var(--glass-border);
      backdrop-filter: blur(var(--glass-blur));
      box-shadow: var(--glass-shadow);
      overflow:visible;
    }

    .avatar {
      width:92px;
      height:92px;
      border-radius:50%;
      overflow:hidden;
      display:block;
      border:3px solid rgba(255,255,255,0.06);
      transition: transform .45s ease, box-shadow .3s ease;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.06));
    }
    .avatar img{ width:100%; height:100%; object-fit:cover; display:block; }

    /* neon animated ring purely CSS gradient + rotation */
    .neon-ring {
      position:absolute;
      left:50%;
      top:50%;
      transform:translate(-50%,-50%);
      width:124px;
      height:124px;
      border-radius:50%;
      pointer-events:none;
      filter: blur(6px);
      opacity:0.95;
      animation: spin 9s linear infinite;
      mix-blend-mode:screen;
      background:
        radial-gradient(circle at 20% 20%, rgba(0,255,217,0.35), transparent 10%),
        conic-gradient(from 120deg, rgba(0,255,217,0.45), rgba(125,0,255,0.35), rgba(0,255,217,0.25), rgba(125,0,255,0.25));
    }
    @keyframes spin { to{ transform: translate(-50%,-50%) rotate(360deg); } }

    .avatar-wrap:hover .avatar { transform: scale(1.04); box-shadow: 0 10px 30px rgba(0,0,0,0.4); }

    /* animated frame glow pulse */
    .avatar::after{
      content:"";
      position:absolute;
      left:0; top:0; right:0; bottom:0;
      border-radius:50%;
      box-shadow: 0 0 18px rgba(0,230,255,0.06), inset 0 0 10px rgba(125,0,255,0.02);
      pointer-events:none;
      animation: pulse 2.8s ease-in-out infinite;
    }
    @keyframes pulse {
      0%{ transform:scale(.98); opacity:.9; }
      50%{ transform:scale(1.02); opacity:1; }
      100%{ transform:scale(.98); opacity:.9; }
    }

    /* =======================
       Buttons / toggle label
       ======================= */
    .controls { display:flex; gap:10px; align-items:center; }
    .toggle {
      display:inline-grid;
      grid-auto-flow:column;
      gap:6px;
      align-items:center;
      padding:8px 12px;
      border-radius:999px;
      background: linear-gradient(90deg,var(--accent),var(--accent-2));
      color:#071426;
      font-weight:700;
      font-size:13px;
      box-shadow: 0 10px 40px rgba(0,230,255,0.06);
      cursor:pointer;
      user-select:none;
    }
    /* Show theme label text depending on checked state */
    #theme-toggle:not(:checked) + label .on { display:inline-block; }
    #theme-toggle:checked + label .on { display:none; }
    #theme-toggle:checked + label .off { display:inline-block; }
    #theme-toggle:not(:checked) + label .off { display:none; }

    /* =======================
       Glass cards grid
       ======================= */
    .grid {
      display:grid;
      grid-template-columns: repeat(3,1fr);
      gap:18px;
      margin-top:28px;
      align-items:start;
    }
    @media (max-width:980px){ .grid{ grid-template-columns: repeat(2,1fr);} }
    @media (max-width:620px){ .grid{ grid-template-columns: 1fr; } header{flex-direction:column;align-items:flex-start} .controls{margin-top:12px} }

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
    .card:hover { transform: translateY(-10px) scale(1.01); border-color: rgba(255,255,255,0.12); }
    .card h3 { margin:0 0 8px 0; color:var(--accent); letter-spacing:0.4px; }
    .card p{ margin:0; color:var(--muted); font-size:13px; }

    /* accent bar (subtle animated gradient) */
    .card .accent-bar {
      position:absolute;
      left:-40%;
      top:-50%;
      width:220%;
      height:220%;
      transform: rotate(10deg);
      background: linear-gradient(120deg, rgba(0,255,217,0.05), rgba(125,0,255,0.03));
      transition: opacity .45s ease, transform .45s ease;
      pointer-events:none;
      opacity:0.9;
      animation: floaty 6s ease-in-out infinite;
    }
    .card:hover .accent-bar { transform: rotate(12deg) translateY(-8px); opacity:1; }
    @keyframes floaty { 0%{ transform: translateY(0) rotate(10deg); } 50%{ transform: translateY(-6px) rotate(10deg); } 100%{ transform: translateY(0) rotate(10deg); } }

    /* neon text */
    .neon {
      font-weight:800;
      font-size:28px;
      background: linear-gradient(90deg,var(--accent),var(--accent-2));
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      filter: drop-shadow(0 10px 30px rgba(0,230,255,0.06));
    }

    .link { color:var(--accent); text-decoration:none; font-weight:600; display:inline-block; margin-top:8px; }
    .link:hover { text-decoration:underline; text-decoration-thickness:2px; }

    /* =======================
       SVG waves
       ======================= */
    .wave { margin-top:28px; height:120px; overflow:hidden; }
    .wave svg{ display:block; width:100%; height:100%; }

    /* =======================
       Loader (CSS-only)
       - visible for a short duration then fades out
       ======================= */
    .loader-wrap {
      position:fixed; inset:0; z-index:9999; display:grid; place-items:center;
      background: linear-gradient(0deg, rgba(0,0,0,0.65), rgba(0,0,0,0.6));
      -webkit-backdrop-filter: blur(2px);
      animation: loaderFade 2.8s linear forwards; /* fades out after 2.8s */
    }
    .loader {
      width:96px; height:96px; border-radius:50%; display:grid; place-items:center; position:relative;
    }
    .loader .ring {
      position:absolute; inset:0; border-radius:50%;
      border:6px solid rgba(255,255,255,0.06);
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
      animation: ringSpin 1.9s linear infinite;
    }
    .loader .dot {
      width:20px; height:20px; border-radius:50%;
      background: linear-gradient(180deg,var(--accent),var(--accent-2));
      box-shadow: 0 6px 30px rgba(0,230,255,0.12);
      animation: dotBounce 1.05s ease-in-out infinite;
      z-index:2;
    }
    @keyframes ringSpin { to{ transform: rotate(360deg); } }
    @keyframes dotBounce { 0%{ transform: translateY(0) } 50%{ transform: translateY(-14px) } 100%{ transform: translateY(0) } }
    @keyframes loaderFade {
      0%{ opacity:1; visibility:visible; }
      75%{ opacity:1; visibility:visible; }
      100%{ opacity:0; visibility:hidden; pointer-events:none; }
    }

    /* =======================
       Small helpers
       ======================= */
    footer { text-align:center; margin-top:28px; color:var(--muted); font-size:13px; }
    .muted{ color:var(--muted); font-size:14px; }
    .row { display:flex; gap:12px; align-items:center; flex-wrap:wrap; }
    .big { font-size:14px; font-weight:700; color:var(--muted); }
  </style>
</head>
<body>

  <!-- CSS-only theme toggle input must appear before page so we can use sibling selectors -->
  <input id="theme-toggle" type="checkbox" aria-label="Toggle theme (dark / light)">
  <div class="page">
    <!-- Loader (CSS-only, will fade out after its animation) -->
    <div class="loader-wrap" role="status" aria-live="polite" aria-label="Loading profile">
      <div class="loader" aria-hidden="true">
        <div class="ring" aria-hidden="true"></div>
        <div class="dot" aria-hidden="true"></div>
      </div>
    </div>

    <div class="wrap" role="main" aria-labelledby="profile-title">
      <header>
        <div class="left">
          <div class="avatar-wrap" aria-hidden="false" title="Syed Saqueeb">
            <div class="neon-ring" aria-hidden="true"></div>
            <a class="avatar" href="https://github.com/saqueeb07" target="_blank" rel="noopener noreferrer">
              <!-- Replace with your GitHub avatar -->
              <img src="https://avatars.githubusercontent.com/saqueeb07?s=200" alt="Syed Saqueeb" onerror="this.removeAttribute('onerror')">
            </a>
          </div>

          <div class="title">
            <h1 id="profile-title" class="neon">Syed Saqueeb</h1>
            <p class="muted">MERN Stack Developer • UI/UX Enthusiast — Mobile-first, animation-driven interfaces</p>
            <div class="row" style="margin-top:8px;">
              <span class="big">Pixel-perfect UIs</span>
              <span class="muted">•</span>
              <span class="big">Performance-first</span>
            </div>
          </div>
        </div>

        <div class="controls">
          <!-- Label acts as toggle control (no JS). The text updates via CSS rules above. -->
          <label for="theme-toggle" class="toggle" role="button" aria-pressed="false" tabindex="0">
            <span class="on">Dark</span>
            <span class="off">Light</span>
          </label>
        </div>
      </header>

      <!-- Intro card -->
      <section class="card" aria-labelledby="about">
        <div class="accent-bar" aria-hidden="true"></div>
        <h3 id="about">About me</h3>
        <p class="muted">Mobile-first MERN developer focused on pixel-perfect responsive interfaces, modern UI/UX, and performance optimized apps. I build clean frontends and scalable backends.</p>

        <div style="margin-top:12px;" class="row">
          <a class="link" href="https://genuinehospital.netlify.app" target="_blank" rel="noopener">Genuine Hospital (live)</a>
          <a class="link" href="https://almannandecor.netlify.app" target="_blank" rel="noopener">Almannan Decor (live)</a>
        </div>
      </section>

      <!-- SVG wave -->
      <div class="wave" aria-hidden="true">
        <svg viewBox="0 0 1440 120" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
          <path d="M0 60 C 200 0, 400 120, 720 60 C 1040 0, 1240 120, 1440 60 L1440 120 L0 120 Z"
                fill="rgba(0,230,255,0.06)"></path>
          <path d="M0 80 C 250 20, 500 140, 720 80 C 940 20, 1180 140, 1440 80 L1440 120 L0 120 Z"
                fill="rgba(125,0,255,0.03)"></path>
        </svg>
      </div>

      <!-- Cards grid -->
      <div class="grid" role="list" aria-label="Profile sections">
        <article class="card" role="listitem" aria-labelledby="skills">
          <div class="accent-bar" aria-hidden="true"></div>
          <h3 id="skills">Core Skills</h3>
          <p class="muted">MongoDB · Express · React · Node</p>
        </article>

        <article class="card" role="listitem" aria-labelledby="frontend">
          <h3 id="frontend">Frontend & UI</h3>
          <p class="muted">Tailwind CSS · JavaScript (ES6+) · Responsive & animated UIs</p>
        </article>

        <article class="card" role="listitem" aria-labelledby="tools">
          <h3 id="tools">Tools & Workflow</h3>
          <p class="muted">Git · VS Code · Chrome DevTools · CI/CD</p>
        </article>

        <article class="card" style="grid-column: span 2;" role="listitem" aria-labelledby="projects">
          <h3 id="projects">Featured Projects</h3>
          <div style="display:flex; gap:14px; align-items:flex-start; flex-wrap:wrap; margin-top:8px;">
            <div style="flex:1; min-width:220px;">
              <strong>Genuine Hospital</strong>
              <p class="muted">Responsive medical website with modern UI and accessibility focus.</p>
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
            <div>MongoDB · Express · React · Node · Tailwind · JavaScript · Figma</div>
          </details>

          <details style="margin-top:8px;">
            <summary>Tools</summary>
            <div>Git, GitHub Actions, VS Code, Postman</div>
          </details>
        </article>

      </div>

      <!-- Lower SVG wave -->
      <div class="wave" aria-hidden="true" style="margin-top:30px;">
        <svg viewBox="0 0 1440 120" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
          <path d="M0 30 C 200 90, 400 0, 720 40 C 1040 80, 1240 0, 1440 40 L1440 120 L0 120 Z"
                fill="rgba(0,230,255,0.04)"></path>
        </svg>
      </div>

      <footer>
        <p class="muted">Made with ❤️ by <strong>Syed Saqueeb</strong> — MERN & UI/UX</p>
        <p class="muted" style="margin-top:8px;">Tip: toggle theme using the pill at top-right (CSS-only)</p>
      </footer>
    </div>
  </div>

  <!-- NOTE: no JavaScript used anywhere in this file -->
</body>
</html>
