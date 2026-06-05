<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Martin Sigala — Cybersecurity Professional</title>
<style>
:root {
  --bg: #0a0f1a;
  --surface: #111827;
  --surface2: #1e2a3a;
  --border: #1e3a5f;
  --accent: #38bdf8;
  --accent2: #34d399;
  --warn: #f87171;
  --yellow: #fbbf24;
  --text: #f1f5f9;
  --muted: #94a3b8;
  --glow: rgba(56,189,248,0.15);
}
* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body { background: var(--bg); color: var(--text); font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; line-height: 1.6; overflow-x: hidden; }

/* ── NAV ── */
nav { position: fixed; top: 0; left: 0; right: 0; z-index: 100; background: rgba(10,15,26,0.92); backdrop-filter: blur(12px); border-bottom: 1px solid var(--border); padding: 0 2rem; height: 60px; display: flex; align-items: center; justify-content: space-between; }
.nav-name { font-weight: 800; font-size: 1rem; color: var(--accent); }
.nav-links { display: flex; gap: 1.8rem; }
.nav-links a { color: var(--muted); font-size: 0.85rem; text-decoration: none; transition: color 0.2s; }
.nav-links a:hover { color: var(--text); }
.nav-hire { background: var(--accent); color: #000 !important; padding: 6px 16px; border-radius: 8px; font-weight: 700; font-size: 0.82rem !important; }
.hamburger { display: none; background: none; border: none; color: var(--text); font-size: 1.4rem; cursor: pointer; }
.mobile-menu { display: none; position: fixed; inset: 60px 0 0; background: var(--surface); z-index: 99; padding: 1.5rem 2rem; flex-direction: column; gap: 1rem; border-bottom: 1px solid var(--border); }
.mobile-menu.open { display: flex; }
.mobile-menu a { color: var(--text); text-decoration: none; font-size: 1rem; padding: 0.5rem 0; border-bottom: 1px solid var(--border); }

/* ── HERO ── */
.hero { min-height: 100vh; display: flex; align-items: center; padding: 7rem 2rem 4rem; position: relative; overflow: hidden; }
.hero-bg { position: absolute; inset: 0; background: radial-gradient(ellipse 70% 60% at 30% 50%, rgba(56,189,248,0.08) 0%, transparent 70%); pointer-events: none; }
.hero-dots { position: absolute; inset: 0; background-image: radial-gradient(rgba(56,189,248,0.08) 1px, transparent 1px); background-size: 32px 32px; pointer-events: none; }
.hero-inner { max-width: 1080px; margin: 0 auto; width: 100%; display: flex; align-items: center; gap: 4rem; flex-wrap: wrap; }
.hero-left { flex: 1; min-width: 280px; }
.hero-tag { display: inline-flex; align-items: center; gap: 6px; background: rgba(56,189,248,0.1); border: 1px solid rgba(56,189,248,0.25); color: var(--accent); padding: 4px 14px; border-radius: 50px; font-size: 0.75rem; margin-bottom: 1.3rem; text-transform: uppercase; letter-spacing: 0.07em; }
.hero-name { font-size: clamp(2.4rem,5vw,4rem); font-weight: 900; line-height: 1.1; margin-bottom: 0.5rem; }
.hero-name span { color: var(--accent); }
.hero-title { font-size: 1.1rem; color: var(--muted); margin-bottom: 1.2rem; font-weight: 500; }
.hero-title strong { color: var(--accent2); }
.hero-desc { color: var(--muted); font-size: 0.95rem; max-width: 520px; margin-bottom: 2rem; line-height: 1.8; }
.hero-btns { display: flex; gap: 0.8rem; flex-wrap: wrap; margin-bottom: 2rem; }
.btn { display: inline-flex; align-items: center; gap: 6px; padding: 11px 22px; border-radius: 9px; font-weight: 700; font-size: 0.88rem; cursor: pointer; border: none; transition: opacity 0.2s, transform 0.15s; text-decoration: none; }
.btn:hover { opacity: 0.85; transform: translateY(-1px); }
.btn-primary { background: var(--accent); color: #000; }
.btn-outline { background: transparent; color: var(--text); border: 1.5px solid var(--border); }
.btn-sm { padding: 7px 16px; font-size: 0.8rem; }
.hero-social { display: flex; gap: 0.8rem; flex-wrap: wrap; }
.social-chip { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 7px 14px; font-size: 0.8rem; color: var(--muted); text-decoration: none; display: flex; align-items: center; gap: 6px; transition: border-color 0.2s, color 0.2s; }
.social-chip:hover { border-color: var(--accent); color: var(--accent); }
.hero-right { flex-shrink: 0; }
.hero-card { background: var(--surface); border: 1px solid var(--border); border-radius: 16px; padding: 1.8rem; width: 280px; box-shadow: 0 0 40px rgba(56,189,248,0.08); }
.hc-avatar { width: 72px; height: 72px; border-radius: 50%; background: linear-gradient(135deg, var(--accent), #6366f1); display: flex; align-items: center; justify-content: center; font-size: 2rem; margin-bottom: 1rem; border: 3px solid var(--border); }
.hc-name { font-weight: 800; font-size: 1.05rem; margin-bottom: 2px; }
.hc-role { color: var(--accent); font-size: 0.78rem; font-weight: 600; margin-bottom: 1rem; }
.hc-stats { display: flex; flex-direction: column; gap: 0.6rem; }
.hc-stat { display: flex; align-items: center; gap: 0.6rem; font-size: 0.8rem; color: var(--muted); }
.hc-stat .dot { width: 7px; height: 7px; border-radius: 50%; background: var(--accent2); flex-shrink: 0; }
.hc-stat .dot.yellow { background: var(--yellow); }
.hc-stat .dot.blue { background: var(--accent); }

/* ── SECTIONS ── */
section { padding: 5rem 2rem; }
.section-inner { max-width: 1080px; margin: 0 auto; }
.section-label { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 0.1em; color: var(--accent); font-weight: 700; margin-bottom: 0.5rem; }
.section-title { font-size: clamp(1.6rem,3vw,2.2rem); font-weight: 800; margin-bottom: 0.6rem; }
.section-sub { color: var(--muted); font-size: 0.92rem; max-width: 540px; margin-bottom: 2.5rem; }
.divider { border: none; border-top: 1px solid var(--border); margin: 0; }

/* ── ABOUT ── */
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; align-items: start; }
.about-text p { color: var(--muted); font-size: 0.92rem; margin-bottom: 1rem; line-height: 1.8; }
.about-text p strong { color: var(--text); }
.about-highlights { display: flex; flex-direction: column; gap: 0.8rem; }
.about-highlight { background: var(--surface); border: 1px solid var(--border); border-left: 3px solid var(--accent); border-radius: 0 10px 10px 0; padding: 0.9rem 1.1rem; }
.about-highlight .ah-label { font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.07em; color: var(--accent); font-weight: 700; margin-bottom: 2px; }
.about-highlight .ah-val { font-size: 0.88rem; font-weight: 600; }

/* ── SKILLS ── */
.skills-section { background: var(--surface); }
.skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 0.9rem; }
.skill-card { background: var(--bg); border: 1px solid var(--border); border-radius: 10px; padding: 1rem 1.1rem; display: flex; align-items: center; gap: 0.8rem; transition: border-color 0.2s; }
.skill-card:hover { border-color: var(--accent); }
.skill-card .sk-icon { font-size: 1.4rem; flex-shrink: 0; }
.skill-card .sk-label { font-size: 0.85rem; font-weight: 600; }
.skill-card .sk-sub { font-size: 0.7rem; color: var(--muted); }

/* ── EXPERIENCE ── */
.exp-timeline { position: relative; padding-left: 1.5rem; }
.exp-timeline::before { content: ''; position: absolute; left: 0; top: 8px; bottom: 8px; width: 2px; background: var(--border); }
.exp-item { position: relative; margin-bottom: 2.5rem; }
.exp-item::before { content: ''; position: absolute; left: -1.5rem; top: 8px; width: 10px; height: 10px; border-radius: 50%; background: var(--accent); border: 2px solid var(--bg); transform: translateX(-4px); }
.exp-item .ei-header { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 0.5rem; }
.exp-item .ei-role { font-weight: 800; font-size: 1rem; }
.exp-item .ei-date { font-size: 0.75rem; color: var(--muted); background: var(--surface); border: 1px solid var(--border); padding: 2px 10px; border-radius: 50px; }
.exp-item .ei-org { color: var(--accent); font-size: 0.85rem; font-weight: 600; margin-bottom: 0.7rem; }
.exp-item ul { padding-left: 1.1rem; }
.exp-item ul li { color: var(--muted); font-size: 0.85rem; margin-bottom: 5px; }
.exp-item ul li strong { color: var(--text); }

/* ── PROJECTS ── */
.projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1.2rem; }
.proj-card { background: var(--surface); border: 1px solid var(--border); border-radius: 14px; padding: 1.5rem; transition: border-color 0.2s, transform 0.15s; }
.proj-card:hover { border-color: var(--accent); transform: translateY(-2px); }
.proj-card .pc-icon { font-size: 1.8rem; margin-bottom: 0.7rem; }
.proj-card h3 { font-size: 0.97rem; font-weight: 800; margin-bottom: 0.5rem; }
.proj-card p { color: var(--muted); font-size: 0.83rem; margin-bottom: 0.9rem; line-height: 1.6; }
.proj-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-bottom: 1rem; }
.proj-tags span { background: rgba(56,189,248,0.08); border: 1px solid rgba(56,189,248,0.2); color: var(--accent); border-radius: 50px; padding: 2px 9px; font-size: 0.68rem; }
.proj-link { color: var(--accent); font-size: 0.8rem; text-decoration: none; display: inline-flex; align-items: center; gap: 4px; }
.proj-link:hover { text-decoration: underline; }

