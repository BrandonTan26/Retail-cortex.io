<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Retail-Cortex.io — Tech & AI Retail Services</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg-dark: #030512;
      --bg-grad: radial-gradient(circle at top, #311b92 0, #030512 52%, #01020a 100%);
      --neon-accent: #8b5cf6;  /* ungu neon */
      --neon-cyan: #22d3ee;    /* biru neon */
      --neon-purple: #7c3aed;
      --text-main: #f9fafb;
      --text-soft: #9ca3af;
      --card-bg: rgba(8, 11, 30, 0.96);
      --border-glass: rgba(129, 140, 248, 0.6);
      --radius-xl: 20px;
      --shadow-neon: 0 0 40px rgba(34, 211, 238, 0.25);
      --transition-fast: 0.22s ease;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html, body {
      height: 100%;
    }

    body {
      font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--bg-grad);
      color: var(--text-main);
      overflow-x: hidden;
    }

    .container {
      width: 100%;
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 18px;
      position: relative;
      z-index: 1;
    }

    section {
      padding: 64px 0;
      position: relative;
      z-index: 1;
    }

    h1, h2 {
      font-family: "Orbitron", system-ui;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    /* BACKGROUND ORBS + GRID */
    .bg-grid {
      position: fixed;
      inset: 0;
      pointer-events: none;
      opacity: 0.18;
      background-image:
        linear-gradient(rgba(129, 140, 248, 0.2) 1px, transparent 1px),
        linear-gradient(90deg, rgba(129, 140, 248, 0.2) 1px, transparent 1px);
      background-size: 52px 52px;
      animation: gridShift 22s linear infinite;
      z-index: 0;
    }

    .orb {
      position: fixed;
      border-radius: 999px;
      filter: blur(4px);
      opacity: 0.38;
      mix-blend-mode: screen;
      pointer-events: none;
      z-index: 0;
    }

    .orb--top {
      width: 420px;
      height: 420px;
      background: radial-gradient(circle, rgba(124, 58, 237, 0.85), transparent 70%);
      top: -60px;
      right: -120px;
      animation: floatOrb 18s ease-in-out infinite;
    }

    .orb--bottom {
      width: 360px;
      height: 360px;
      background: radial-gradient(circle, rgba(34, 211, 238, 0.8), transparent 70%);
      bottom: -80px;
      left: -80px;
      animation: floatOrb 20s ease-in-out infinite reverse;
    }

    @keyframes gridShift {
      0% { background-position: 0 0, 0 0; }
      100% { background-position: 120px 120px, 120px 120px; }
    }

    @keyframes floatOrb {
      0%, 100% { transform: translateY(0) translateX(0); }
      50% { transform: translateY(30px) translateX(10px); }
    }

    /* NAVBAR */
    .navbar {
      position: sticky;
      top: 0;
      z-index: 10;
      backdrop-filter: blur(16px);
      background: linear-gradient(to right, rgba(10, 10, 31, 0.96), rgba(15, 23, 42, 0.98));
      border-bottom: 1px solid rgba(129, 140, 248, 0.5);
    }

    .navbar-inner {
      max-width: 1100px;
      margin: 0 auto;
      padding: 10px 18px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 14px;
    }

    .logo-wrap {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-img {
      height: 40px;
      width: auto;
      display: block;
    }

    .logo-text-main {
      font-family: "Orbitron", system-ui;
      font-size: 17px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    .logo-text-sub {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.22em;
      color: var(--text-soft);
    }

    .nav-links {
      display: flex;
      gap: 18px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
    }

    .nav-links a {
      color: var(--text-soft);
      text-decoration: none;
      position: relative;
      padding-bottom: 2px;
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0;
      height: 2px;
      border-radius: 999px;
      background: linear-gradient(90deg, var(--neon-cyan), var(--neon-accent));
      box-shadow: 0 0 10px rgba(34, 211, 238, 0.8);
      transition: width var(--transition-fast);
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    @media (max-width: 720px) {
      .nav-links {
        display: none;
      }
    }

    /* HERO */
    .hero {
      padding-top: 48px;
    }

    .hero-inner {
      display: grid;
      grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
      gap: 32px;
      align-items: center;
    }

    @media (max-width: 880px) {
      .hero-inner {
        grid-template-columns: 1fr;
      }
    }

    .tagline {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 12px;
      border-radius: 999px;
      border: 1px solid rgba(129, 140, 248, 0.6);
      background: rgba(15, 23, 42, 0.96);
      box-shadow: 0 0 18px rgba(34, 211, 238, 0.3);
      font-size: 11px;
      color: var(--text-soft);
      margin-bottom: 14px;
    }

    .tag-dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 20%, #e5f6ff, var(--neon-cyan));
      box-shadow: 0 0 14px rgba(34, 211, 238, 1);
    }

    .hero-title {
      font-size: clamp(30px, 4vw, 38px);
      margin-bottom: 14px;
      text-transform: uppercase;
    }

    .hero-title span.highlight {
      background: linear-gradient(120deg, var(--neon-cyan), var(--neon-accent), #e5f6ff);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero-sub {
      font-size: 14px;
      color: var(--text-soft);
      max-width: 480px;
      margin-bottom: 20px;
    }

    .hero-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 22px;
    }

    .pill {
      font-size: 11px;
      border-radius: 999px;
      padding: 5px 11px;
      border: 1px solid rgba(129, 140, 248, 0.7);
      background: rgba(15, 23, 42, 0.96);
      color: var(--text-soft);
    }

    .hero-cta {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      align-items: center;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 11px 22px;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      background: radial-gradient(circle at 10% 0, #e5f6ff, var(--neon-cyan));
      color: #020617;
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      box-shadow:
        0 16px 30px rgba(34, 211, 238, 0.5),
        0 0 18px rgba(124, 58, 237, 0.7);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast);
    }

    .btn-primary span.icon {
      font-size: 16px;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow:
        0 24px 40px rgba(34, 211, 238, 0.7),
        0 0 26px rgba(124, 58, 237, 0.9);
    }

    .btn-ghost {
      border-radius: 999px;
      border: 1px dashed rgba(129, 140, 248, 0.9);
      padding: 9px 17px;
      background: rgba(15, 23, 42, 0.96);
      color: var(--text-soft);
      font-size: 12px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
    }

    .btn-ghost:hover {
      border-style: solid;
      color: var(--text-main);
    }

    .hero-visual {
      position: relative;
      height: 270px;
    }

    .core-orbit {
      position: absolute;
      inset: 0;
      border-radius: 26px;
      background:
        radial-gradient(circle at 0 0, rgba(124, 58, 237, 0.8), transparent 65%),
        radial-gradient(circle at 100% 100%, rgba(34, 211, 238, 0.7), transparent 65%),
        rgba(15, 23, 42, 0.98);
      border: 1px solid rgba(129, 140, 248, 0.9);
      box-shadow:
        0 18px 40px rgba(0, 0, 0, 0.8),
        0 0 40px rgba(34, 211, 238, 0.35);
      overflow: hidden;
    }

    .hero-logo-overlay {
      position: absolute;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0.08;
    }

    .hero-logo-overlay img {
      max-width: 80%;
      height: auto;
      filter: drop-shadow(0 0 18px rgba(34,211,238,0.9));
    }

    .core-orbit::before,
    .core-orbit::after {
      content: "";
      position: absolute;
      width: 160%;
      height: 160%;
      border-radius: 999px;
      border: 1px dashed rgba(129, 140, 248, 0.9);
      top: -30%;
      left: -30%;
      animation: orbitSpin 20s linear infinite;
    }

    .core-orbit::after {
      border-style: solid;
      border-color: rgba(88, 28, 211, 0.9);
      animation-direction: reverse;
      animation-duration: 26s;
    }

    .ai-core {
      position: absolute;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      pointer-events: none;
    }

    .ai-chip {
      width: 150px;
      height: 90px;
      border-radius: 18px;
      background: radial-gradient(circle at 0 0, #e5f6ff, #c7d2fe 28%, #111827 70%);
      box-shadow:
        0 0 26px rgba(226, 232, 240, 0.9),
        0 0 40px rgba(34, 211, 238, 0.7);
      position: relative;
      overflow: hidden;
    }

    .ai-chip::before,
    .ai-chip::after {
      content: "";
      position: absolute;
      inset: 10px;
      border-radius: 12px;
      border: 2px solid rgba(15, 23, 42, 0.95);
    }

    .ai-chip::after {
      inset: 24px 32px;
      border-color: transparent;
      border-left: 2px solid rgba(15, 23, 42, 0.95);
      border-right: 2px solid rgba(15, 23, 42, 0.95);
    }

    .ai-core-logo {
      position: absolute;
      inset: 16px 30px;
      border-radius: 8px;
      background: radial-gradient(circle at 30% 0, var(--neon-cyan), var(--neon-accent));
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Orbitron", system-ui;
      font-size: 13px;
      color: #020617;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .ai-lines {
      position: absolute;
      inset: 10px;
      display: flex;
      justify-content: space-between;
    }

    .ai-line {
      width: 3px;
      border-radius: 999px;
      background: linear-gradient(to bottom, var(--neon-cyan), transparent);
      opacity: 0.9;
      box-shadow: 0 0 16px rgba(34, 211, 238, 0.9);
      animation: dataFlow 1.7s linear infinite;
    }

    .ai-line:nth-child(2) {
      background: linear-gradient(to bottom, var(--neon-accent), transparent);
      animation-delay: 0.4s;
    }

    .ai-line:nth-child(3) {
      animation-delay: 0.8s;
    }

    .scan-line {
      position: absolute;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, rgba(239, 246, 255, 0.95), transparent);
      top: 0;
      mix-blend-mode: screen;
      animation: scanDown 2.8s linear infinite;
      opacity: 0.7;
    }

    @keyframes orbitSpin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    @keyframes dataFlow {
      0% { transform: translateY(70px); opacity: 0; }
      30% { opacity: 1; }
      100% { transform: translateY(-70px); opacity: 0; }
    }

    @keyframes scanDown {
      0% { transform: translateY(-120%); }
      100% { transform: translateY(220%); }
    }

    /* SECTION HEADINGS */
    .section-heading {
      text-align: center;
      margin-bottom: 30px;
    }

    .section-heading h2 {
      font-size: 22px;
      margin-bottom: 6px;
    }

    .section-heading p {
      font-size: 13px;
      color: var(--text-soft);
    }

    /* SERVICES GRID */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 22px;
    }

    .service-card {
      background: var(--card-bg);
      border-radius: var(--radius-xl);
      padding: 18px 18px 16px;
      border: 1px solid var(--border-glass);
      box-shadow: 0 18px 32px rgba(0, 0, 0, 0.9);
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(16px);
      transform: translateY(0);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast), border-color var(--transition-fast);
    }

    .service-card::before {
      content: "";
      position: absolute;
      width: 120px;
      height: 120px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(124, 58, 237, 0.8), transparent 70%);
      top: -40px;
      right: -50px;
      opacity: 0.6;
    }

    .service-card:hover {
      transform: translateY(-4px);
      border-color: rgba(226, 232, 240, 0.95);
      box-shadow: 0 24px 44px rgba(0, 0, 0, 1);
    }

    .service-tag {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-soft);
      margin-bottom: 4px;
    }

    .service-name {
      font-family: "Orbitron", system-ui;
      font-size: 15px;
      letter-spacing: 0.12em;
      margin-bottom: 6px;
      text-transform: uppercase;
    }

    .service-desc {
      font-size: 12px;
      color: var(--text-soft);
      margin-bottom: 12px;
      min-height: 44px;
    }

    .service-actions {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
    }

    .btn-order {
      border: none;
      cursor: pointer;
      padding: 8px 14px;
      border-radius: 999px;
      background: radial-gradient(circle at 10% 0, #e5f6ff, var(--neon-accent));
      color: #020617;
      font-size: 11px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      box-shadow:
        0 10px 22px rgba(124, 58, 237, 0.7),
        0 0 16px rgba(34, 211, 238, 0.7);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast);
    }

    .btn-order span.icon {
      font-size: 15px;
    }

    .btn-order:hover {
      transform: translateY(-1px);
      box-shadow:
        0 16px 30px rgba(124, 58, 237, 0.9),
        0 0 22px rgba(34, 211, 238, 0.95);
    }

    .chip {
      font-size: 10px;
      padding: 5px 9px;
      border-radius: 999px;
      border: 1px solid rgba(129, 140, 248, 0.9);
      color: var(--text-soft);
      background: rgba(15, 23, 42, 0.98);
    }

    /* CONTACT BOX */
    .contact-box {
      max-width: 720px;
      margin: 0 auto;
      padding: 20px 18px;
      border-radius: 22px;
      background: rgba(15, 23, 42, 0.98);
      border: 1px solid rgba(129, 140, 248, 0.9);
      box-shadow: 0 22px 40px rgba(0, 0, 0, 1);
      backdrop-filter: blur(16px);
    }

    .contact-box h3 {
      font-family: "Orbitron", system-ui;
      font-size: 18px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      margin-bottom: 8px;
    }

    .contact-box p {
      font-size: 13px;
      color: var(--text-soft);
      margin-bottom: 12px;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
      gap: 10px;
      font-size: 12px;
    }

    .contact-label {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-soft);
      margin-bottom: 2px;
    }

    footer {
      text-align: center;
      padding: 20px 0 28px;
      font-size: 11px;
      color: var(--text-soft);
    }

    /* FLOATING WHATSAPP */
    .floating-wa {
      position: fixed;
      right: 18px;
      bottom: 18px;
      width: 58px;
      height: 58px;
      border-radius: 50%;
      background: radial-gradient(circle at 25% 0, #e5f6ff, #22c55e);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow:
        0 18px 38px rgba(0, 0, 0, 0.9),
        0 0 26px rgba(34, 197, 94, 0.95);
      cursor: pointer;
      z-index: 40;
      animation: floatPulse 2.8s ease-in-out infinite;
    }

    .floating-wa-inner {
      width: 30px;
      height: 30px;
      position: relative;
    }

    .wa-bubble {
      position: absolute;
      inset: 0;
      border-radius: 10px;
      border-bottom-left-radius: 4px;
      background: #075e54;
      transform: rotate(-4deg);
    }

    .wa-bubble::after {
      content: "";
      position: absolute;
      bottom: -5px;
      left: 6px;
      border-width: 6px;
      border-style: solid;
      border-color: #075e54 transparent transparent transparent;
      transform: rotate(25deg);
    }

    .wa-phone {
      position: absolute;
      inset: 4px 5px 4px 5px;
      border-radius: 8px;
      border: 2px solid #ffffff;
      box-sizing: border-box;
    }

    .wa-phone-line {
      position: absolute;
      inset: 8px 10px;
      border-radius: 50%;
      border: 2px solid #ffffff;
      border-color: transparent transparent #ffffff #ffffff;
      transform: rotate(-35deg);
    }

    .floating-wa-tooltip {
      position: absolute;
      right: 66px;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(15, 23, 42, 0.98);
      color: #f9fafb;
      padding: 6px 12px;
      border-radius: 999px;
      font-size: 11px;
      white-space: nowrap;
      box-shadow: 0 10px 24px rgba(0, 0, 0, 1);
    }

    .floating-wa-tooltip::after {
      content: "";
      position: absolute;
      right: -6px;
      top: 50%;
      transform: translateY(-50%);
      border-width: 6px;
      border-style: solid;
      border-color: transparent transparent transparent rgba(15, 23, 42, 0.98);
    }

    @keyframes floatPulse {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-4px); }
    }

    @media (max-width: 520px) {
      .floating-wa-tooltip {
        display: none;
      }
    }
  </style>
