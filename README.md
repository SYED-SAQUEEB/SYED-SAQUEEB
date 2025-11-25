<!-- README.md — Futuristic GitHub Profile (SVG-only animations) -->

<p align="center">
  <!-- Neon Title (SVG with gradient + glow filter) -->
  <svg width="100%" height="140" viewBox="0 0 1200 140" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" role="img" aria-label="Syed Saqueeb">
    <defs>
      <linearGradient id="g1" x1="0" x2="1">
        <stop offset="0" stop-color="#00eaff"/>
        <stop offset="0.5" stop-color="#7d00ff"/>
        <stop offset="1" stop-color="#ff6ec7"/>
        <animate attributeName="x1" dur="6s" values="0;1;0" repeatCount="indefinite" />
      </linearGradient>

      <filter id="glow" x="-50%" y="-50%" width="200%" height="200%">
        <feGaussianBlur stdDeviation="3.5" result="blur"/>
        <feMerge>
          <feMergeNode in="blur"/>
          <feMergeNode in="SourceGraphic"/>
        </feMerge>
      </filter>
    </defs>

    <text x="50%" y="55%" text-anchor="middle" font-size="46" font-family="Verdana, Geneva, sans-serif"
          fill="url(#g1)" filter="url(#glow)" font-weight="700">
      SYED SAQUEEB
    </text>
    <text x="50%" y="86%" text-anchor="middle" font-size="14" font-family="Verdana, Geneva, sans-serif"
          fill="#9fb7ff" opacity="0.85">
      MERN Stack Developer • UI/UX Enthusiast
    </text>
  </svg>
</p>

---

<p align="center">
  <!-- 3D Rotating Profile Frame (SVG) -->
  <svg width="260" height="260" viewBox="0 0 260 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Rotating profile frame">
    <defs>
      <!-- soft glow -->
      <radialGradient id="rg" cx="50%" cy="35%" r="60%">
        <stop offset="0%" stop-color="#00eaff" stop-opacity="0.6"/>
        <stop offset="60%" stop-color="#7d00ff" stop-opacity="0.18"/>
        <stop offset="100%" stop-color="#000000" stop-opacity="0"/>
      </radialGradient>

      <!-- ring segments to simulate 3D -->
      <linearGradient id="ringGradA" x1="0" x2="1">
        <stop offset="0" stop-color="#00eaff"/>
        <stop offset="1" stop-color="#7d00ff"/>
      </linearGradient>

      <!-- subtle rim shadow -->
      <filter id="drop" x="-50%" y="-50%" width="200%" height="200%">
        <feDropShadow dx="0" dy="6" stdDeviation="10" flood-color="#000" flood-opacity="0.5"/>
      </filter>
    </defs>

    <!-- background glow -->
    <circle cx="130" cy="130" r="110" fill="url(#rg)" opacity="0.9"/>

    <!-- rotating outer multi-segment ring (conic illusion) -->
    <g transform="translate(130,130)">
      <!-- multiple thin arcs rotated with different speeds to suggest 3D rotation -->
      <g>
        <path d="M110 0 A110 110 0 0 1 77.78 77.78" fill="none" stroke="url(#ringGradA)" stroke-width="6" stroke-linecap="round" filter="url(#drop)" opacity="0.92">
          <animateTransform attributeName="transform" type="rotate" from="0" to="360" dur="11s" repeatCount="indefinite"/>
        </path>
        <path d="M85 55 A85 85 0 0 1 0 85" fill="none" stroke="#00ffd3" stroke-width="3" stroke-linecap="round" opacity="0.55">
          <animateTransform attributeName="transform" type="rotate" from="360" to="0" dur="7.6s" repeatCount="indefinite"/>
        </path>
        <path d="M-77.78 77.78 A110 110 0 0 1 -110 0" fill="none" stroke="#ff6ec7" stroke-width="4" stroke-linecap="round" opacity="0.5">
          <animateTransform attributeName="transform" type="rotate" from="0" to="-360" dur="15s" repeatCount="indefinite"/>
        </path>
      </g>
    </g>

    <!-- profile image clipped as circle -->
    <defs>
      <clipPath id="c">
        <circle cx="130" cy="130" r="68"/>
      </clipPath>
    </defs>

    <!-- image (replace href for your avatar if needed) -->
    <image href="https://avatars.githubusercontent.com/saqueeb07" x="62" y="62" width="136" height="136" clip-path="url(#c)" preserveAspectRatio="xMidYMid slice" />

    <!-- inner rim to create depth -->
    <circle cx="130" cy="130" r="70" fill="none" stroke="#000000" stroke-opacity="0.25" stroke-width="6"/>

    <!-- small animated ticks around inner rim to suggest rotation -->
    <g transform="translate(130,130)">
      <!-- 12 ticks -->
      <g stroke="#00eaff" stroke-width="2" stroke-linecap="round" opacity="0.85">
        <!-- a single tick animated on scale to pulse; duplicate with rotation -->
        <g>
          <line x1="0" y1="-86" x2="0" y2="-98" transform="rotate(0)">
            <animate attributeName="opacity" values="0.2;1;0.2" dur="2s" repeatCount="indefinite" begin="0s"/>
          </line>
        </g>
        <!-- copy ticks rotated -->
        <!-- rather than writing all, use transforms with animateTransform on the group -->
        <g>
          <use href="#tick" />
        </g>
      </g>
    </g>
  </svg>