/* ── CERTIFICATIONS ── */
.certs-section { background: var(--surface); }
.certs-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 1rem; }
.cert-card { background: var(--bg); border: 1.5px solid var(--border); border-radius: 12px; padding: 1.2rem; display: flex; gap: 0.9rem; align-items: flex-start; }
.cert-card.done { border-color: rgba(52,211,153,0.35); }
.cert-card.active { border-color: rgba(251,191,36,0.35); }
.cert-card .cc-icon { font-size: 1.8rem; flex-shrink: 0; }
.cert-card .cc-name { font-weight: 700; font-size: 0.9rem; margin-bottom: 2px; }
.cert-card .cc-status { font-size: 0.72rem; font-weight: 700; }
.cert-card.done .cc-status { color: var(--accent2); }
.cert-card.active .cc-status { color: var(--yellow); }
.cert-card .cc-desc { color: var(--muted); font-size: 0.75rem; margin-top: 3px; }

/* ── CONTACT ── */
.contact-section { text-align: center; }
.contact-box { background: var(--surface); border: 1px solid var(--border); border-radius: 16px; padding: 3rem 2rem; max-width: 600px; margin: 0 auto; position: relative; overflow: hidden; }
.contact-box::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(56,189,248,0.07) 0%, transparent 70%); pointer-events: none; }
.contact-box h2 { font-size: 1.8rem; font-weight: 800; margin-bottom: 0.5rem; }
.contact-box p { color: var(--muted); font-size: 0.92rem; margin-bottom: 2rem; }
.contact-links { display: flex; gap: 0.8rem; justify-content: center; flex-wrap: wrap; }
.contact-link { background: var(--bg); border: 1.5px solid var(--border); border-radius: 10px; padding: 0.8rem 1.3rem; font-size: 0.85rem; font-weight: 600; display: flex; align-items: center; gap: 0.5rem; cursor: pointer; text-decoration: none; color: var(--text); transition: border-color 0.2s, color 0.2s; }
.contact-link:hover { border-color: var(--accent); color: var(--accent); }

