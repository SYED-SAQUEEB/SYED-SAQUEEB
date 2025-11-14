<div align="center">

<!-- Name Animation With Bounce + Wave + Gradient Underline -->
<svg width="780" height="160" viewBox="0 0 780 160" xmlns="http://www.w3.org/2000/svg">
  
  <defs>
    <linearGradient id="textGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#38BDF8"/>
      <stop offset="35%" stop-color="#7C3AED"/>
      <stop offset="65%" stop-color="#FB7185"/>
      <stop offset="100%" stop-color="#06B6D4"/>
    </linearGradient>

    <filter id="shadow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- Greeting -->
  <text x="50%" y="40" text-anchor="middle"
        font-family="Fira Code, monospace"
        font-size="20" fill="#cbd5ff" opacity="0.9">
    Hi 👋 I'm
  </text>

  <!-- Bouncing + wave animated name -->
  <text x="50%" y="95" text-anchor="middle"
        font-family="Fira Code, monospace"
        font-weight="900" font-size="42"
        fill="url(#textGrad)" filter="url(#shadow)">
    SYED SAQUEEB
    <animate attributeName="y"
             values="95;90;95"
             dur="3s"
             repeatCount="indefinite" />
  </text>

  <!-- Animated underline -->
  <rect x="160" y="110" width="460" height="5" rx="2"
        fill="url(#textGrad)">
    <animate attributeName="width"
             values="460;480;460"
             dur="3s"
             repeatCount="indefinite"/>
  </rect>
</svg>

<!-- Typing animation -->
<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=20&duration=3500&pause=900&color=38BDF8&center=true&vCenter=true&width=700&lines=Frontend+Developer;UI%2FUX+Enthusiast;Building+Modern+Web+Experiences;Creative+Thinker" />
</div>