</p>

---

## 🚀 About Me
I build modern, mobile-first MERN apps with attention to UI/UX, performance, and craft.

- ⚡ Pixel-perfect UI  
- 🎨 Clean UX & animations  
- 🚀 Scalable MERN architecture  
- 📱 Mobile-first responsive design

---

## 🌟 Featured Projects

<!-- Project Cards (SVG auto-tilt animation simulating hover-tilt) -->
<p align="center">
  <!-- Card 1 -->
  <svg width="360" height="120" viewBox="0 0 360 120" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Genuine Hospital project card">
    <defs>
      <linearGradient id="cardA" x1="0" x2="1">
        <stop offset="0" stop-color="#021027"/>
        <stop offset="1" stop-color="#002a3a"/>
      </linearGradient>
      <filter id="cg" x="-50%" y="-50%" width="200%" height="200%">
        <feDropShadow dx="0" dy="8" stdDeviation="10" flood-color="#001628" flood-opacity="0.6"/>
      </filter>
    </defs>

    <!-- gentle tilting group -->
    <g transform="translate(0,0)">
      <g>
        <rect x="6" y="6" rx="12" ry="12" width="348" height="108" fill="url(#cardA)" stroke="#00eaff" stroke-opacity="0.12" filter="url(#cg)"/>
        <text x="32" y="44" font-family="Verdana" font-size="16" fill="#bfeeff" font-weight="700">Genuine Hospital</text>
        <text x="32" y="68" font-family="Verdana" font-size="12" fill="#9fb7ff">Responsive hospital UI — accessibility focused</text>
        <a href="https://genuinehospital.netlify.app">
          <text x="32" y="94" font-family="Verdana" font-size="12" fill="#00eaff">Live preview →</text>
        </a>

        <!-- tilt animation (oscillate rotate around center) -->
        <animateTransform attributeName="transform" type="rotate" values="-2 180 60; 2 180 60; -2 180 60" dur="6s" repeatCount="indefinite" additive="replace"/>
      </g>
    </g>
  </svg>

  <!-- spacer -->
  &nbsp;&nbsp;

  <!-- Card 2 -->
  <svg width="360" height="120" viewBox="0 0 360 120" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Almannan Decor project card">
    <defs>
      <linearGradient id="cardB" x1="0" x2="1">
        <stop offset="0" stop-color="#120012"/>
        <stop offset="1" stop-color="#2a002a"/>
      </linearGradient>
      <filter id="cg2" x="-50%" y="-50%" width="200%" height="200%">
        <feDropShadow dx="0" dy="8" stdDeviation="10" flood-color="#2a001f" flood-opacity="0.5"/>
      </filter>
    </defs>

    <g>
      <rect x="6" y="6" rx="12" ry="12" width="348" height="108" fill="url(#cardB)" stroke="#ff6ec7" stroke-opacity="0.12" filter="url(#cg2)"/>
      <text x="32" y="44" font-family="Verdana" font-size="16" fill="#ffd3f8" font-weight="700">Almannan Decor</text>
      <text x="32" y="68" font-family="Verdana" font-size="12" fill="#ffb7ea">Minimal decor UI — semantic & responsive</text>
      <a href="https://almannandecor.netlify.app">
        <text x="32" y="94" font-family="Verdana" font-size="12" fill="#ff6ec7">Live preview →</text>
      </a>

      <!-- subtle tilt -->
      <animateTransform attributeName="transform" type="rotate" values="3 180 60; -3 180 60; 3 180 60" dur="7.2s" repeatCount="indefinite" additive="replace"/>
    </g>
  </svg>