</head>
<body>

  <div class="bg-grid"></div>
  <div class="orb orb--top"></div>
  <div class="orb orb--bottom"></div>

  <!-- NAVBAR -->
  <header class="navbar">
    <div class="navbar-inner">
      <div class="logo-wrap">
        <img src="retail-cortex-logo.png" alt="Retail-Cortex.io logo" class="logo-img">
        <div>
          <div class="logo-text-main">Retail-Cortex.io</div>
          <div class="logo-text-sub">AI • RETAIL • AUTOMATION</div>
        </div>
      </div>
      <nav class="nav-links">
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#how">Workflow</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <!-- HERO -->
  <main id="home" class="hero">
    <div class="container">
      <div class="hero-inner">
        <div>
          <div class="tagline">
            <span class="tag-dot"></span>
            RETAIL AUTOMATION • POWERED BY AI
          </div>
          <h1 class="hero-title">
            Plug your store into the <span class="highlight">Retail-Cortex</span>.
          </h1>
          <p class="hero-sub">
            Studio digital yang fokus di AI & data buat bantu personil toko ngerjain task berat:
            dari new member sampai PPT report, semua dibungkus rapi dan otomatis langsung ke WhatsApp.
          </p>
          <div class="hero-badges">
            <span class="pill">Neon Cyberpunk Interface</span>
            <span class="pill">AI-Assisted Workflow</span>
            <span class="pill">Built for Store Teams</span>
          </div>
          <div class="hero-cta">
            <button class="btn-primary" onclick="openWhatsAppGeneral()">
              <span class="icon">⚡</span>
              <span>Chat Retail-Cortex via WA</span>
            </button>
            <button class="btn-ghost" onclick="scrollToSection('services')">
              <span>👁 View Cortex Modules</span>
            </button>
          </div>
        </div>

        <aside class="hero-visual">
          <div class="core-orbit">
            <div class="hero-logo-overlay">
              <img src="retail-cortex-logo.png" alt="Retail-Cortex.io logo">
            </div>
            <div class="ai-core">
              <div class="ai-chip">
                <div class="scan-line"></div>
                <div class="ai-core-logo">RC • AI</div>
                <div class="ai-lines">
                  <div class="ai-line"></div>
                  <div class="ai-line"></div>
                  <div class="ai-line"></div>
                </div>
              </div>
            </div>
          </div>
        </aside>
      </div>
    </div>
  </main>

  <!-- SERVICES -->
  <section id="services">
    <div class="container">
      <div class="section-heading">
        <h2>Cortex Service Modules</h2>
        <p>Pilih modul sesuai kebutuhan toko, klik order, auto kebuka WhatsApp dengan teks siap kirim.</p>
      </div>

      <div class="services-grid">

        <!-- NEW MEMBER FRESH -->
        <article class="service-card">
          <div class="service-tag">Membership Engine</div>
          <h3 class="service-name">New Member Fresh</h3>
          <p class="service-desc">
            Pembuatan new member Alfamart khusus buat kamu yang member-nya flop, seret, atau stagnan. Disusun biar aliran member baru ke toko jadi lebih segar lagi.
          </p>
          <div class="service-actions">
            <button class="btn-order" onclick="orderService('NEW MEMBER FRESH')">
              <span class="icon">💬</span>
              <span>Order via WA</span>
            </button>
            <span class="chip">Growth & Acquisition</span>
          </div>
        </article>

        <!-- DESIGN AREA COVERAGE -->
        <article class="service-card">
          <div class="service-tag">Geo Intelligence</div>
          <h3 class="service-name">Design Area Coverage</h3>
          <p class="service-desc">
            Pembuatan desain area coverage / mapping area dengan tampilan 3D, biar potensi sekitar toko kebaca jelas dan enak dijelasin ke atasan.
          </p>
          <div class="service-actions">
            <button class="btn-order" onclick="orderService('DESIGN AREA COVERAGE')">
              <span class="icon">💬</span>
              <span>Order via WA</span>
            </button>
            <span class="chip">Coverage Mapping</span>
          </div>
        </article>

        <!-- TUGAS PPT -->
        <article class="service-card">
          <div class="service-tag">Deck Engine</div>
          <h3 class="service-name">Tugas PPT</h3>
          <p class="service-desc">
            Pembuatan PPT presentasi strategi, laporan toko, atau bahan meeting yang kelihatan mahal: clean, data-driven, dan siap tampil depan BM/AM.
          </p>
          <div class="service-actions">
            <button class="btn-order" onclick="orderService('TUGAS PPT')">
              <span class="icon">💬</span>
              <span>Order via WA</span>
            </button>
            <span class="chip">Presentation Suite</span>
          </div>
        </article>

        <!-- PANDUAN RAHASIA TOP 10 SUEGEERRR -->
        <article class="service-card">
          <div class="service-tag">Playbook</div>
          <h3 class="service-name">Panduan Rahasia Top 10 Suegeerrr</h3>
          <p class="service-desc">
            Strategi rahasia bikin toko kamu tembus top 10 suegeerrr tanpa harus jual ke agen. Fokus ke eksekusi ritel murni, bukan numpang volume.
          </p>
          <div class="service-actions">
            <button class="btn-order" onclick="orderService('PANDUAN RAHASIA TOP 10 SUEGEERRR')">
              <span class="icon">💬</span>
              <span>Order via WA</span>
            </button>
            <span class="chip">Top 10 Guide</span>
          </div>
        </article>

        <!-- PANDUAN RAHASIA TOP 10 PPS -->
        <article class="service-card">
          <div class="service-tag">Playbook</div>
          <h3 class="service-name">Panduan Rahasia Top 10 PPS</h3>
          <p class="service-desc">
            Strategi rahasia bikin toko kamu tembus top 10 PPS tanpa jual ke agen. Isinya pola kerja, prioritas, dan eksekusi yang realistis buat di lapangan.
          </p>
          <div class="service-actions">
            <button class="btn-order" onclick="orderService('PANDUAN RAHASIA TOP 10 PPS')">
              <span class="icon">💬</span>
              <span>Order via WA</span>
            </button>
            <span class="chip">PPS Mastery</span>
          </div>
        </article>

      </div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section id="how">
    <div class="container">
      <div class="section-heading">
        <h2>How Retail-Cortex Works</h2>
        <p>Simple 3 langkah — semua komunikasi lewat WhatsApp, human touch + sentuhan AI.</p>
      </div>

      <div class="contact-box">
        <h3>01. Pilih Modul • 02. Chat • 03. Eksekusi</h3>
        <p>
          Kamu cukup pilih layanan yang cocok buat toko, klik tombol order, dan jelasin brief via WhatsApp.
          Retail-Cortex bakal bantu nyusun struktur, teks, sampai ide eksekusinya.
        </p>
        <div class="contact-grid">
          <div>
            <div class="contact-label">Brand</div>
            <div>Retail-Cortex.io — Tech &amp; AI Retail Studio</div>
          </div>
          <div>
            <div class="contact-label">WhatsApp</div>
            <div>087809236556</div>
          </div>
          <div>
            <div class="contact-label">Email</div>
            <div>brandotan94@gmail.com</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT / FOOTER -->
  <section id="contact">
    <footer>
      <div>© 2025 Retail-Cortex.io — AI Retail Support crafted for store teams.</div>
      <div style="margin-top:4px;font-size:11px;">
        Email:
        <a href="mailto:brandotan94@gmail.com" style="color:#22d3ee;text-decoration:none;">
          brandotan94@gmail.com
        </a>
        • WhatsApp: 087809236556
      </div>
    </footer>
  </section>

  <!-- FLOATING WHATSAPP BUTTON -->
  <div class="floating-wa" onclick="openWhatsAppGeneral()">
    <div class="floating-wa-inner">
      <div class="wa-bubble"></div>
      <div class="wa-phone"></div>
      <div class="wa-phone-line"></div>
    </div>
    <div class="floating-wa-tooltip">Chat Retail-Cortex via WhatsApp</div>
  </div>

  <script>
    // Nomor WA: 087809236556 -> format internasional
    const WHATSAPP_NUMBER = "6287809236556";

    function orderService(serviceName) {
      const baseUrl = "https://wa.me/" + WHATSAPP_NUMBER;
      const text =
        "Halo, saya mau menggunakan layanan *" +
        serviceName +
        "* dari Retail-Cortex.io untuk bantu pekerjaan toko.";
      const url = baseUrl + "?text=" + encodeURIComponent(text);
      window.open(url, "_blank");
    }

    function openWhatsAppGeneral() {
      const baseUrl = "https://wa.me/" + WHATSAPP_NUMBER;
      const text =
        "Halo, saya mau tanya dulu tentang layanan di Retail-Cortex.io. Bisa jelasin modul yang cocok buat toko saya?";
      const url = baseUrl + "?text=" + encodeURIComponent(text);
      window.open(url, "_blank");
    }

    function scrollToSection(id) {
      const el = document.getElementById(id);
      if (!el) return;
      el.scrollIntoView({ behavior: "smooth", block: "start" });
    }
  </script>
</body>
</html>