/* ── FOOTER ── */
footer { border-top: 1px solid var(--border); padding: 1.5rem 2rem; text-align: center; }
footer p { font-size: 0.78rem; color: var(--muted); }
footer a { color: var(--accent); text-decoration: none; }

/* ── METRICS BAR ── */
.metrics-bar { background: linear-gradient(135deg, rgba(56,189,248,0.08), rgba(52,211,153,0.06)); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); padding: 2rem; }
.metrics-inner { max-width: 1080px; margin: 0 auto; display: flex; justify-content: space-around; flex-wrap: wrap; gap: 1.5rem; text-align: center; }
.metric { }
.metric-num { font-size: 2.2rem; font-weight: 900; color: var(--accent); line-height: 1; }
.metric-label { font-size: 0.75rem; color: var(--muted); margin-top: 4px; }

/* ── CURRENTLY LEARNING ── */
.learning-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 1rem; }
.learning-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 1.2rem; display: flex; gap: 0.9rem; align-items: flex-start; transition: border-color 0.2s; }
.learning-card:hover { border-color: var(--accent); }
.learning-card .lc-icon { font-size: 1.6rem; flex-shrink: 0; }
.learning-card .lc-title { font-weight: 700; font-size: 0.88rem; margin-bottom: 2px; }
.learning-card .lc-desc { color: var(--muted); font-size: 0.78rem; }
.learning-card .lc-status { display: inline-block; margin-top: 5px; font-size: 0.68rem; font-weight: 700; padding: 2px 8px; border-radius: 50px; background: rgba(251,191,36,0.1); color: var(--yellow); border: 1px solid rgba(251,191,36,0.25); }