</p>

---

## 🧰 Skills — Animated Bars

<p align="center">
  <!-- Skill bars implemented in SVG with animated widths -->
  <svg width="720" height="160" viewBox="0 0 720 160" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Animated skill bars">
    <defs>
      <linearGradient id="s1" x1="0" x2="1"><stop offset="0" stop-color="#00eaff"/><stop offset="1" stop-color="#7d00ff"/></linearGradient>
      <linearGradient id="s2" x1="0" x2="1"><stop offset="0" stop-color="#ff6ec7"/><stop offset="1" stop-color="#ffae00"/></linearGradient>
      <linearGradient id="s3" x1="0" x2="1"><stop offset="0" stop-color="#00ffd3"/><stop offset="1" stop-color="#00eaff"/></linearGradient>
      <filter id="bglow"><feGaussianBlur stdDeviation="4" result="b"/><feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge></filter>
    </defs>

    <!-- labels -->
    <text x="16" y="28" font-family="Verdana" font-size="13" fill="#bfeeff">React</text>
    <rect x="110" y="12" rx="6" ry="6" width="580" height="20" fill="#0b1220" opacity="0.35"/>
    <rect x="110" y="12" rx="6" ry="6" width="0" height="20" fill="url(#s1)" filter="url(#bglow)">
      <animate attributeName="width" dur="1.6s" values="0;460" fill="freeze" begin="0.2s"/>
    </rect>

    <text x="16" y="68" font-family="Verdana" font-size="13" fill="#bfeeff">Node.js</text>
    <rect x="110" y="52" rx="6" ry="6" width="580" height="20" fill="#0b1220" opacity="0.35"/>
    <rect x="110" y="52" rx="6" ry="6" width="0" height="20" fill="url(#s2)" filter="url(#bglow)">
      <animate attributeName="width" dur="1.6s" values="0;380" fill="freeze" begin="0.5s"/>
    </rect>

    <text x="16" y="108" font-family="Verdana" font-size="13" fill="#bfeeff">MongoDB</text>
    <rect x="110" y="92" rx="6" ry="6" width="580" height="20" fill="#0b1220" opacity="0.35"/>
    <rect x="110" y="92" rx="6" ry="6" width="0" height="20" fill="url(#s3)" filter="url(#bglow)">
      <animate attributeName="width" dur="1.6s" values="0;320" fill="freeze" begin="0.8s"/>
    </rect>
  </svg>
</p>

---

## 📦 Quick Links & Futuristic Buttons

<p align="center">
  <!-- Buttons as inline SVG links for consistent visuals in README -->
  <a href="https://github.com/saqueeb07" target="_blank" rel="noopener">
    <svg width="160" height="44" viewBox="0 0 160 44" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="GitHub">
      <rect rx="10" ry="10" width="160" height="44" fill="#001624" stroke="#00eaff" stroke-opacity="0.16"/>
      <text x="80" y="28" text-anchor="middle" font-family="Verdana" font-size="14" fill="#00eaff" font-weight="700">View GitHub</text>
    </svg>
  </a>
  &nbsp;&nbsp;
  <a href="https://genuinehospital.netlify.app" target="_blank" rel="noopener">
    <svg width="192" height="44" viewBox="0 0 192 44" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Portfolio">
      <rect rx="10" ry="10" width="192" height="44" fill="#001624" stroke="#ff6ec7" stroke-opacity="0.12"/>
      <text x="96" y="28" text-anchor="middle" font-family="Verdana" font-size="14" fill="#ff6ec7" font-weight="700">Open Portfolio</text>
    </svg>
  </a>
</p>

---

## 📫 Connect
<p align="center">
  <a href="https://github.com/saqueeb07"><img alt="GitHub" src="https://simpleicons.org/icons/github.svg" width="26" style="vertical-align:middle; margin-right:8px;"></a>
  <a href="https://www.linkedin.com/in/"><img alt="LinkedIn" src="https://simpleicons.org/icons/linkedin.svg" width="26" style="vertical-align:middle; margin-left:10px; margin-right:8px;"></a>
  <a href="mailto:you@example.com"><img alt="Email" src="https://simpleicons.org/icons/gmail.svg" width="26" style="vertical-align:middle; margin-left:10px;"></a>
</p>

---

<p align="center">
  Made with ❤️ by **Syed Saqueeb** — MERN • UI/UX
</p>
