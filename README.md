<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fahad Imaduddin — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f9f8f6;
    --surface: #ffffff;
    --surface2: #f2f0ed;
    --accent: #0ea5e9;
    --accent2: #7c3aed;
    --accent3: #059669;
    --ink: #1a1a2e;
    --ink2: #4a4a6a;
    --ink3: #8888aa;
    --border: #e8e5df;
    --shadow: rgba(10,10,40,0.06);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--ink);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ─── NOISE TEXTURE OVERLAY ─── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0; opacity: 0.4;
  }

  .page {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 32px 100px;
    position: relative; z-index: 1;
  }

  /* ─── HEADER ─── */
  .header {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: start;
    margin-bottom: 64px;
    animation: fadeUp 0.7s ease both;
  }

  .ascii-block {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    line-height: 1.2;
    color: var(--accent);
    letter-spacing: 0;
    white-space: pre;
    opacity: 0.7;
    margin-bottom: 20px;
  }

  .name-tag {
    display: inline-block;
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 6vw, 64px);
    font-weight: 900;
    color: var(--ink);
    line-height: 1;
    margin-bottom: 8px;
  }

  .role-line {
    font-size: 14px;
    color: var(--ink3);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-weight: 500;
    margin-bottom: 24px;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 500;
    font-family: 'DM Mono', monospace;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    border: 1.5px solid var(--border);
    background: var(--surface);
    color: var(--ink2);
  }
  .badge:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px var(--shadow);
  }
  .badge.li { border-color: #0A66C2; color: #0A66C2; }
  .badge.tw { border-color: #000; color: #000; }
  .badge.dev { border-color: #1a1a1a; color: #1a1a1a; }
  .badge.yt { border-color: #FF0000; color: #FF0000; }
  .badge.gm { border-color: #EA4335; color: #EA4335; }

  .header-right {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 12px;
  }

  .views-pill {
    background: linear-gradient(135deg, #e0f2fe, #f0e6ff);
    border: 1px solid #bfdbfe;
    border-radius: 100px;
    padding: 8px 16px;
    font-size: 12px;
    font-family: 'DM Mono', monospace;
    color: var(--accent2);
    font-weight: 500;
  }

  /* ─── SECTION LABEL ─── */
  .section-label {
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink3);
    font-weight: 600;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ─── ABOUT CARD ─── */
  .about-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    margin-bottom: 48px;
    box-shadow: 0 2px 16px var(--shadow);
    animation: fadeUp 0.7s 0.1s ease both;
    position: relative;
    overflow: hidden;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .code-block {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    line-height: 2;
    color: var(--ink2);
  }
  .kw { color: #7c3aed; font-weight: 500; }
  .cls { color: #0ea5e9; }
  .str { color: #059669; }
  .prop { color: #db6c00; }
  .cmt { color: var(--ink3); font-style: italic; }
  .arr { color: #e11d48; }

  /* ─── TECH GRID ─── */
  .tech-section {
    margin-bottom: 48px;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .tech-category {
    margin-bottom: 28px;
  }

  .cat-label {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink3);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tech-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .chip {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    border-radius: 8px;
    font-size: 12.5px;
    font-weight: 500;
    border: 1.5px solid;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: default;
  }
  .chip:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 24px var(--shadow);
  }
  .chip-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
  }

  /* Tech colors */
  .c-csharp { background: #f0fdf4; border-color: #86efac; color: #166534; }
  .c-csharp .chip-dot { background: #239120; }
  .c-dotnet { background: #f5f3ff; border-color: #c4b5fd; color: #5b21b6; }
  .c-dotnet .chip-dot { background: #512BD4; }
  .c-sql { background: #fff1f2; border-color: #fca5a5; color: #991b1b; }
  .c-sql .chip-dot { background: #CC2927; }
  .c-react { background: #ecfeff; border-color: #a5f3fc; color: #0e7490; }
  .c-react .chip-dot { background: #61DAFB; }
  .c-next { background: #f8fafc; border-color: #cbd5e1; color: #334155; }
  .c-next .chip-dot { background: #000; }
  .c-ts { background: #eff6ff; border-color: #93c5fd; color: #1e40af; }
  .c-ts .chip-dot { background: #3178C6; }
  .c-js { background: #fefce8; border-color: #fde047; color: #854d0e; }
  .c-js .chip-dot { background: #F7DF1E; }
  .c-angular { background: #fff1f2; border-color: #fca5a5; color: #9f1239; }
  .c-angular .chip-dot { background: #DD0031; }
  .c-azure { background: #eff6ff; border-color: #93c5fd; color: #1d4ed8; }
  .c-azure .chip-dot { background: #0078D4; }
  .c-docker { background: #ecfeff; border-color: #67e8f9; color: #0e7490; }
  .c-docker .chip-dot { background: #2496ED; }
  .c-git { background: #fff7ed; border-color: #fdba74; color: #9a3412; }
  .c-git .chip-dot { background: #F05032; }
  .c-power { background: #faf5ff; border-color: #d8b4fe; color: #6b21a8; }
  .c-power .chip-dot { background: #742774; }
  .c-sp { background: #eff6ff; border-color: #93c5fd; color: #1e3a8a; }
  .c-sp .chip-dot { background: #0078D4; }
  .c-d365 { background: #f0f9ff; border-color: #7dd3fc; color: #0c4a6e; }
  .c-d365 .chip-dot { background: #002050; }

  /* ─── STATS GRID ─── */
  .stats-section {
    margin-bottom: 48px;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    box-shadow: 0 2px 12px var(--shadow);
    position: relative;
    overflow: hidden;
  }
  .stat-card::after {
    content: attr(data-icon);
    position: absolute;
    right: 16px;
    bottom: 12px;
    font-size: 48px;
    opacity: 0.06;
    pointer-events: none;
  }

  .stat-label {
    font-size: 11px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--ink3);
    font-weight: 600;
    margin-bottom: 12px;
  }

  /* ─── CONTRIBUTION GRAPH ─── */
  .contrib-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 3px;
    margin-top: 16px;
  }

  .contrib-col {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .contrib-cell {
    width: 100%;
    aspect-ratio: 1;
    border-radius: 2px;
    transition: transform 0.15s;
    cursor: default;
  }
  .contrib-cell:hover { transform: scale(1.4); }

  .c0 { background: #f0ece4; }
  .c1 { background: #bfdbfe; }
  .c2 { background: #60a5fa; }
  .c3 { background: #2563eb; }
  .c4 { background: #1d4ed8; }

  .contrib-legend {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 11px;
    color: var(--ink3);
    margin-top: 10px;
    justify-content: flex-end;
    font-family: 'DM Mono', monospace;
  }
  .legend-cell {
    width: 11px; height: 11px;
    border-radius: 2px;
  }

  /* ─── STREAK CARD ─── */
  .streak-inner {
    text-align: center;
    padding: 20px 0;
  }
  .streak-number {
    font-family: 'Playfair Display', serif;
    font-size: 64px;
    font-weight: 900;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 4px;
  }
  .streak-label {
    font-size: 12px;
    color: var(--ink3);
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }
  .streak-sub {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--ink3);
    margin-top: 12px;
  }

  /* ─── MINI STATS ─── */
  .mini-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-top: 16px;
  }
  .mini-stat {
    text-align: center;
    padding: 16px 8px;
    background: var(--surface2);
    border-radius: 10px;
    border: 1px solid var(--border);
  }
  .mini-val {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 900;
    color: var(--ink);
    line-height: 1;
  }
  .mini-lbl {
    font-size: 10px;
    color: var(--ink3);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-top: 4px;
    font-weight: 600;
  }

  /* ─── QUOTE ─── */
  .quote-section {
    text-align: center;
    padding: 48px 20px;
    animation: fadeUp 0.7s 0.4s ease both;
  }

  .quote-mark {
    font-family: 'Playfair Display', serif;
    font-size: 80px;
    color: var(--accent);
    opacity: 0.15;
    line-height: 0.6;
    display: block;
    margin-bottom: 16px;
  }

  .quote-text {
    font-family: 'Playfair Display', serif;
    font-size: clamp(16px, 2.5vw, 22px);
    font-style: italic;
    color: var(--ink2);
    max-width: 580px;
    margin: 0 auto 12px;
    line-height: 1.6;
  }

  .quote-author {
    font-size: 12px;
    color: var(--ink3);
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-family: 'DM Mono', monospace;
  }

  .star-cta {
    margin-top: 32px;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    color: white;
    padding: 12px 28px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.04em;
    box-shadow: 0 8px 32px rgba(14,165,233,0.25);
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
  }
  .star-cta:hover {
    transform: translateY(-2px);
    box-shadow: 0 14px 40px rgba(14,165,233,0.35);
  }

  /* ─── DECORATIVE DOTS ─── */
  .dot-cluster {
    position: fixed;
    pointer-events: none;
    z-index: 0;
    opacity: 0.35;
  }
  .dot-cluster svg { display: block; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ─── FLOATING ORBS ─── */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    opacity: 0.12;
  }
  .orb1 { width: 400px; height: 400px; background: #0ea5e9; top: -100px; right: -100px; }
  .orb2 { width: 300px; height: 300px; background: #7c3aed; bottom: 100px; left: -80px; }
  .orb3 { width: 250px; height: 250px; background: #059669; top: 50%; right: 5%; }

  @media (max-width: 600px) {
    .header { grid-template-columns: 1fr; }
    .header-right { align-items: flex-start; }
    .stats-grid { grid-template-columns: 1fr; }
    .contrib-grid { grid-template-columns: repeat(26, 1fr); }
    .ascii-block { font-size: 6px; }
  }
</style>
</head>
<body>

<!-- Orbs -->
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="page">

  <!-- ── HEADER ── -->
  <div class="header">
    <div>
      <div class="ascii-block">███████╗ █████╗ ██╗  ██╗ █████╗ ██████╗
██╔════╝██╔══██╗██║  ██║██╔══██╗██╔══██╗
█████╗  ███████║███████║███████║██║  ██║
██╔══╝  ██╔══██║██╔══██║██╔══██║██║  ██║
██║     ██║  ██║██║  ██║██║  ██║██████╔╝
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═════╝</div>

      <div class="name-tag">Fahad Imaduddin ☁</div>
      <div class="role-line">Backend Developer · Systems Limited, Karachi 🇵🇰</div>

      <div class="badges">
        <a class="badge li" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="badge tw" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.744l7.73-8.835L1.254 2.25H8.08l4.259 5.63zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
          Twitter
        </a>
        <a class="badge dev" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M7.42 10.05c-.18-.16-.46-.23-.84-.23H6l.02 2.44.04 2.45.56-.02c.41 0 .63-.07.83-.26.24-.24.26-.36.26-2.2 0-1.91-.02-1.96-.29-2.18zM0 4.94v14.12h24V4.94H0zM8.56 15.3c-.44.58-1.06.77-2.53.77H4.71V8.53h1.4c1.67 0 2.16.18 2.6.9.27.43.29.6.32 2.57.05 2.23-.02 2.73-.47 3.3zm5.09-5.47h-2.47v1.77h1.52v1.28l-.72.04-.75.03v1.77l1.22.03 1.2.04v1.28h-1.6c-1.53 0-1.6-.01-1.87-.3l-.3-.28v-3.16c0-3.02.01-3.18.25-3.48.23-.31.25-.31 1.88-.31h1.64v1.28zm4.68 5.45c-.17.43-.64.79-1 .79-.18 0-.45-.15-.67-.39-.32-.32-.45-.63-.82-2.08l-.9-3.39-.45-1.67h.76c.4 0 .75.02.75.05 0 .06 1.16 4.54 1.26 4.83.04.15.32-.7.73-2.3l.66-2.52.74-.04c.4-.02.73 0 .73.04 0 .14-1.67 6.38-1.8 6.68z"/></svg>
          Dev.to
        </a>
        <a class="badge yt" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
          YouTube
        </a>
        <a class="badge gm" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.908 1.528-1.147C21.69 2.28 24 3.434 24 5.457z"/></svg>
          Gmail
        </a>
      </div>
    </div>

    <div class="header-right">
      <div class="views-pill">👁 Profile Views · 2.4k</div>
      <img src="https://komarev.com/ghpvc/?username=fahadimaduddin&label=&color=0ea5e9&style=flat" alt="" style="opacity:0;height:0;">
    </div>
  </div>

  <!-- ── ABOUT ── -->
  <div class="section-label">👨‍💻 About Me</div>
  <div class="about-card">
    <div class="code-block">
      <span class="kw">namespace</span> <span class="cls">Fahad</span>.Profile<br>
      {<br>
      &nbsp;&nbsp;<span class="kw">public class</span> <span class="cls">Developer</span><br>
      &nbsp;&nbsp;{<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Name</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"Fahad Imaduddin ☁"</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Role</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"Backend Developer"</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Company</span>&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"Systems Limited, Karachi 🇵🇰"</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string[] <span class="prop">Focus</span>&nbsp;&nbsp; =&gt; <span class="arr">{</span> <span class="str">".NET Core"</span>, <span class="str">"Azure"</span>, <span class="str">"SQL"</span>, <span class="str">"React"</span> <span class="arr">}</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Passion</span>&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"Building scalable cloud-native solutions"</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Fun</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"Part-time gamer 🎮"</span>;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">public</span> string <span class="prop">Contact</span>&nbsp;&nbsp;&nbsp; =&gt; <span class="str">"fahdimaduddin@gmail.com"</span>;<br>
      &nbsp;&nbsp;}<br>
      }
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section-label">🛠️ Tech Stack</div>
  <div class="tech-section">

    <div class="tech-category">
      <div class="cat-label">💙 Backend</div>
      <div class="tech-chips">
        <div class="chip c-csharp"><div class="chip-dot"></div>C#</div>
        <div class="chip c-dotnet"><div class="chip-dot"></div>.NET Core</div>
        <div class="chip c-sql"><div class="chip-dot"></div>SQL Server</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="cat-label">🎨 Frontend</div>
      <div class="tech-chips">
        <div class="chip c-react"><div class="chip-dot"></div>React</div>
        <div class="chip c-next"><div class="chip-dot"></div>Next.js</div>
        <div class="chip c-ts"><div class="chip-dot"></div>TypeScript</div>
        <div class="chip c-js"><div class="chip-dot"></div>JavaScript</div>
        <div class="chip c-angular"><div class="chip-dot"></div>Angular</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="cat-label">☁️ Cloud & DevOps</div>
      <div class="tech-chips">
        <div class="chip c-azure"><div class="chip-dot"></div>Microsoft Azure</div>
        <div class="chip c-docker"><div class="chip-dot"></div>Docker</div>
        <div class="chip c-git"><div class="chip-dot"></div>Git</div>
      </div>
    </div>

    <div class="tech-category">
      <div class="cat-label">🔧 Microsoft Ecosystem</div>
      <div class="tech-chips">
        <div class="chip c-power"><div class="chip-dot"></div>Power Platform</div>
        <div class="chip c-sp"><div class="chip-dot"></div>SharePoint</div>
        <div class="chip c-d365"><div class="chip-dot"></div>Dynamics 365</div>
      </div>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="section-label">📊 GitHub Stats</div>
  <div class="stats-section">
    <div class="stats-grid">

      <!-- Streak -->
      <div class="stat-card" data-icon="🔥">
        <div class="stat-label">Current Streak</div>
        <div class="streak-inner">
          <div class="streak-number">47</div>
          <div class="streak-label">days on fire</div>
          <div class="streak-sub">Jan 21 → Mar 8, 2026</div>
        </div>
        <div class="mini-stats">
          <div class="mini-stat">
            <div class="mini-val">312</div>
            <div class="mini-lbl">Total Days</div>
          </div>
          <div class="mini-stat">
            <div class="mini-val">63</div>
            <div class="mini-lbl">Longest</div>
          </div>
          <div class="mini-stat">
            <div class="mini-val">1.2k</div>
            <div class="mini-lbl">Commits</div>
          </div>
        </div>
      </div>

      <!-- Contribution Graph -->
      <div class="stat-card" data-icon="📈">
        <div class="stat-label">Contribution Graph · 2025–2026</div>
        <div class="contrib-grid" id="grid"></div>
        <div class="contrib-legend">
          Less
          <div class="legend-cell c0"></div>
          <div class="legend-cell c1"></div>
          <div class="legend-cell c2"></div>
          <div class="legend-cell c3"></div>
          <div class="legend-cell c4"></div>
          More
        </div>
      </div>

    </div>
  </div>

  <!-- ── QUOTE ── -->
  <div class="quote-section">
    <span class="quote-mark">"</span>
    <p class="quote-text">Code is like humor. When you have to explain it, it's bad.</p>
    <div class="quote-author">— Cory House</div>
    <div class="star-cta">⭐ Drop a star if my repos helped you!</div>
  </div>

</div>

<script>
  // Generate contribution grid
  const grid = document.getElementById('grid');
  const levels = [0,0,0,1,1,2,2,3,4];

  for (let w = 0; w < 52; w++) {
    const col = document.createElement('div');
    col.className = 'contrib-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      // Weight towards more contributions recently
      const weight = w > 40 ? [0,1,2,3,4] : w > 28 ? [0,0,1,2,3] : [0,0,0,1,2];
      const lvl = weight[Math.floor(Math.random() * weight.length)];
      cell.className = `contrib-cell c${lvl}`;
      col.appendChild(cell);
    }
    grid.appendChild(col);
  }
</script>
</body>
</html>