/* ── RESPONSIVE ── */
@media(max-width:768px) {
  nav { padding: 0 1rem; }
  .nav-links { display: none; }
  .hamburger { display: block; }
  .about-grid { grid-template-columns: 1fr; }
  .hero-inner { gap: 2rem; }
  .hero-right { display: none; }
  section { padding: 3.5rem 1rem; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-name">Martin Sigala</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#projects">Projects</a>
    <a href="#certifications">Certs</a>
    <a href="#contact">Contact</a>
  </div>
  <button class="hamburger" onclick="document.getElementById('mob').classList.toggle('open')">☰</button>
</nav>

<!-- MOBILE MENU -->
<div class="mobile-menu" id="mob">
  <a href="#about" onclick="document.getElementById('mob').classList.remove('open')">About</a>
  <a href="#skills" onclick="document.getElementById('mob').classList.remove('open')">Skills</a>
  <a href="#experience" onclick="document.getElementById('mob').classList.remove('open')">Experience</a>
  <a href="#projects" onclick="document.getElementById('mob').classList.remove('open')">Projects</a>
  <a href="#certifications" onclick="document.getElementById('mob').classList.remove('open')">Certifications</a>
  <a href="#contact" onclick="document.getElementById('mob').classList.remove('open')" style="color:var(--accent);font-weight:700">Contact →</a>
</div>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-dots"></div>
  <div class="hero-inner">
    <div class="hero-left">
      <div class="hero-tag">🛡️ Open to Opportunities</div>
      <h1 class="hero-name">Martin<br><span>Sigala</span></h1>
      <div class="hero-title">Cybersecurity Professional · <strong>SOC Analyst</strong></div>
      <p class="hero-desc">IT professional with 5+ years of experience and a B.S. in Information Technology & Cybersecurity. Completed a hands-on SOC internship working with Microsoft Sentinel, Tenable, KQL, and Microsoft Defender for Endpoint in a live enterprise environment.</p>
      <div class="hero-social">
        <a href="https://www.linkedin.com/in/martin-sigala-b56177239/" target="_blank" class="social-chip">in LinkedIn</a>
        <a href="https://github.com/martinsigala32" target="_blank" class="social-chip">🐙 GitHub</a>
        <a href="https://martinsigala32.github.io/Cybersafe" target="_blank" class="social-chip">🛡️ CyberSafe</a>
        <a href="mailto:martinsigala804@gmail.com" class="social-chip">✉️ Email</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-card">
        <div class="hc-avatar">🛡️</div>
        <div class="hc-name">Martin Sigala</div>
        <div class="hc-role">Cybersecurity Professional</div>
        <div class="hc-stats">
          <div class="hc-stat"><div class="dot blue"></div>5+ Years IT Experience</div>
          <div class="hc-stat"><div class="dot"></div>SOC Analyst Internship</div>
          <div class="hc-stat"><div class="dot"></div>Microsoft Sentinel · KQL</div>
          <div class="hc-stat"><div class="dot"></div>Tenable · Defender for Endpoint</div>
          <div class="hc-stat"><div class="dot yellow"></div>Security+ — Expected 2026</div>
          <div class="hc-stat"><div class="dot yellow"></div>GCR — In Progress</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- METRICS BAR -->
<div class="metrics-bar">
  <div class="metrics-inner">
    <div class="metric"><div class="metric-num" data-target="100" data-suffix="%">0%</div><div class="metric-label">Critical Vulnerabilities Reduced</div></div>
    <div class="metric"><div class="metric-num" data-target="5" data-suffix="+">0+</div><div class="metric-label">Years IT Experience</div></div>
    <div class="metric"><div class="metric-num" data-target="500" data-suffix="+">0+</div><div class="metric-label">Endpoints Supported</div></div>
    <div class="metric"><div class="metric-num" data-target="4">0</div><div class="metric-label">Cybersecurity Projects</div></div>
    <div class="metric"><div class="metric-num" data-target="2">0</div><div class="metric-label">Certifications Completed</div></div>
  </div>
</div>

<hr class="divider">

<!-- ABOUT -->
<section id="about">
  <div class="section-inner">
    <div class="section-label">About Me</div>
    <div class="section-title">Who I Am</div>
    <div class="about-grid">
      <div class="about-text">
        <p>I'm a cybersecurity professional based in Riverside County, CA with a passion for defending organizations against modern threats. My background combines <strong>5+ years of hands-on IT experience</strong> with focused cybersecurity training and real SOC work.</p>
        <p>I completed a cybersecurity internship at <strong>The Cyber Range</strong> — a live SOC environment led by industry educator Josh Madakor — where I worked with the same enterprise security tools used by Fortune 500 companies. I investigated real alerts, hunted threats, managed vulnerabilities, and automated remediations.</p>
        <p>I stay current daily through <strong>CyberWire Daily</strong> and <strong>Simply Cyber's Daily Threat Brief</strong>, and I built <strong>CyberSafe</strong> — a public cybersecurity awareness platform — to demonstrate both my technical skills and my ability to communicate security concepts clearly.</p>
        <p>I'm actively seeking <strong>SOC Analyst, Junior Security Analyst, or Vulnerability Management</strong> roles where I can contribute from day one.</p>
      </div>
      <div class="about-highlights">
        <div class="about-highlight">
          <div class="ah-label">Degree</div>
          <div class="ah-val">B.S. Information Technology & Cybersecurity — University of Phoenix, 2021</div>
        </div>
        <div class="about-highlight" style="border-left-color:var(--accent2)">
          <div class="ah-label">Internship</div>
          <div class="ah-val">SOC Analyst Intern — The Cyber Range (Josh Madakor), 2025</div>
        </div>
        <div class="about-highlight" style="border-left-color:var(--yellow)">
          <div class="ah-label">IT Experience</div>
          <div class="ah-val">5+ years — Networking, Systems, Infrastructure, Endpoint Support</div>
        </div>
        <div class="about-highlight">
          <div class="ah-label">Location</div>
          <div class="ah-val">Riverside County, California</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- SKILLS -->
<section id="skills" class="skills-section">
  <div class="section-inner">
    <div class="section-label">Technical Skills</div>
    <div class="section-title">What I Work With</div>
    <div class="skills-grid">
      <div class="skill-card"><div class="sk-icon">🔵</div><div><div class="sk-label">Microsoft Sentinel</div><div class="sk-sub">SIEM · Alert investigation</div></div></div>
      <div class="skill-card"><div class="sk-icon">🔍</div><div><div class="sk-label">KQL</div><div class="sk-sub">Threat hunting · Log analysis</div></div></div>
      <div class="skill-card"><div class="sk-icon">🛡️</div><div><div class="sk-label">Microsoft Defender</div><div class="sk-sub">EDR · Endpoint detection</div></div></div>
      <div class="skill-card"><div class="sk-icon">🔎</div><div><div class="sk-label">Tenable</div><div class="sk-sub">Vulnerability management</div></div></div>
      <div class="skill-card"><div class="sk-icon">☁️</div><div><div class="sk-label">Azure VMs</div><div class="sk-sub">VM deployment · Log Analytics</div></div></div>
      <div class="skill-card"><div class="sk-icon">⚙️</div><div><div class="sk-label">PowerShell</div><div class="sk-sub">Automation · STIG remediation</div></div></div>
      <div class="skill-card"><div class="sk-icon">🖥️</div><div><div class="sk-label">BASH Scripting</div><div class="sk-sub">Linux automation</div></div></div>
      <div class="skill-card"><div class="sk-icon">📋</div><div><div class="sk-label">DISA STIG</div><div class="sk-sub">Compliance · Hardening</div></div></div>
      <div class="skill-card"><div class="sk-icon">🔟</div><div><div class="sk-label">OWASP Top 10</div><div class="sk-sub">Web security risks</div></div></div>
      <div class="skill-card"><div class="sk-icon">📜</div><div><div class="sk-label">NIST CSF</div><div class="sk-sub">Cybersecurity Framework</div></div></div>
      <div class="skill-card"><div class="sk-icon">⚖️</div><div><div class="sk-label">Compliance</div><div class="sk-sub">PCI-DSS · GDPR · HIPAA</div></div></div>
      <div class="skill-card"><div class="sk-icon">🌐</div><div><div class="sk-label">Networking & IT</div><div class="sk-sub">5+ years hands-on</div></div></div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-inner">
    <div class="section-label">Experience</div>
    <div class="section-title">Where I've Worked</div>
    <div class="exp-timeline">

      <div class="exp-item">
        <div class="ei-header">
          <div class="ei-role">Cybersecurity Support Analyst — Vulnerability Management & SecOps Intern</div>
          <div class="ei-date">2025 · Completed</div>
        </div>
        <div class="ei-org">The Cyber Range — Josh Madakor · Remote</div>
        <ul>
          <li>Conducted vulnerability scans and implemented <strong>PowerShell-based remediations</strong> — contributing to a 100% reduction in critical, 90% in high, and 76% in medium vulnerabilities</li>
          <li>Performed vulnerability assessments and risk prioritization using <strong>Tenable</strong> across Windows and Linux environments</li>
          <li>Executed secure configurations and <strong>DISA STIG compliance audits</strong> with Tenable to meet industry standards</li>
          <li>Performed <strong>threat hunting with EDR</strong>, detecting IoCs from brute force attacks, data exfiltration, and ransomware</li>
          <li>Developed <strong>custom detection rules in Microsoft Defender for Endpoint</strong> to automate isolation and investigation</li>
          <li>Reduced brute force incidents by 100% by implementing inbound <strong>NSG/firewall rules</strong></li>
          <li>Created <strong>Microsoft Sentinel dashboards</strong> to monitor logon failures and malicious traffic using threat intelligence</li>
          <li>Wrote <strong>KQL queries</strong> to hunt threats and query logs within SIEM and EDR platforms</li>
        </ul>
      </div>

      <div class="exp-item">
        <div class="ei-header">
          <div class="ei-role">Information Technology Technician III</div>
          <div class="ei-date">Oct 2021 – Present</div>
        </div>
        <div class="ei-org">IT Department · Riverside County</div>
        <ul>
          <li>Provided district-wide networking support — troubleshooting wired/wireless connectivity, switch ports, and IP/DNS conflicts</li>
          <li>Supported <strong>500+ endpoints</strong> with 95%+ successful configuration on first attempt</li>
          <li>Reduced average network downtime per incident by <strong>40%</strong> through proactive troubleshooting</li>
          <li>Resolved <strong>80% of tickets at first contact</strong>, handling up to 100 support tickets monthly</li>
          <li>Performed scheduled system backups with a <strong>99% recovery success rate</strong></li>
          <li>Participated in system upgrades, server migrations, software rollouts, and security policy implementations</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<hr class="divider">

<!-- PROJECTS -->
<section id="projects" style="background:var(--surface)">
  <div class="section-inner">
    <div class="section-label">Projects</div>
    <div class="section-title">What I've Built</div>
    <div class="projects-grid">

      <div class="proj-card">
        <div class="pc-icon">🛡️</div>
        <h3>CyberSafe — Cybersecurity Awareness Platform</h3>
        <p>A full-featured public cybersecurity awareness website with 5 courses, interactive phishing simulation, quiz, certificate, glossary, and dark/light mode. Built entirely with vanilla HTML, CSS, and JavaScript.</p>
        <div class="proj-tags"><span>HTML/CSS/JS</span><span>localStorage</span><span>Responsive</span><span>UX Design</span></div>
        <a href="https://martinsigala32.github.io/Cybersafe" target="_blank" class="proj-link">🔗 View Live →</a>
      </div>

      <div class="proj-card">
        <div class="pc-icon">🔎</div>
        <h3>Vulnerability Management Program</h3>
        <p>Full vulnerability management lifecycle on Azure VMs — scanning with Tenable, prioritizing findings, remediating with PowerShell and BASH, and rescanning to verify. Achieved 100% reduction in critical vulnerabilities.</p>
        <div class="proj-tags"><span>Tenable</span><span>Azure VMs</span><span>PowerShell</span><span>BASH</span></div>
        <a href="https://github.com/martinsigala32/vulnerability-management-program" target="_blank" class="proj-link">🐙 View on GitHub →</a>
      </div>

      <div class="proj-card">
        <div class="pc-icon">🕵️</div>
        <h3>Threat Hunting — Tor Browser Detection</h3>
        <p>Conducted a real threat hunting scenario in Microsoft Sentinel to detect unauthorized Tor Browser usage. Wrote KQL queries, correlated logs, and documented findings in a structured incident report.</p>
        <div class="proj-tags"><span>Microsoft Sentinel</span><span>KQL</span><span>Threat Hunting</span><span>SIEM</span></div>
        <a href="https://github.com/martinsigala32/Threat-Hunting-Scenario" target="_blank" class="proj-link">🐙 View on GitHub →</a>
      </div>

      <div class="proj-card">
        <div class="pc-icon">⚙️</div>
        <h3>STIG Remediation Automation — WN10-AU-000500</h3>
        <p>Identified a failing DISA STIG compliance check, manually remediated it, validated the fix, then automated the remediation with a PowerShell script. Confirmed compliance via Tenable rescan.</p>
        <div class="proj-tags"><span>PowerShell</span><span>DISA STIG</span><span>Tenable</span><span>Compliance</span></div>
        <a href="https://github.com/martinsigala32/STIG-WN10-AU-000500.ps1" target="_blank" class="proj-link">🐙 View on GitHub →</a>
      </div>

    </div>
  </div>
</section>

<hr class="divider">

<!-- CERTIFICATIONS -->
<section id="certifications" class="certs-section">
  <div class="section-inner">
    <div class="section-label">Certifications</div>
    <div class="section-title">Credentials</div>
    <div class="certs-grid">
      <div class="cert-card done">
        <div class="cc-icon">🏆</div>
        <div>
          <div class="cc-name">Google Cybersecurity</div>
          <div class="cc-status">✅ Completed</div>
          <div class="cc-desc">Professional certificate covering threat detection, network security, and security operations.</div>
        </div>
      </div>
      <div class="cert-card done">
        <div class="cc-icon">🏆</div>
        <div>
          <div class="cc-name">TryHackMe — SOC Level 1</div>
          <div class="cc-status">✅ Completed</div>
          <div class="cc-desc">Hands-on SOC training covering SIEM, incident response, threat intelligence, and digital forensics.</div>
        </div>
      </div>
      <div class="cert-card active">
        <div class="cc-icon">📋</div>
        <div>
          <div class="cc-name">CompTIA Security+</div>
          <div class="cc-status">🟡 In Progress — Expected 2026</div>
          <div class="cc-desc">Industry-standard security certification covering threats, cryptography, and network security.</div>
        </div>
      </div>
      <div class="cert-card active">
        <div class="cc-icon">🎯</div>
        <div>
          <div class="cc-name">GIAC Cyber Range (GCR)</div>
          <div class="cc-status">🟡 In Progress</div>
          <div class="cc-desc">Hands-on certification validating real SOC analyst skills from The Cyber Range.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- CURRENTLY LEARNING -->
<section id="learning" style="background:var(--surface)">
  <div class="section-inner">
    <div class="section-label">Always Growing</div>
    <div class="section-title">Currently Learning</div>
    <p class="section-sub">Cybersecurity changes daily. Here's what I'm actively working on right now.</p>
    <div class="learning-grid">
      <div class="learning-card">
        <div class="lc-icon">📋</div>
        <div>
          <div class="lc-title">CompTIA Security+</div>
          <div class="lc-desc">Studying threat management, cryptography, identity management, and network security fundamentals.</div>
          <div class="lc-status">🟡 Expected 2026</div>
        </div>
      </div>
      <div class="learning-card">
        <div class="lc-icon">🎯</div>
        <div>
          <div class="lc-title">GIAC Cyber Range (GCR)</div>
          <div class="lc-desc">Hands-on SOC analyst certification validating real enterprise security skills from The Cyber Range.</div>
          <div class="lc-status">🟡 In Progress</div>
        </div>
      </div>
      <div class="learning-card">
        <div class="lc-icon">🔍</div>
        <div>
          <div class="lc-title">Advanced KQL</div>
          <div class="lc-desc">Deepening my Kusto Query Language skills for more sophisticated threat hunting and detection rule writing in Microsoft Sentinel.</div>
          <div class="lc-status">🟡 Ongoing</div>
        </div>
      </div>
      <div class="learning-card">
        <div class="lc-icon">🎙️</div>
        <div>
          <div class="lc-title">Daily Threat Intelligence</div>
          <div class="lc-desc">Following CyberWire Daily and Simply Cyber's Daily Threat Brief every day to stay current on the evolving threat landscape.</div>
          <div class="lc-status">✅ Daily Habit</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider">

<!-- CONTACT -->
<section id="contact" class="contact-section">
  <div class="section-inner">
    <div class="contact-box">
      <h2>Let's Work Together</h2>
      <p>I'm actively looking for SOC Analyst, Junior Security Analyst, and Vulnerability Management roles. Let's connect.</p>
      <div class="contact-links">
        <a href="mailto:martinsigala804@gmail.com" class="contact-link">✉️ martinsigala804@gmail.com</a>
        <a href="https://www.linkedin.com/in/martin-sigala-b56177239/" target="_blank" class="contact-link">in LinkedIn</a>
        <a href="https://github.com/martinsigala32" target="_blank" class="contact-link">🐙 GitHub</a>
        <a href="https://martinsigala32.github.io/Cybersafe" target="_blank" class="contact-link">🛡️ CyberSafe</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <p>© 2025 Martin Sigala · Cybersecurity Professional · Riverside County, CA · <a href="mailto:martinsigala804@gmail.com">martinsigala804@gmail.com</a></p>
</footer>

<script>
// Animated counters
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (!e.isIntersecting) return;
    e.target.querySelectorAll('[data-target]').forEach(el => {
      const target = parseFloat(el.dataset.target);
      const suffix = el.dataset.suffix || '';
      const duration = 1600;
      const start = performance.now();
      function update(now) {
        const progress = Math.min((now - start) / duration, 1);
        const eased = 1 - Math.pow(1 - progress, 3);
        el.textContent = Math.round(target * eased) + suffix;
        if (progress < 1) requestAnimationFrame(update);
      }
      requestAnimationFrame(update);
    });
    observer.disconnect();
  });
}, { threshold: 0.3 });
const mb = document.querySelector('.metrics-bar');
if (mb) observer.observe(mb);
</script>
</body>
</html>
