<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mohd Affan | Full Stack Developer Profile</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet" />
  
  <style>
    :root {
      --bg-primary: #07090e;
      --bg-secondary: #0d121f;
      --card-bg: rgba(16, 23, 38, 0.65);
      --card-hover: rgba(24, 34, 56, 0.85);
      --card-border: rgba(255, 255, 255, 0.08);
      --card-border-glow: rgba(56, 189, 248, 0.3);
      --accent-cyan: #38bdf8;
      --accent-blue: #3b82f6;
      --accent-purple: #a855f7;
      --accent-pink: #ec4899;
      --accent-emerald: #10b981;
      --text-main: #f1f5f9;
      --text-muted: #94a3b8;
      --text-dim: #64748b;
      --font-sans: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif;
      --font-mono: 'JetBrains Mono', monospace;
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-lg: 20px;
      --radius-xl: 28px;
      --shadow-glow: 0 0 35px -5px rgba(56, 189, 248, 0.25);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: var(--font-sans);
      background-color: var(--bg-primary);
      color: var(--text-main);
      line-height: 1.6;
      overflow-x: hidden;
      min-height: 100vh;
      position: relative;
    }

    /* Background Ambient Glowing Orbs */
    .bg-glow-1 {
      position: fixed;
      top: -150px;
      left: 15%;
      width: 550px;
      height: 550px;
      background: radial-gradient(circle, rgba(56, 189, 248, 0.15) 0%, rgba(0, 0, 0, 0) 70%);
      pointer-events: none;
      z-index: 0;
      filter: blur(50px);
    }

    .bg-glow-2 {
      position: fixed;
      top: 35%;
      right: -100px;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(168, 85, 247, 0.12) 0%, rgba(0, 0, 0, 0) 70%);
      pointer-events: none;
      z-index: 0;
      filter: blur(60px);
    }

    .bg-glow-3 {
      position: fixed;
      bottom: -100px;
      left: 20%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(59, 130, 246, 0.12) 0%, rgba(0, 0, 0, 0) 70%);
      pointer-events: none;
      z-index: 0;
      filter: blur(60px);
    }

    /* Grid pattern overlay */
    .bg-grid {
      position: fixed;
      inset: 0;
      background-image: linear-gradient(to right, rgba(255, 255, 255, 0.02) 1px, transparent 1px),
                        linear-gradient(to bottom, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }

    .container {
      max-width: 1050px;
      margin: 0 auto;
      padding: 40px 24px 80px;
      position: relative;
      z-index: 1;
    }

    /* Top Navigation bar */
    .top-nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 20px;
      background: rgba(13, 18, 31, 0.6);
      border: 1px solid var(--card-border);
      border-radius: 9999px;
      backdrop-filter: blur(12px);
      margin-bottom: 40px;
    }

    .nav-brand {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.9rem;
      font-weight: 600;
      color: var(--text-muted);
      font-family: var(--font-mono);
    }

    .nav-brand span.user {
      color: var(--text-main);
    }

    .nav-status {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.8rem;
      font-weight: 500;
      color: #34d399;
      background: rgba(16, 185, 129, 0.1);
      border: 1px solid rgba(16, 185, 129, 0.2);
      padding: 4px 12px;
      border-radius: 999px;
    }

    .status-dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #10b981;
      box-shadow: 0 0 10px #10b981;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(0.9); }
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    /* View Switcher Tabs */
    .tab-toggle {
      display: inline-flex;
      background: rgba(0, 0, 0, 0.4);
      padding: 4px;
      border-radius: 999px;
      border: 1px solid var(--card-border);
    }

    .tab-btn {
      background: transparent;
      border: none;
      color: var(--text-muted);
      padding: 6px 16px;
      border-radius: 999px;
      font-size: 0.8rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.25s ease;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .tab-btn.active {
      background: linear-gradient(135deg, #2563eb, #38bdf8);
      color: #ffffff;
      box-shadow: 0 2px 10px rgba(56, 189, 248, 0.3);
    }

    /* Hero Section */
    .hero-card {
      background: linear-gradient(180deg, rgba(20, 28, 48, 0.7) 0%, rgba(13, 18, 31, 0.8) 100%);
      border: 1px solid var(--card-border);
      border-radius: var(--radius-xl);
      padding: 48px 36px;
      text-align: center;
      position: relative;
      overflow: hidden;
      box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(16px);
      margin-bottom: 30px;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      top: 0;
      left: 10%;
      right: 10%;
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(56, 189, 248, 0.6), rgba(168, 85, 247, 0.6), transparent);
    }

    .avatar-wrapper {
      position: relative;
      width: 120px;
      height: 120px;
      margin: 0 auto 24px;
    }

    .avatar-img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid rgba(255, 255, 255, 0.15);
      box-shadow: 0 0 30px rgba(56, 189, 248, 0.35);
      transition: transform 0.3s ease;
    }

    .avatar-wrapper:hover .avatar-img {
      transform: scale(1.05);
    }

    .avatar-badge {
      position: absolute;
      bottom: 2px;
      right: 4px;
      background: #10b981;
      border: 2px solid #0d121f;
      width: 20px;
      height: 20px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 11px;
    }

    .hero-badge-pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 16px;
      border-radius: 999px;
      background: rgba(56, 189, 248, 0.08);
      border: 1px solid rgba(56, 189, 248, 0.25);
      color: var(--accent-cyan);
      font-size: 0.85rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      margin-bottom: 16px;
    }

    .hero-title {
      font-size: 3rem;
      font-weight: 800;
      letter-spacing: -1px;
      margin-bottom: 8px;
      line-height: 1.15;
    }

    .gradient-text {
      background: linear-gradient(135deg, #ffffff 30%, #38bdf8 70%, #a855f7 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-subtitle {
      font-size: 1.35rem;
      font-weight: 600;
      color: #93c5fd;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
    }

    .hero-desc {
      color: var(--text-muted);
      max-width: 620px;
      margin: 0 auto 24px;
      font-size: 1rem;
    }

    .views-counter {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: rgba(0, 0, 0, 0.4);
      border: 1px solid var(--card-border);
      border-radius: 999px;
      padding: 6px 14px;
      margin-bottom: 28px;
    }

    .views-counter img {
      height: 22px;
      border-radius: 4px;
      vertical-align: middle;
    }

    .hero-cta-group {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 14px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 11px 22px;
      border-radius: var(--radius-md);
      font-size: 0.92rem;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
      cursor: pointer;
    }

    .btn-primary {
      background: linear-gradient(135deg, #2563eb, #38bdf8);
      color: #ffffff;
      box-shadow: 0 4px 18px rgba(37, 99, 235, 0.4);
      border: none;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(56, 189, 248, 0.5);
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.05);
      color: var(--text-main);
      border: 1px solid var(--card-border);
      backdrop-filter: blur(10px);
    }

    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.1);
      border-color: rgba(255, 255, 255, 0.2);
      transform: translateY(-2px);
    }

    /* Section Header */
    .section-title {
      font-size: 1.5rem;
      font-weight: 700;
      margin: 40px 0 20px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .section-title .icon-box {
      width: 38px;
      height: 38px;
      border-radius: 10px;
      background: rgba(56, 189, 248, 0.12);
      border: 1px solid rgba(56, 189, 248, 0.25);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--accent-cyan);
    }

    /* About Section Grid */
    .about-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 18px;
      margin-bottom: 30px;
    }

    .info-card {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: var(--radius-lg);
      padding: 24px;
      transition: all 0.3s ease;
      backdrop-filter: blur(12px);
      position: relative;
      overflow: hidden;
    }

    .info-card:hover {
      border-color: var(--card-border-glow);
      background: var(--card-hover);
      transform: translateY(-3px);
    }

    .info-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 12px;
    }

    .info-icon {
      width: 32px;
      height: 32px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.1rem;
    }

    .info-title {
      font-size: 1.05rem;
      font-weight: 700;
      color: var(--text-main);
    }

    .info-card p {
      color: var(--text-muted);
      font-size: 0.92rem;
      line-height: 1.5;
    }

    .tag-container {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 12px;
    }

    .tag {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.08);
      color: #cbd5e1;
      font-size: 0.76rem;
      font-weight: 600;
      padding: 4px 10px;
      border-radius: 6px;
      font-family: var(--font-mono);
    }

    /* Social Connect Bar */
    .social-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
      margin-bottom: 35px;
    }

    .social-card {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 14px 18px;
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: var(--radius-md);
      color: var(--text-main);
      text-decoration: none;
      transition: all 0.25s ease;
      backdrop-filter: blur(12px);
    }

    .social-card:hover {
      transform: translateY(-3px);
      border-color: rgba(255, 255, 255, 0.2);
    }

    .social-card.linkedin:hover {
      border-color: #0077b5;
      background: rgba(0, 119, 181, 0.12);
      box-shadow: 0 4px 20px rgba(0, 119, 181, 0.2);
    }

    .social-card.instagram:hover {
      border-color: #e4405f;
      background: rgba(228, 64, 95, 0.12);
      box-shadow: 0 4px 20px rgba(228, 64, 95, 0.2);
    }

    .social-card.discord:hover {
      border-color: #5865f2;
      background: rgba(88, 101, 242, 0.12);
      box-shadow: 0 4px 20px rgba(88, 101, 242, 0.2);
    }

    .social-card.portfolio:hover {
      border-color: #38bdf8;
      background: rgba(56, 189, 248, 0.12);
      box-shadow: 0 4px 20px rgba(56, 189, 248, 0.2);
    }

    .social-card img {
      width: 28px;
      height: 28px;
      object-fit: contain;
    }

    .social-meta span.title {
      font-size: 0.88rem;
      font-weight: 700;
      display: block;
    }

    .social-meta span.handle {
      font-size: 0.78rem;
      color: var(--text-dim);
      display: block;
    }

    /* Skills Categories */
    .skills-category {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: var(--radius-lg);
      padding: 24px;
      margin-bottom: 20px;
      backdrop-filter: blur(12px);
    }

    .skills-category-title {
      font-size: 0.95rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      color: var(--text-muted);
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .skill-chip {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid rgba(255, 255, 255, 0.08);
      padding: 8px 16px;
      border-radius: var(--radius-md);
      text-decoration: none;
      color: var(--text-main);
      font-size: 0.9rem;
      font-weight: 600;
      transition: all 0.25s ease;
    }

    .skill-chip img {
      width: 22px;
      height: 22px;
      object-fit: contain;
      transition: transform 0.25s ease;
    }

    .skill-chip:hover {
      background: rgba(255, 255, 255, 0.09);
      border-color: var(--accent-cyan);
      transform: translateY(-2px);
      box-shadow: 0 4px 14px rgba(56, 189, 248, 0.2);
    }

    .skill-chip:hover img {
      transform: scale(1.15) rotate(5deg);
    }

    /* Stats Grid */
    .stats-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
      gap: 20px;
      margin-bottom: 30px;
    }

    .stat-card {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: var(--radius-lg);
      padding: 20px;
      text-align: center;
      backdrop-filter: blur(12px);
      transition: all 0.3s ease;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .stat-card:hover {
      border-color: var(--card-border-glow);
      transform: translateY(-3px);
      box-shadow: var(--shadow-glow);
    }

    .stat-card img {
      width: 100%;
      height: auto;
      max-width: 480px;
      border-radius: 10px;
      display: block;
    }

    /* Markdown Export Drawer / Modal */
    .readme-code-wrapper {
      background: #090d16;
      border: 1px solid var(--card-border);
      border-radius: var(--radius-lg);
      padding: 24px;
      position: relative;
      margin-top: 20px;
    }

    .code-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 16px;
      padding-bottom: 12px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .code-title {
      font-size: 0.9rem;
      font-family: var(--font-mono);
      color: var(--text-muted);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .code-title span.dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #38bdf8;
    }

    .copy-btn {
      background: rgba(56, 189, 248, 0.12);
      border: 1px solid rgba(56, 189, 248, 0.3);
      color: var(--accent-cyan);
      font-size: 0.82rem;
      font-weight: 600;
      padding: 6px 14px;
      border-radius: 8px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.2s ease;
    }

    .copy-btn:hover {
      background: var(--accent-cyan);
      color: #000000;
    }

    pre.markdown-code {
      background: #05070c;
      padding: 16px;
      border-radius: var(--radius-md);
      color: #e2e8f0;
      font-family: var(--font-mono);
      font-size: 0.85rem;
      overflow-x: auto;
      max-height: 480px;
      line-height: 1.6;
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    /* Toast Notification */
    .toast {
      position: fixed;
      bottom: 24px;
      right: 24px;
      background: linear-gradient(135deg, #10b981, #059669);
      color: #ffffff;
      padding: 12px 20px;
      border-radius: var(--radius-md);
      font-weight: 600;
      font-size: 0.9rem;
      box-shadow: 0 10px 25px rgba(16, 185, 129, 0.4);
      display: flex;
      align-items: center;
      gap: 10px;
      transform: translateY(100px);
      opacity: 0;
      transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
      z-index: 9999;
    }

    .toast.show {
      transform: translateY(0);
      opacity: 1;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 40px 0 20px;
      border-top: 1px solid var(--card-border);
      color: var(--text-dim);
      font-size: 0.85rem;
      margin-top: 60px;
    }

    footer a {
      color: var(--accent-cyan);
      text-decoration: none;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .hero-title {
        font-size: 2.2rem;
      }
      .hero-card {
        padding: 32px 20px;
      }
      .top-nav {
        flex-direction: column;
        gap: 12px;
        border-radius: var(--radius-lg);
      }
      .stats-container {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

  <!-- Ambient lighting -->
  <div class="bg-glow-1"></div>
  <div class="bg-glow-2"></div>
  <div class="bg-glow-3"></div>
  <div class="bg-grid"></div>

  <div class="container">

    <!-- Top Floating Navigation -->
    <header class="top-nav">
      <div class="nav-brand">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
        </svg>
        <span>github.com/<span class="user">mohdaffan01</span></span>
      </div>

      <div class="nav-status">
        <span class="status-dot"></span>
        Available for Full-time Roles & Projects
      </div>

      <div class="tab-toggle">
        <button class="tab-btn active" id="btn-web-view" onclick="switchView('web')">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/><path d="M2 12h20"/></svg>
          Web Preview
        </button>
        <button class="tab-btn" id="btn-md-view" onclick="switchView('markdown')">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
          GitHub README.md
        </button>
      </div>
    </header>

    <!-- MAIN WEB PREVIEW VIEW -->
    <main id="web-view-section">
      
      <!-- HERO CARD -->
      <section class="hero-card">
        <div class="avatar-wrapper">
          <img src="https://avatars.githubusercontent.com/mohdaffan01" alt="Mohd Affan Avatar" class="avatar-img" onerror="this.src='https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg'" />
          <div class="avatar-badge" title="Online">⚡</div>
        </div>

        <div class="hero-badge-pill">
          ✨ Welcome to my universe
        </div>

        <h1 class="hero-title">
          Hi, I'm <span class="gradient-text">Mohd Affan</span> 👋
        </h1>

        <div class="hero-subtitle">
          <span>Full Stack Developer</span>
          <span>•</span>
          <span style="color: var(--accent-purple);">MERN Specialist</span>
          <span>•</span>
          <span style="color: var(--accent-emerald);">DSA & System Design</span>
        </div>

        <p class="hero-desc">
          Passionate software engineer building robust, scalable full-stack applications and solving complex algorithmic challenges with high-performance code.
        </p>

        <div class="views-counter">
          <img src="https://komarev.com/ghpvc/?username=mohdaffan01&label=Profile%20views&color=0e75b6&style=flat-square" alt="Profile Views" />
        </div>

        <div class="hero-cta-group">
          <a href="https://affan-personalportfolio.netlify.app/" target="_blank" rel="noreferrer" class="btn btn-primary">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
            Live Portfolio
          </a>
          <a href="mailto:mohdaffan338@gmail.com" class="btn btn-secondary">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
            Email Me
          </a>
          <a href="https://linkedin.com/in/mohdaffan01" target="_blank" rel="noreferrer" class="btn btn-secondary">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            LinkedIn
          </a>
        </div>
      </section>

      <!-- ABOUT ME CARDS -->
      <h2 class="section-title">
        <span class="icon-box">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
        </span>
        About Me
      </h2>

      <div class="about-grid">
        <div class="info-card">
          <div class="info-header">
            <div class="info-icon" style="background: rgba(56, 189, 248, 0.15); color: #38bdf8;">🚀</div>
            <div class="info-title">Full Stack Specialist</div>
          </div>
          <p>
            Specialized in crafting performant end-to-end architectures using the modern <strong>MERN Stack</strong>, RESTful APIs, and cloud services.
          </p>
          <div class="tag-container">
            <span class="tag">React</span>
            <span class="tag">Node.js</span>
            <span class="tag">Express</span>
            <span class="tag">MongoDB</span>
          </div>
        </div>

        <div class="info-card">
          <div class="info-header">
            <div class="info-icon" style="background: rgba(168, 85, 247, 0.15); color: #c084fc;">🧠</div>
            <div class="info-title">Systems & Algorithms</div>
          </div>
          <p>
            Strong foundation in <strong>Data Structures & Algorithms (DSA)</strong>, Object-Oriented Programming, and scalable <strong>System Design</strong> principles.
          </p>
          <div class="tag-container">
            <span class="tag">Java</span>
            <span class="tag">C</span>
            <span class="tag">MySQL</span>
            <span class="tag">Docker</span>
          </div>
        </div>

        <div class="info-card">
          <div class="info-header">
            <div class="info-icon" style="background: rgba(16, 185, 129, 0.15); color: #34d399;">🌐</div>
            <div class="info-title">Let's Collaborate</div>
          </div>
          <p>
            Always excited to discuss high-impact software projects, open-source initiatives, and engineering opportunities.
          </p>
          <div class="tag-container">
            <span class="tag">affan-personalportfolio.netlify.app</span>
            <span class="tag">mohdaffan338@gmail.com</span>
          </div>
        </div>
      </div>

      <!-- CONNECT WITH ME -->
      <h2 class="section-title">
        <span class="icon-box">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><line x1="19" y1="8" x2="19" y2="14"/><line x1="22" y1="11" x2="16" y2="11"/></svg>
        </span>
        Connect With Me
      </h2>

      <div class="social-grid">
        <a href="https://linkedin.com/in/mohdaffan01" target="_blank" rel="noreferrer" class="social-card linkedin">
          <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn" />
          <div class="social-meta">
            <span class="title">LinkedIn</span>
            <span class="handle">/in/mohdaffan01</span>
          </div>
        </a>

        <a href="https://instagram.com/themdaffan" target="_blank" rel="noreferrer" class="social-card instagram">
          <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="Instagram" />
          <div class="social-meta">
            <span class="title">Instagram</span>
            <span class="handle">@themdaffan</span>
          </div>
        </a>

        <a href="https://discord.gg/mdaffan01" target="_blank" rel="noreferrer" class="social-card discord">
          <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/discord.svg" alt="Discord" />
          <div class="social-meta">
            <span class="title">Discord</span>
            <span class="handle">mdaffan01</span>
          </div>
        </a>

        <a href="https://affan-personalportfolio.netlify.app/" target="_blank" rel="noreferrer" class="social-card portfolio">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#38bdf8" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/><path d="M2 12h20"/></svg>
          <div class="social-meta">
            <span class="title">Portfolio</span>
            <span class="handle">affan-personalportfolio</span>
          </div>
        </a>
      </div>

      <!-- SKILLS & TECH STACK -->
      <h2 class="section-title">
        <span class="icon-box">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 2 7 12 12 22 7 12 2"/><polyline points="2 17 12 22 22 17"/><polyline points="2 12 12 17 22 12"/></svg>
        </span>
        Tech Stack & Skills
      </h2>

      <!-- Frontend -->
      <div class="skills-category">
        <div class="skills-category-title">
          <span>🎨 Frontend & Mobile Development</span>
        </div>
        <div class="skills-grid">
          <a href="https://reactjs.org/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" alt="React" />
            <span>React</span>
          </a>
          <a href="https://reactnative.dev/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://reactnative.dev/img/header_logo.svg" alt="React Native" />
            <span>React Native</span>
          </a>
          <a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="TypeScript" />
            <span>TypeScript</span>
          </a>
          <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript" />
            <span>JavaScript</span>
          </a>
          <a href="https://tailwindcss.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="Tailwind CSS" />
            <span>Tailwind CSS</span>
          </a>
          <a href="https://getbootstrap.com" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain.svg" alt="Bootstrap" />
            <span>Bootstrap</span>
          </a>
          <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg" alt="HTML5" />
            <span>HTML5</span>
          </a>
          <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg" alt="CSS3" />
            <span>CSS3</span>
          </a>
        </div>
      </div>

      <!-- Backend & Systems -->
      <div class="skills-category">
        <div class="skills-category-title">
          <span>⚙️ Backend, Systems & Languages</span>
        </div>
        <div class="skills-grid">
          <a href="https://nodejs.org" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" alt="Node.js" />
            <span>Node.js</span>
          </a>
          <a href="https://expressjs.com" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original.svg" alt="Express" />
            <span>Express.js</span>
          </a>
          <a href="https://www.java.com" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" />
            <span>Java</span>
          </a>
          <a href="https://www.python.org" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" />
            <span>Python</span>
          </a>
          <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="C" />
            <span>C</span>
          </a>
          <a href="https://www.docker.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://www.vectorlogo.zone/logos/docker/docker-icon.svg" alt="Docker" />
            <span>Docker</span>
          </a>
        </div>
      </div>

      <!-- Database, Cloud & Tools -->
      <div class="skills-category">
        <div class="skills-category-title">
          <span>🗄️ Database, Cloud & Tools</span>
        </div>
        <div class="skills-grid">
          <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original.svg" alt="MongoDB" />
            <span>MongoDB</span>
          </a>
          <a href="https://www.mysql.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original.svg" alt="MySQL" />
            <span>MySQL</span>
          </a>
          <a href="https://firebase.google.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="Firebase" />
            <span>Firebase</span>
          </a>
          <a href="https://aws.amazon.com" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="AWS" />
            <span>AWS</span>
          </a>
          <a href="https://git-scm.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="Git" />
            <span>Git</span>
          </a>
          <a href="https://www.figma.com/" target="_blank" rel="noreferrer" class="skill-chip">
            <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="Figma" />
            <span>Figma</span>
          </a>
        </div>
      </div>

      <!-- GITHUB STATS & ACTIVITY -->
      <h2 class="section-title">
        <span class="icon-box">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>
        </span>
        GitHub Stats & Analytics
      </h2>

      <div class="stats-container">
        <!-- Streak Stats -->
        <div class="stat-card">
          <img src="https://streak-stats.demolab.com?user=mohdaffan01&theme=tokyonight&hide_border=true&border_radius=12&background=0b1021" alt="Mohd Affan GitHub Streak" loading="lazy" />
        </div>

        <!-- GitHub Overview Stats -->
        <div class="stat-card">
          <img src="https://github-readme-stats.vercel.app/api?username=mohdaffan01&show_icons=true&theme=tokyonight&hide_border=true&border_radius=12&background=0b1021&include_all_commits=true&count_private=true" alt="Mohd Affan GitHub Stats" loading="lazy" />
        </div>

        <!-- Top Languages -->
        <div class="stat-card" style="grid-column: 1 / -1;">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mohdaffan01&layout=compact&theme=tokyonight&hide_border=true&border_radius=12&background=0b1021" alt="Top Languages" loading="lazy" />
        </div>
      </div>

    </main>

    <!-- MARKDOWN EXPORT VIEW (For pasting directly into GitHub Profile README) -->
    <section id="markdown-view-section" style="display: none;">
      
      <div class="readme-code-wrapper">
        <div class="code-header">
          <div class="code-title">
            <span class="dot"></span>
            <span>README.md — Copy & Paste directly to your GitHub Profile repo (<code>mohdaffan01/mohdaffan01</code>)</span>
          </div>
          <button class="copy-btn" onclick="copyMarkdownCode()">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2" ry="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
            <span id="copy-btn-text">Copy Markdown</span>
          </button>
        </div>

        <p style="color: var(--text-muted); font-size: 0.85rem; margin-bottom: 14px;">
          💡 <strong>Tip:</strong> GitHub strips custom CSS & scripts from READMEs. The code below uses GitHub-optimized SVG banners, shields badges, and Tokyo Night cards designed specifically to render beautifully inside your official GitHub profile.
        </p>

        <pre class="markdown-code" id="raw-markdown-code"><code>&lt;div align="center"&gt;
  &lt;!-- Animated Header Wave Banner --&gt;
  &lt;img src="https://capsule-render.vercel.app/api?type=waving&amp;color=gradient&amp;customColorList=2,14,26,43,100&amp;height=220&amp;section=header&amp;text=Mohd%20Affan&amp;fontSize=50&amp;fontColor=fff&amp;animation=fadeIn&amp;fontAlignY=38&amp;desc=Full%20Stack%20Developer%20%7C%20MERN%20Specialist%20%7C%20Problem%20Solver&amp;descAlignY=62&amp;descAlign=50" width="100%" alt="Mohd Affan Banner" /&gt;

  &lt;!-- Dynamic Typing SVG Subtitle --&gt;
  &lt;a href="https://affan-personalportfolio.netlify.app/"&gt;
    &lt;img src="https://readme-typing-svg.demolab.com?font=Fira+Code&amp;weight=600&amp;size=20&amp;duration=3000&amp;pause=1000&amp;color=38BDF8&amp;center=true&amp;vCenter=true&amp;multiline=false&amp;width=500&amp;height=45&amp;lines=Full+Stack+Developer+%F0%9F%9A%80;MERN+Stack+Specialist+%E2%9A%A1;Problem+Solver+%7C+DSA+%26+System+Design;Building+modern+scalable+web+apps" alt="Typing SVG" /&gt;
  &lt;/a&gt;

  &lt;p&gt;
    &lt;img src="https://komarev.com/ghpvc/?username=mohdaffan01&amp;label=Profile%20Views&amp;color=0e75b6&amp;style=for-the-badge&amp;logo=github" alt="Profile Views" /&gt;
  &lt;/p&gt;

  &lt;!-- Social Badges --&gt;
  &lt;p&gt;
    &lt;a href="https://linkedin.com/in/mohdaffan01" target="_blank"&gt;
      &lt;img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" alt="LinkedIn" /&gt;
    &lt;/a&gt;
    &lt;a href="https://affan-personalportfolio.netlify.app/" target="_blank"&gt;
      &lt;img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&amp;logo=googlechrome&amp;logoColor=white" alt="Portfolio" /&gt;
    &lt;/a&gt;
    &lt;a href="mailto:mohdaffan338@gmail.com"&gt;
      &lt;img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&amp;logo=gmail&amp;logoColor=white" alt="Email" /&gt;
    &lt;/a&gt;
    &lt;a href="https://instagram.com/themdaffan" target="_blank"&gt;
      &lt;img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&amp;logo=instagram&amp;logoColor=white" alt="Instagram" /&gt;
    &lt;/a&gt;
    &lt;a href="https://discord.gg/mdaffan01" target="_blank"&gt;
      &lt;img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&amp;logo=discord&amp;logoColor=white" alt="Discord" /&gt;
    &lt;/a&gt;
  &lt;/p&gt;
&lt;/div&gt;

---

### &lt;img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Card%20Index%20Dividers.png" width="25" height="25" /&gt; About Me

- 💻 **Passionate Full Stack Developer** dedicated to building scalable web applications with smooth UX.
- 💬 Ask me about **MERN Stack, Java, C, MySQL, Docker, DSA, and System Design**.
- 🌐 Portfolio: **[affan-personalportfolio.netlify.app](https://affan-personalportfolio.netlify.app/)**
- 📬 Reach out at: **[mohdaffan338@gmail.com](mailto:mohdaffan338@gmail.com)**
- ⚡ Fun fact: *I turn coffee into performant, clean code.*

---

### &lt;img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Laptop.png" width="25" height="25" /&gt; Tech Stack &amp; Tools

&lt;p align="center"&gt;
  &lt;!-- Frontend --&gt;
  &lt;img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&amp;logo=react&amp;logoColor=61DAFB" alt="React" /&gt;
  &lt;img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&amp;logo=typescript&amp;logoColor=white" alt="TypeScript" /&gt;
  &lt;img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&amp;logo=javascript&amp;logoColor=black" alt="JavaScript" /&gt;
  &lt;img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&amp;logo=tailwind-css&amp;logoColor=white" alt="Tailwind CSS" /&gt;
  &lt;img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&amp;logo=html5&amp;logoColor=white" alt="HTML5" /&gt;
  &lt;img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&amp;logo=css3&amp;logoColor=white" alt="CSS3" /&gt;
  &lt;img src="https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&amp;logo=bootstrap&amp;logoColor=white" alt="Bootstrap" /&gt;
&lt;/p&gt;

&lt;p align="center"&gt;
  &lt;!-- Backend &amp; DB --&gt;
  &lt;img src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&amp;logo=node.js&amp;logoColor=white" alt="Node.js" /&gt;
  &lt;img src="https://img.shields.io/badge/Express.js-404D59?style=for-the-badge&amp;logo=express&amp;logoColor=white" alt="Express" /&gt;
  &lt;img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&amp;logo=openjdk&amp;logoColor=white" alt="Java" /&gt;
  &lt;img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&amp;logo=python&amp;logoColor=white" alt="Python" /&gt;
  &lt;img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&amp;logo=c&amp;logoColor=white" alt="C" /&gt;
  &lt;img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&amp;logo=mongodb&amp;logoColor=white" alt="MongoDB" /&gt;
  &lt;img src="https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&amp;logo=mysql&amp;logoColor=white" alt="MySQL" /&gt;
  &lt;img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&amp;logo=firebase&amp;logoColor=black" alt="Firebase" /&gt;
&lt;/p&gt;

&lt;p align="center"&gt;
  &lt;!-- Cloud &amp; Tools --&gt;
  &lt;img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&amp;logo=docker&amp;logoColor=white" alt="Docker" /&gt;
  &lt;img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&amp;logo=amazon-aws&amp;logoColor=white" alt="AWS" /&gt;
  &lt;img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&amp;logo=git&amp;logoColor=white" alt="Git" /&gt;
  &lt;img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&amp;logo=figma&amp;logoColor=white" alt="Figma" /&gt;
&lt;/p&gt;

---

### &lt;img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Bar%20Chart.png" width="25" height="25" /&gt; GitHub Analytics &amp; Streaks

&lt;p align="center"&gt;
  &lt;img src="https://streak-stats.demolab.com?user=mohdaffan01&amp;theme=tokyonight&amp;hide_border=true&amp;border_radius=12&amp;background=0b1021" alt="GitHub Streak" width="48%" /&gt;
  &lt;img src="https://github-readme-stats.vercel.app/api?username=mohdaffan01&amp;show_icons=true&amp;theme=tokyonight&amp;hide_border=true&amp;border_radius=12&amp;background=0b1021&amp;include_all_commits=true&amp;count_private=true" alt="GitHub Stats" width="48%" /&gt;
&lt;/p&gt;

&lt;p align="center"&gt;
  &lt;img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mohdaffan01&amp;layout=compact&amp;theme=tokyonight&amp;hide_border=true&amp;border_radius=12&amp;background=0b1021" alt="Top Languages" /&gt;
&lt;/p&gt;

---

&lt;div align="center"&gt;
  &lt;img src="https://capsule-render.vercel.app/api?type=waving&amp;color=gradient&amp;customColorList=2,14,26,43,100&amp;height=120&amp;section=footer" width="100%" alt="Footer Wave" /&gt;
  &lt;p&gt;⭐️ From &lt;b&gt;Mohd Affan&lt;/b&gt; — Thanks for stopping by!&lt;/p&gt;
&lt;/div&gt;</code></pre>
      </div>

    </section>

    <!-- FOOTER -->
    <footer>
      <p>Designed with ❤️ for <strong>Mohd Affan</strong> • Built for high impact & modern web standards</p>
      <p style="margin-top: 6px;">
        <a href="https://github.com/mohdaffan01" target="_blank" rel="noreferrer">github.com/mohdaffan01</a> • 
        <a href="https://affan-personalportfolio.netlify.app/" target="_blank" rel="noreferrer">affan-personalportfolio.netlify.app</a>
      </p>
    </footer>

  </div>

  <!-- Toast Notification element -->
  <div class="toast" id="copy-toast">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
    <span>GitHub README Markdown copied to clipboard!</span>
  </div>

  <script>
    // Tab Switcher between Web View and Markdown View
    function switchView(mode) {
      const webSec = document.getElementById('web-view-section');
      const mdSec = document.getElementById('markdown-view-section');
      const btnWeb = document.getElementById('btn-web-view');
      const btnMd = document.getElementById('btn-md-view');

      if (mode === 'web') {
        webSec.style.display = 'block';
        mdSec.style.display = 'none';
        btnWeb.classList.add('active');
        btnMd.classList.remove('active');
      } else {
        webSec.style.display = 'none';
        mdSec.style.display = 'block';
        btnMd.classList.add('active');
        btnWeb.classList.remove('active');
      }
    }

    // Copy to clipboard helper
    function copyMarkdownCode() {
      const codeElement = document.getElementById('raw-markdown-code');
      const textToCopy = codeElement.innerText;

      navigator.clipboard.writeText(textToCopy).then(() => {
        showToast();
        const btnText = document.getElementById('copy-btn-text');
        btnText.innerText = 'Copied!';
        setTimeout(() => {
          btnText.innerText = 'Copy Markdown';
        }, 2500);
      }).catch(err => {
        console.error('Failed to copy: ', err);
      });
    }

    function showToast() {
      const toast = document.getElementById('copy-toast');
      toast.classList.add('show');
      setTimeout(() => {
        toast.classList.remove('show');
      }, 3000);
    }
  </script>
</body>
</html>







