
<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&family=Space+Grotesk:wght@400;500;700&display=swap');
  *{box-sizing:border-box;margin:0;padding:0}
  :root{
    --bg:#0d1117;--surface:#161b22;--surface2:#21262d;--border:#30363d;
    --text:#c9d1d9;--muted:#8b949e;--pink:#fe428e;--blue:#2f81f7;--purple:#7f3fbf;
    --yellow:#f8d866;--green:#3fb950;--white:#ffffff;
  }
  body{background:var(--bg);color:var(--text);font-family:'Space Grotesk',sans-serif;padding:0;min-height:100vh}
  .wrapper{max-width:860px;margin:0 auto;padding:2rem 1.5rem}

  /* === HEADER === */
  .header{text-align:center;margin-bottom:2.5rem;position:relative;overflow:hidden}
  .header::before{content:'';position:absolute;top:-60px;left:50%;transform:translateX(-50%);width:400px;height:400px;background:radial-gradient(ellipse,rgba(254,66,142,0.08) 0%,transparent 70%);pointer-events:none}
  .greeting{font-family:'Fira Code',monospace;font-size:1rem;color:var(--muted);margin-bottom:.5rem;animation:fadeDown .6s ease both}
  .greeting span{color:var(--white);font-weight:600}
  .name-line{font-size:2.8rem;font-weight:700;line-height:1.1;margin-bottom:.3rem;animation:fadeDown .7s .1s ease both}
  .name-line .first{color:var(--white)}
  .name-line .last{color:var(--pink)}
  .tagline{font-family:'Fira Code',monospace;font-size:.9rem;color:var(--blue);margin-bottom:1.5rem;animation:fadeDown .7s .2s ease both}
  .tagline::before{content:'> '}
  .tagline::after{content:'_';animation:blink 1s infinite}
  @keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
  @keyframes fadeDown{from{opacity:0;transform:translateY(-12px)}to{opacity:1;transform:translateY(0)}}
  @keyframes fadeUp{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}

  /* === ONE PIECE FLAG === */
  .flag-container{display:flex;justify-content:center;margin:1.5rem 0 2rem;animation:fadeUp .8s .3s ease both}
  .flag-wrap{position:relative;width:200px;animation:flagWave 3s ease-in-out infinite}
  @keyframes flagWave{
    0%,100%{clip-path:polygon(0 0,100% 3%,100% 97%,0 100%)}
    25%{clip-path:polygon(0 0,100% 0%,100% 100%,0 100%)}
    50%{clip-path:polygon(0 3%,100% 0%,100% 100%,0 97%)}
    75%{clip-path:polygon(0 0,100% 0%,100% 100%,0 100%)}
  }
  .flag{background:#111;border-radius:2px;padding:14px 20px;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 24px rgba(0,0,0,0.5);border:1px solid #333}
  .flag-pole{width:4px;height:160px;background:linear-gradient(180deg,#b8860b,#8b6914);border-radius:2px;margin-right:4px;flex-shrink:0;box-shadow:0 0 6px rgba(184,134,11,0.4)}
  .skull-svg{width:130px;height:90px}

  /* skull animation */
  .skull-eyes{animation:eyeGlow 2.5s ease-in-out infinite}
  @keyframes eyeGlow{0%,100%{opacity:.7}50%{opacity:1}}
  .skull-hat{animation:hatBob 2s ease-in-out infinite}
  @keyframes hatBob{0%,100%{transform:translateY(0)}50%{transform:translateY(-2px)}}

  /* === BADGES === */
  .badges{display:flex;flex-wrap:wrap;justify-content:center;gap:.6rem;margin-bottom:2rem;animation:fadeUp .8s .4s ease both}
  .badge{display:inline-flex;align-items:center;gap:.4rem;padding:.4rem .85rem;border-radius:100px;font-size:.8rem;font-weight:600;text-decoration:none;transition:transform .2s,box-shadow .2s;letter-spacing:.02em}
  .badge:hover{transform:translateY(-2px);box-shadow:0 4px 16px rgba(0,0,0,.4)}
  .badge-fb{background:#1877f2;color:#fff}
  .badge-li{background:#0a66c2;color:#fff}
  .badge-wa{background:#25d366;color:#000}
  .badge-ig{background:linear-gradient(135deg,#f09433,#e6683c,#dc2743,#cc2366,#bc1888);color:#fff}
  .badge-gh{background:#24292e;color:#fff;border:1px solid #444}
  .badge-icon{width:16px;height:16px;fill:currentColor}

  /* === ABOUT GRID === */
  .section-title{font-family:'Fira Code',monospace;font-size:1rem;color:var(--pink);margin-bottom:1rem;padding-bottom:.4rem;border-bottom:1px solid var(--border);letter-spacing:.05em}
  .section-title::before{content:'## ';color:var(--muted)}
  .about-grid{display:grid;grid-template-columns:1fr auto;gap:1.5rem;margin-bottom:2rem;animation:fadeUp .8s .5s ease both;align-items:start}
  .about-items{display:flex;flex-direction:column;gap:.75rem}
  .about-item{display:flex;gap:.75rem;align-items:flex-start;font-size:.9rem;color:var(--text);line-height:1.5}
  .about-item .icon{font-size:1rem;flex-shrink:0;margin-top:.05rem}
  .about-item a{color:var(--blue);text-decoration:none}
  .about-item a:hover{text-decoration:underline}
  .coding-gif{width:160px;border-radius:8px;overflow:hidden;flex-shrink:0}
  .coding-gif img{width:100%;display:block}
  .fake-gif{width:160px;height:110px;background:var(--surface);border-radius:8px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;flex-direction:column;gap:.3rem;font-family:'Fira Code',monospace;font-size:.65rem;color:var(--green);overflow:hidden;position:relative}
  .code-line{animation:codeFade 3s ease-in-out infinite}
  .code-line:nth-child(2){animation-delay:.4s}
  .code-line:nth-child(3){animation-delay:.8s}
  .code-line:nth-child(4){animation-delay:1.2s}
  .code-line:nth-child(5){animation-delay:1.6s}
  @keyframes codeFade{0%,100%{opacity:.4}50%{opacity:1}}

  /* === SKILLS === */
  .skills-section{margin-bottom:2rem;animation:fadeUp .8s .6s ease both}
  .pills-wrap{display:flex;flex-wrap:wrap;gap:.5rem}
  .pill{padding:.3rem .7rem;border-radius:6px;font-size:.75rem;font-weight:600;letter-spacing:.02em;animation:pillPop .5s ease both;transition:transform .15s}
  .pill:hover{transform:scale(1.05)}
  @keyframes pillPop{from{opacity:0;transform:scale(.85)}to{opacity:1;transform:scale(1)}}
  .pill-js{background:#f0db4f22;color:#f0db4f;border:1px solid #f0db4f44}
  .pill-ts{background:#007acc22;color:#5eb8f5;border:1px solid #007acc44}
  .pill-react{background:#61dbfb22;color:#61dbfb;border:1px solid #61dbfb44}
  .pill-next{background:#ffffff15;color:#fff;border:1px solid #ffffff33}
  .pill-node{background:#3c873a22;color:#6dcf6d;border:1px solid #3c873a44}
  .pill-mongo{background:#4ea94b22;color:#6dcf6d;border:1px solid #4ea94b44}
  .pill-html{background:#e34f2622;color:#f97b4e;border:1px solid #e34f2644}
  .pill-css{background:#1572b622;color:#5eb8f5;border:1px solid #1572b644}
  .pill-tail{background:#06b6d422;color:#22d3ee;border:1px solid #06b6d444}
  .pill-redux{background:#764abc22;color:#b393d3;border:1px solid #764abc44}
  .pill-sass{background:#cc669922;color:#f09fc4;border:1px solid #cc669944}
  .pill-express{background:#ffffff10;color:#ccc;border:1px solid #ffffff22}

  /* === TOOLS === */
  .tools-wrap{display:flex;flex-wrap:wrap;gap:.5rem}
  .tool-pill{padding:.25rem .6rem;border-radius:4px;font-size:.72rem;background:var(--surface2);border:1px solid var(--border);color:var(--muted);transition:color .15s,border-color .15s}
  .tool-pill:hover{color:var(--text);border-color:#555}

  /* === STATS === */
  .stats-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:2rem;animation:fadeUp .8s .7s ease both}
  .stat-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:1rem;text-align:center}
  .stat-title{font-size:.75rem;color:var(--muted);margin-bottom:.5rem;font-family:'Fira Code',monospace}
  .stat-bar-wrap{height:6px;background:var(--surface2);border-radius:3px;overflow:hidden}
  .stat-bar{height:100%;border-radius:3px;animation:barGrow 1.5s ease both}
  @keyframes barGrow{from{width:0}to{width:var(--w)}}
  .stat-lang{display:flex;justify-content:space-between;font-size:.8rem;margin-top:.4rem;color:var(--muted)}

  /* === FOOTER === */
  .footer{text-align:center;font-family:'Fira Code',monospace;font-size:.8rem;color:var(--muted);margin-top:2rem;padding-top:1.5rem;border-top:1px solid var(--border);animation:fadeUp .8s .9s ease both}
  .footer span{color:var(--pink)}

  @media(max-width:560px){
    .about-grid{grid-template-columns:1fr}
    .fake-gif{display:none}
    .stats-row{grid-template-columns:1fr}
    .name-line{font-size:2rem}
  }
</style>

<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="greeting">&gt; Hey There! <span>I'm Asif Hosen</span> 👋</div>
    <div class="name-line"><span class="first">Asif </span><span class="last">Hosen</span></div>
    <div class="tagline">Full-Stack Web Developer from Bangladesh</div>

    <!-- ONE PIECE STRAW HAT FLAG -->
    <div class="flag-container">
      <div class="flag-wrap">
        <div class="flag">
          <div class="flag-pole"></div>
          <svg class="skull-svg" viewBox="0 0 130 90" xmlns="http://www.w3.org/2000/svg">
            <!-- crossbones left -->
            <line x1="12" y1="72" x2="55" y2="45" stroke="white" stroke-width="7" stroke-linecap="round"/>
            <circle cx="10" cy="75" r="7" fill="white"/>
            <circle cx="10" cy="62" r="5" fill="white"/>
            <circle cx="55" cy="42" r="6" fill="white"/>
            <!-- crossbones right -->
            <line x1="118" y1="72" x2="75" y2="45" stroke="white" stroke-width="7" stroke-linecap="round"/>
            <circle cx="120" cy="75" r="7" fill="white"/>
            <circle cx="120" cy="62" r="5" fill="white"/>
            <circle cx="75" cy="42" r="6" fill="white"/>
            <!-- skull -->
            <ellipse cx="65" cy="52" rx="28" ry="26" fill="white"/>
            <!-- jaw -->
            <rect x="51" y="64" width="28" height="13" rx="4" fill="white"/>
            <!-- teeth -->
            <rect x="53" y="65" width="5" height="10" rx="1" fill="#111"/>
            <rect x="60" y="65" width="5" height="10" rx="1" fill="#111"/>
            <rect x="67" y="65" width="5" height="10" rx="1" fill="#111"/>
            <rect x="74" y="65" width="4" height="10" rx="1" fill="#111"/>
            <!-- eyes -->
            <g class="skull-eyes">
              <ellipse cx="56" cy="50" rx="7" ry="8" fill="#111"/>
              <ellipse cx="74" cy="50" rx="7" ry="8" fill="#111"/>
            </g>
            <!-- nose -->
            <ellipse cx="65" cy="60" rx="3" ry="2.5" fill="#111"/>
            <!-- STRAW HAT -->
            <g class="skull-hat">
              <!-- brim -->
              <ellipse cx="65" cy="28" rx="34" ry="8" fill="#e8b84b"/>
              <ellipse cx="65" cy="26" rx="24" ry="6" fill="#e8b84b"/>
              <!-- top -->
              <rect x="41" y="6" width="48" height="22" rx="12" fill="#e8b84b"/>
              <!-- hat band red -->
              <rect x="38" y="22" width="54" height="7" rx="2" fill="#cc2200"/>
            </g>
          </svg>
        </div>
      </div>
    </div>
  </div>

  <!-- SOCIAL BADGES -->
  <div class="badges">
    <a class="badge badge-fb" href="https://www.facebook.com/ahamedasif01729?rdid=B2swPOEE7grVUsij#" target="_blank">
      <svg class="badge-icon" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
      Facebook
    </a>
    <a class="badge badge-li" href="https://linkedin.com/in/asif-hosen-87269832b" target="_blank">
      <svg class="badge-icon" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a class="badge badge-wa" href="https://api.whatsapp.com/send/?phone=8801729149634&text&type=phone_number&app_absent=0" target="_blank">
      <svg class="badge-icon" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
      WhatsApp
    </a>
    <a class="badge badge-ig" href="https://www.instagram.com/ahamed_asif_07/" target="_blank">
      <svg class="badge-icon" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
      Instagram
    </a>
    <a class="badge badge-gh" href="https://github.com/ahamedasif07" target="_blank">
      <svg class="badge-icon" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
      GitHub
    </a>
  </div>

  <!-- ABOUT -->
  <div style="animation:fadeUp .8s .5s ease both">
    <div class="section-title">about me</div>
    <div class="about-grid">
      <div class="about-items">
        <div class="about-item"><span class="icon">✌️</span><span>Enjoy programming and sharing knowledge with the dev community</span></div>
        <div class="about-item"><span class="icon">❤️</span><span>Love writing clean code and learning new tech every day</span></div>
        <div class="about-item"><span class="icon">📧</span><span>Reach me: <a href="mailto:ahamedasif01729@gmail.com">ahamedasif01729@gmail.com</a></span></div>
        <div class="about-item"><span class="icon">📞</span><span>Phone: <a href="tel:01729149634">01729149634</a></span></div>
        <div class="about-item"><span class="icon">⏱️</span><span>2+ years of full-stack development experience</span></div>
        <div class="about-item"><span class="icon">🌍</span><span>Based in Bangladesh 🇧🇩</span></div>
      </div>
      <div class="fake-gif">
        <div class="code-line" style="color:#61dbfb">const dev = {</div>
        <div class="code-line" style="color:#f0db4f;padding-left:12px">name: "Asif",</div>
        <div class="code-line" style="color:#fe428e;padding-left:12px">stack: "MERN",</div>
        <div class="code-line" style="color:#3fb950;padding-left:12px">open: true</div>
        <div class="code-line" style="color:#61dbfb">}</div>
      </div>
    </div>
  </div>

  <!-- LANGUAGES & FRAMEWORKS -->
  <div class="skills-section">
    <div class="section-title">languages & frameworks</div>
    <div class="pills-wrap">
      <span class="pill pill-js" style="animation-delay:.05s">JavaScript</span>
      <span class="pill pill-ts" style="animation-delay:.1s">TypeScript</span>
      <span class="pill pill-react" style="animation-delay:.15s">React</span>
      <span class="pill pill-next" style="animation-delay:.2s">Next.js</span>
      <span class="pill pill-redux" style="animation-delay:.25s">Redux</span>
      <span class="pill pill-node" style="animation-delay:.3s">Node.js</span>
      <span class="pill pill-express" style="animation-delay:.35s">Express.js</span>
      <span class="pill pill-mongo" style="animation-delay:.4s">MongoDB</span>
      <span class="pill pill-html" style="animation-delay:.45s">HTML5</span>
      <span class="pill pill-css" style="animation-delay:.5s">CSS3</span>
      <span class="pill pill-sass" style="animation-delay:.55s">Sass</span>
      <span class="pill pill-tail" style="animation-delay:.6s">Tailwind CSS</span>
    </div>
  </div>

  <!-- TOOLS -->
  <div class="skills-section">
    <div class="section-title">tools</div>
    <div class="tools-wrap">
      <span class="tool-pill">Git Bash</span>
      <span class="tool-pill">VS Code</span>
      <span class="tool-pill">Figma</span>
      <span class="tool-pill">Postman</span>
      <span class="tool-pill">Vercel</span>
      <span class="tool-pill">Heroku</span>
      <span class="tool-pill">Render</span>
      <span class="tool-pill">OpenAI API</span>
      <span class="tool-pill">Google Sheets</span>
    </div>
  </div>

  <!-- TOP LANGUAGES STATS -->
  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-title">top languages</div>
      <div style="display:flex;flex-direction:column;gap:.6rem;margin-top:.5rem">
        <div>
          <div style="display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:.3rem"><span style="color:#f0db4f">JavaScript</span><span style="color:var(--muted)">42%</span></div>
          <div class="stat-bar-wrap"><div class="stat-bar" style="--w:42%;background:#f0db4f"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:.3rem"><span style="color:#61dbfb">TypeScript</span><span style="color:var(--muted)">24%</span></div>
          <div class="stat-bar-wrap"><div class="stat-bar" style="--w:24%;background:#61dbfb;animation-delay:.2s"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:.3rem"><span style="color:#e34f26">HTML</span><span style="color:var(--muted)">18%</span></div>
          <div class="stat-bar-wrap"><div class="stat-bar" style="--w:18%;background:#e34f26;animation-delay:.4s"></div></div>
        </div>
        <div>
          <div style="display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:.3rem"><span style="color:#1572b6">CSS</span><span style="color:var(--muted)">16%</span></div>
          <div class="stat-bar-wrap"><div class="stat-bar" style="--w:16%;background:#1572b6;animation-delay:.6s"></div></div>
        </div>
      </div>
    </div>
    <div class="stat-card">
      <div class="stat-title">experience & focus</div>
      <div style="display:flex;flex-direction:column;gap:.5rem;margin-top:.5rem">
        <div style="display:flex;justify-content:space-between;font-size:.82rem;border-bottom:1px solid var(--border);padding-bottom:.4rem"><span style="color:var(--muted)">Experience</span><span style="color:var(--green);font-weight:600">2+ Years</span></div>
        <div style="display:flex;justify-content:space-between;font-size:.82rem;border-bottom:1px solid var(--border);padding-bottom:.4rem"><span style="color:var(--muted)">Stack</span><span style="color:var(--blue);font-weight:600">MERN</span></div>
        <div style="display:flex;justify-content:space-between;font-size:.82rem;border-bottom:1px solid var(--border);padding-bottom:.4rem"><span style="color:var(--muted)">Location</span><span style="color:var(--text)">Bangladesh 🇧🇩</span></div>
        <div style="display:flex;justify-content:space-between;font-size:.82rem"><span style="color:var(--muted)">Status</span><span style="color:var(--pink);font-weight:600">Open to Work</span></div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span>Thank you</span> for visiting my profile! 🥰 — Made with ❤️ from Bangladesh
  </div>

</div>
