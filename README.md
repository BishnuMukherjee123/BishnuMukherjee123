<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bishnu Mukherjee — Dev Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --card: #0a0f1e;
    --border: rgba(0,255,180,0.15);
    --green: #00ffb3;
    --cyan: #00e5ff;
    --purple: #9d4edd;
    --text: #e8f0fe;
    --muted: #6a7fa8;
    --glow: 0 0 40px rgba(0,255,180,0.12);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    font-family: 'Syne', sans-serif;
    color: var(--text);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow-x: hidden;
    padding: 40px 20px;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,180,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,180,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    animation: gridShift 20s linear infinite;
    pointer-events: none;
    z-index: 0;
  }

  @keyframes gridShift {
    0% { transform: translateY(0); }
    100% { transform: translateY(50px); }
  }

  /* Floating orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: float 10s ease-in-out infinite;
  }
  .orb1 { width: 400px; height: 400px; background: rgba(0,255,180,0.05); top: -100px; left: -100px; animation-delay: 0s; }
  .orb2 { width: 300px; height: 300px; background: rgba(157,78,221,0.07); bottom: -80px; right: -80px; animation-delay: 4s; }
  .orb3 { width: 200px; height: 200px; background: rgba(0,229,255,0.05); top: 50%; left: 50%; animation-delay: 2s; }

  @keyframes float {
    0%, 100% { transform: translate(0, 0) scale(1); }
    50% { transform: translate(20px, -20px) scale(1.05); }
  }

  /* Main wrapper */
  .profile-wrapper {
    position: relative;
    z-index: 1;
    width: 100%;
    max-width: 820px;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(40px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Header strip */
  .header-strip {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 32px;
    animation: fadeUp 0.8s 0.1s cubic-bezier(0.16,1,0.3,1) both;
  }
  .header-strip .line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
  }
  .header-strip .label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--green);
    letter-spacing: 3px;
    text-transform: uppercase;
    opacity: 0.8;
  }

  /* Profile card */
  .profile-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 24px;
    overflow: hidden;
    box-shadow: var(--glow), 0 40px 100px rgba(0,0,0,0.6);
    position: relative;
  }

  /* Animated top border */
  .profile-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--green), var(--cyan), var(--purple), var(--green), transparent);
    background-size: 200% 100%;
    animation: borderFlow 3s linear infinite;
  }

  @keyframes borderFlow {
    0% { background-position: 0% 50%; }
    100% { background-position: 200% 50%; }
  }

  /* Hero top section */
  .hero {
    padding: 48px 48px 40px;
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 40px;
    align-items: start;
    position: relative;
  }

  /* Avatar */
  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
    animation: fadeUp 0.8s 0.2s cubic-bezier(0.16,1,0.3,1) both;
  }

  .avatar-ring {
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--green), var(--cyan), var(--purple), var(--green));
    animation: spin 4s linear infinite;
    z-index: -1;
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .avatar-inner {
    width: 130px;
    height: 130px;
    border-radius: 50%;
    border: 4px solid var(--card);
    overflow: hidden;
    position: relative;
    z-index: 1;
    background: #1a2035;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .avatar-placeholder {
    font-size: 52px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--green), var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
  }

  /* Status dot */
  .status-dot {
    position: absolute;
    bottom: 8px;
    right: 8px;
    width: 16px;
    height: 16px;
    background: var(--green);
    border-radius: 50%;
    border: 3px solid var(--card);
    z-index: 2;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(0,255,180,0.7); }
    50% { box-shadow: 0 0 0 8px rgba(0,255,180,0); }
  }

  /* Name & info */
  .profile-info {
    animation: fadeUp 0.8s 0.3s cubic-bezier(0.16,1,0.3,1) both;
  }

  .username-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--green);
    letter-spacing: 2px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .username-tag::before {
    content: '@';
    opacity: 0.6;
  }

  .profile-name {
    font-size: 42px;
    font-weight: 800;
    line-height: 1;
    margin-bottom: 14px;
    background: linear-gradient(135deg, #fff 0%, var(--cyan) 60%, var(--green) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: -1px;
  }

  .profile-bio {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
    max-width: 420px;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 300;
    margin-bottom: 24px;
  }

  .profile-bio .highlight {
    color: var(--cyan);
    font-weight: 500;
  }

  /* Tech stack pills */
  .stack-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 24px;
  }

  .pill {
    padding: 5px 14px;
    border-radius: 100px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 1px;
    border: 1px solid;
    transition: all 0.3s ease;
    cursor: default;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) both;
  }

  .pill:nth-child(1) { border-color: rgba(0,255,180,0.4); color: var(--green); animation-delay: 0.35s; }
  .pill:nth-child(2) { border-color: rgba(0,229,255,0.4); color: var(--cyan); animation-delay: 0.4s; }
  .pill:nth-child(3) { border-color: rgba(157,78,221,0.4); color: var(--purple); animation-delay: 0.45s; }
  .pill:nth-child(4) { border-color: rgba(0,255,180,0.4); color: var(--green); animation-delay: 0.5s; }
  .pill:nth-child(5) { border-color: rgba(0,229,255,0.4); color: var(--cyan); animation-delay: 0.55s; }

  .pill:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 20px rgba(0,255,180,0.2);
    background: rgba(0,255,180,0.05);
  }

  /* Social links */
  .social-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    border-radius: 10px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    color: var(--muted);
    text-decoration: none;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    transition: all 0.3s ease;
  }

  .social-btn:hover {
    background: rgba(0,255,180,0.08);
    border-color: rgba(0,255,180,0.3);
    color: var(--green);
    transform: translateY(-2px);
  }

  .social-btn svg { width: 14px; height: 14px; }

  /* Divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 0 48px;
  }

  /* Stats strip */
  .stats-strip {
    padding: 32px 48px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--border);
    border-radius: 0 0 24px 24px;
    position: relative;
    animation: fadeUp 0.8s 0.5s cubic-bezier(0.16,1,0.3,1) both;
  }

  .stat-block {
    background: var(--card);
    padding: 24px 28px;
    text-align: center;
    transition: all 0.3s ease;
    cursor: default;
  }

  .stat-block:first-child { border-radius: 0 0 0 24px; }
  .stat-block:last-child { border-radius: 0 0 24px 0; }

  .stat-block:hover {
    background: rgba(0,255,180,0.04);
  }

  .stat-num {
    font-size: 36px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--green), var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 6px;
    display: block;
  }

  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* Repos section */
  .repos-section {
    margin-top: 24px;
    animation: fadeUp 0.8s 0.6s cubic-bezier(0.16,1,0.3,1) both;
  }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--green);
    letter-spacing: 3px;
    text-transform: uppercase;
    opacity: 0.7;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .repos-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }

  .repo-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    transition: all 0.35s cubic-bezier(0.16,1,0.3,1);
    cursor: pointer;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: block;
  }

  .repo-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,255,180,0.05), transparent 60%);
    opacity: 0;
    transition: opacity 0.3s ease;
  }

  .repo-card:hover {
    border-color: rgba(0,255,180,0.3);
    transform: translateY(-3px);
    box-shadow: 0 12px 40px rgba(0,255,180,0.1);
  }

  .repo-card:hover::before { opacity: 1; }

  .repo-name {
    font-size: 14px;
    font-weight: 700;
    color: var(--cyan);
    margin-bottom: 6px;
    letter-spacing: -0.3px;
  }

  .repo-desc {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    line-height: 1.5;
    margin-bottom: 14px;
  }

  .repo-meta {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .lang-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    display: inline-block;
  }
  .js { background: #f7df1e; }
  .ts { background: #3178c6; }

  .lang-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .stars {
    display: flex;
    align-items: center;
    gap: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    margin-left: auto;
  }

  /* Contribution heatmap */
  .contrib-section {
    margin-top: 24px;
    animation: fadeUp 0.8s 0.7s cubic-bezier(0.16,1,0.3,1) both;
  }

  .contrib-bar-wrap {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
  }

  .contrib-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--text);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .contrib-count {
    color: var(--green);
    font-weight: 600;
  }

  .heatmap {
    display: flex;
    gap: 3px;
    flex-wrap: wrap;
  }

  .heatmap-col {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .heatmap-cell {
    width: 11px;
    height: 11px;
    border-radius: 2px;
    background: rgba(0,255,180,0.05);
    transition: all 0.2s ease;
    cursor: default;
  }

  .heatmap-cell:hover {
    transform: scale(1.4);
  }

  .heatmap-cell.l1 { background: rgba(0,255,180,0.2); }
  .heatmap-cell.l2 { background: rgba(0,255,180,0.4); }
  .heatmap-cell.l3 { background: rgba(0,255,180,0.65); }
  .heatmap-cell.l4 { background: rgba(0,255,180,0.9); box-shadow: 0 0 6px rgba(0,255,180,0.5); }

  /* Location strip */
  .meta-strip {
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
    margin-top: 20px;
    padding: 16px 20px;
    background: rgba(255,255,255,0.02);
    border: 1px solid var(--border);
    border-radius: 12px;
    animation: fadeUp 0.8s 0.8s cubic-bezier(0.16,1,0.3,1) both;
  }

  .meta-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .meta-item svg { width: 13px; height: 13px; color: var(--green); flex-shrink: 0; }

  /* Scanning animation overlay on card */
  .scan-line {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
    opacity: 0.4;
    animation: scan 4s ease-in-out infinite;
    pointer-events: none;
  }

  @keyframes scan {
    0% { top: 0; opacity: 0; }
    10% { opacity: 0.4; }
    90% { opacity: 0.4; }
    100% { top: 100%; opacity: 0; }
  }

  @media (max-width: 600px) {
    .hero { grid-template-columns: 1fr; padding: 32px 24px 28px; gap: 24px; }
    .avatar-inner { width: 100px; height: 100px; }
    .profile-name { font-size: 30px; }
    .stats-strip { padding: 20px 24px; }
    .repos-grid { grid-template-columns: 1fr; }
    .divider { margin: 0 24px; }
    .stat-block:first-child { border-radius: 0; }
    .stat-block:last-child { border-radius: 0 0 24px 24px; }
  }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="profile-wrapper">

  <!-- Header -->
  <div class="header-strip">
    <div class="line"></div>
    <div class="label">Developer Profile</div>
    <div class="line"></div>
  </div>

  <!-- Main card -->
  <div class="profile-card">
    <div class="scan-line"></div>

    <div class="hero">
      <!-- Avatar -->
      <div class="avatar-wrap">
        <div class="avatar-ring"></div>
        <div class="avatar-inner">
          <span class="avatar-placeholder">BM</span>
        </div>
        <div class="status-dot"></div>
      </div>

      <!-- Info -->
      <div class="profile-info">
        <div class="username-tag">BishnuMukherjee123 · he/him</div>
        <h1 class="profile-name">Bishnu<br>Mukherjee</h1>
        <p class="profile-bio">
          <span class="highlight">Full-Stack Dev</span> building with the MERN stack.<br>
          Turning ideas into real-world apps, one commit at a time.
        </p>

        <div class="stack-pills">
          <span class="pill">MongoDB</span>
          <span class="pill">Express</span>
          <span class="pill">React</span>
          <span class="pill">Node.js</span>
          <span class="pill">TypeScript</span>
        </div>

        <div class="social-row">
          <a href="https://twitter.com/BishnuMukherj11" class="social-btn" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.23H2.744l7.737-8.835L1.254 2.25H8.08l4.26 5.632 5.905-5.632zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
            Twitter
          </a>
          <a href="https://linkedin.com/in/bishnu-mukherjee-a235a621a" class="social-btn" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a href="https://github.com/BishnuMukherjee123" class="social-btn" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
            GitHub
          </a>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <!-- Stats strip -->
    <div class="stats-strip">
      <div class="stat-block">
        <span class="stat-num" id="contribNum">0</span>
        <div class="stat-label">contributions</div>
      </div>
      <div class="stat-block">
        <span class="stat-num" id="repoNum">0</span>
        <div class="stat-label">repositories</div>
      </div>
      <div class="stat-block">
        <span class="stat-num" id="followNum">0</span>
        <div class="stat-label">following</div>
      </div>
    </div>
  </div>

  <!-- Repos section -->
  <div class="repos-section">
    <div class="section-label">Pinned Repos</div>
    <div class="repos-grid">
      <a class="repo-card" href="https://github.com/BishnuMukherjee123/Talent-IQ-MERN" target="_blank">
        <div class="repo-name">⚡ Talent-IQ-MERN</div>
        <div class="repo-desc">Code practice + Video Calling Interview Platform</div>
        <div class="repo-meta">
          <span class="lang-dot js"></span>
          <span class="lang-name">JavaScript</span>
          <span class="stars">★ 1</span>
        </div>
      </a>

      <a class="repo-card" href="https://github.com/BishnuMukherjee123/Portfolio-DAZZLE" target="_blank">
        <div class="repo-name">✦ Portfolio-DAZZLE</div>
        <div class="repo-desc">My personal portfolio — built to impress</div>
        <div class="repo-meta">
          <span class="lang-dot ts"></span>
          <span class="lang-name">TypeScript</span>
          <span class="stars">★ 1</span>
        </div>
      </a>

      <a class="repo-card" href="https://github.com/BishnuMukherjee123/echo-pro" target="_blank">
        <div class="repo-name">🔊 echo-pro</div>
        <div class="repo-desc">TypeScript-powered audio project</div>
        <div class="repo-meta">
          <span class="lang-dot ts"></span>
          <span class="lang-name">TypeScript</span>
          <span class="stars">★ 1</span>
        </div>
      </a>

      <a class="repo-card" href="https://github.com/BishnuMukherjee123/chat-project" target="_blank">
        <div class="repo-name">💬 chat-project</div>
        <div class="repo-desc">Real-time chat application</div>
        <div class="repo-meta">
          <span class="lang-dot js"></span>
          <span class="lang-name">JavaScript</span>
          <span class="stars">★ 1</span>
        </div>
      </a>
    </div>
  </div>

  <!-- Contribution heatmap -->
  <div class="contrib-section">
    <div class="contrib-bar-wrap">
      <div class="contrib-title">
        <span>Contribution Activity</span>
        <span class="contrib-count">342 contributions · last year</span>
      </div>
      <div class="heatmap" id="heatmap"></div>
    </div>
  </div>

  <!-- Meta info -->
  <div class="meta-strip">
    <div class="meta-item">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
      Durgapur, West Bengal
    </div>
    <div class="meta-item">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
      BishnuMukherjee123
    </div>
    <div class="meta-item">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
      MERN Stack Dev
    </div>
    <div class="meta-item">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
      Open to work
    </div>
  </div>

</div>

<script>
  // Animate counters
  function animateCounter(el, target, duration = 1500) {
    let start = 0;
    const step = target / (duration / 16);
    const timer = setInterval(() => {
      start += step;
      if (start >= target) { el.textContent = target; clearInterval(timer); }
      else el.textContent = Math.floor(start);
    }, 16);
  }

  setTimeout(() => {
    animateCounter(document.getElementById('contribNum'), 342);
    animateCounter(document.getElementById('repoNum'), 6);
    animateCounter(document.getElementById('followNum'), 2);
  }, 600);

  // Generate heatmap
  const heatmap = document.getElementById('heatmap');
  const levels = [0,0,0,1,2,3,4];
  const weeks = 52;

  for (let w = 0; w < weeks; w++) {
    const col = document.createElement('div');
    col.className = 'heatmap-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      // Make it look like real activity
      const rand = Math.random();
      let lvl = 0;
      if (rand > 0.5) lvl = 1;
      if (rand > 0.7) lvl = 2;
      if (rand > 0.85) lvl = 3;
      if (rand > 0.95) lvl = 4;
      cell.className = 'heatmap-cell' + (lvl ? ` l${lvl}` : '');
      col.appendChild(cell);
    }
    heatmap.appendChild(col);
  }

  // Staggered heatmap cell reveal
  const cells = heatmap.querySelectorAll('.heatmap-cell');
  cells.forEach((cell, i) => {
    cell.style.opacity = '0';
    cell.style.transform = 'scale(0)';
    setTimeout(() => {
      cell.style.transition = 'all 0.3s ease';
      cell.style.opacity = '1';
      cell.style.transform = 'scale(1)';
    }, 800 + i * 2);
  });
</script>

</body>
</html>
