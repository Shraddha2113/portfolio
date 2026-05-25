
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>shraddhacreates — Marketing Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --coral: #FF6B6B;
    --yellow: #FFD93D;
    --mint: #6BCB77;
    --lavender: #C77DFF;
    --sky: #4FC3F7;
    --cream: #FFF8F0;
    --dark: #1A1A2E;
    --card-bg: #FFFFFF;
    --text-muted: #888;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--dark);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.2rem 2.5rem;
    background: rgba(255,248,240,0.88);
    backdrop-filter: blur(12px);
    border-bottom: 1.5px dashed rgba(255,107,107,0.25);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 900;
    color: var(--coral); letter-spacing: -0.5px;
  }
  .nav-logo span { color: var(--dark); }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    text-decoration: none; color: var(--dark);
    font-size: 0.9rem; font-weight: 500; transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--coral); }
  .nav-cta {
    background: var(--coral); color: white !important;
    padding: 0.45rem 1.2rem; border-radius: 50px;
  }
  .nav-cta:hover { background: #e55555 !important; }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 7rem 2.5rem 4rem;
    position: relative; overflow: hidden;
  }
  .hero-blobs { position: absolute; inset: 0; pointer-events: none; z-index: 0; }
  .blob {
    position: absolute; border-radius: 50%;
    filter: blur(70px); opacity: 0.35;
    animation: float 8s ease-in-out infinite;
  }
  .blob-1 { width: 420px; height: 420px; background: var(--coral); top: -100px; right: -80px; }
  .blob-2 { width: 320px; height: 320px; background: var(--yellow); bottom: 0; left: -80px; animation-delay: 2s; }
  .blob-3 { width: 250px; height: 250px; background: var(--lavender); top: 40%; right: 20%; animation-delay: 4s; }
  @keyframes float {
    0%,100% { transform: translateY(0) scale(1); }
    50% { transform: translateY(-30px) scale(1.05); }
  }
  .hero-inner { max-width: 900px; position: relative; z-index: 1; }
  .hero-tag {
    display: inline-block;
    background: var(--yellow); color: var(--dark);
    font-size: 0.8rem; font-weight: 500; padding: 0.3rem 1rem;
    border-radius: 50px; margin-bottom: 1.5rem;
    border: 2px solid var(--dark);
    animation: slideDown 0.7s ease both;
  }
  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 8vw, 6rem);
    font-weight: 900; line-height: 1.05; margin-bottom: 1.5rem;
    animation: slideUp 0.8s 0.1s ease both;
  }
  .hero-title .highlight {
    color: var(--coral); position: relative; display: inline-block;
  }
  .hero-title .highlight::after {
    content: ''; position: absolute; bottom: 4px; left: 0; right: 0; height: 6px;
    background: var(--yellow); z-index: -1; border-radius: 3px;
  }
  .hero-sub {
    font-size: 1.15rem; color: #555; max-width: 560px;
    line-height: 1.8; margin-bottom: 2.5rem;
    animation: slideUp 0.8s 0.2s ease both;
  }
  .hero-btns {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: slideUp 0.8s 0.3s ease both;
  }
  .btn-primary {
    background: var(--dark); color: white;
    padding: 0.85rem 2rem; border-radius: 50px;
    text-decoration: none; font-weight: 500; font-size: 0.95rem;
    border: 2px solid var(--dark);
    transition: transform 0.2s, background 0.2s; display: inline-block;
  }
  .btn-primary:hover { transform: translateY(-2px); background: var(--coral); border-color: var(--coral); }
  .btn-outline {
    background: transparent; color: var(--dark);
    padding: 0.85rem 2rem; border-radius: 50px;
    text-decoration: none; font-weight: 500; font-size: 0.95rem;
    border: 2px solid var(--dark);
    transition: transform 0.2s, background 0.2s; display: inline-block;
  }
  .btn-outline:hover { transform: translateY(-2px); background: var(--yellow); }
  .hero-scroll {
    position: absolute; bottom: 2.5rem; left: 2.5rem; z-index: 1;
    display: flex; align-items: center; gap: 0.7rem;
    font-size: 0.8rem; color: var(--text-muted); font-weight: 500;
  }
  .scroll-line {
    width: 50px; height: 1.5px; background: var(--text-muted);
    animation: scrollLine 1.5s ease-in-out infinite alternate;
  }
  @keyframes scrollLine { from { width: 20px; } to { width: 60px; } }
  @keyframes slideDown { from { opacity:0; transform:translateY(-20px); } to { opacity:1; transform:translateY(0); } }
  @keyframes slideUp { from { opacity:0; transform:translateY(30px); } to { opacity:1; transform:translateY(0); } }

  /* SECTIONS */
  section { padding: 6rem 2.5rem; }
  .section-tag {
    font-size: 0.78rem; font-weight: 500; letter-spacing: 2px;
    text-transform: uppercase; color: var(--coral);
    margin-bottom: 0.8rem; display: block;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3rem); font-weight: 700;
    line-height: 1.15; margin-bottom: 1.2rem;
  }

  /* ABOUT */
  #about { background: white; }
  .about-inner {
    max-width: 1100px; margin: 0 auto;
    display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center;
  }
  .about-image-wrap { position: relative; }
  .about-img-placeholder {
    width: 100%; aspect-ratio: 4/5; border-radius: 24px;
    background: linear-gradient(135deg, #FFD93D 0%, #FF6B6B 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem; border: 3px solid var(--dark); position: relative; overflow: hidden;
  }
  .about-img-placeholder::before {
    content: ''; position: absolute; inset: 0;
    background: repeating-linear-gradient(45deg, transparent, transparent 10px, rgba(255,255,255,0.07) 10px, rgba(255,255,255,0.07) 20px);
  }
  .about-sticker {
    position: absolute; bottom: -20px; right: -20px;
    background: var(--mint); color: var(--dark);
    font-weight: 700; font-size: 0.85rem;
    padding: 1rem 1.2rem; border-radius: 16px;
    border: 2px solid var(--dark); text-align: center; line-height: 1.4;
    box-shadow: 4px 4px 0 var(--dark);
  }
  .about-text p { color: #555; line-height: 1.9; margin-bottom: 1.2rem; }
  .about-skills { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 2rem; }
  .skill-chip {
    padding: 0.35rem 1rem; border-radius: 50px;
    font-size: 0.82rem; font-weight: 500; border: 1.5px solid var(--dark);
    transition: transform 0.15s;
  }
  .skill-chip:hover { transform: translateY(-2px); }
  .chip-coral { background: #FFE5E5; color: #c0392b; }
  .chip-yellow { background: #FFF8D6; color: #8a6d00; }
  .chip-mint { background: #E5F7E8; color: #1e7a2f; }
  .chip-lavender { background: #F2E0FF; color: #6a0dad; }
  .chip-sky { background: #E0F5FF; color: #0277a8; }

  /* PROJECTS */
  #projects { background: var(--cream); }
  .projects-header {
    max-width: 1100px; margin: 0 auto 3.5rem;
    display: flex; justify-content: space-between; align-items: flex-end; flex-wrap: wrap; gap: 1rem;
  }
  .projects-grid {
    max-width: 1100px; margin: 0 auto;
    display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1.8rem;
  }

  /* PROJECT CARD (clickable to expand) */
  .project-card {
    background: white; border-radius: 20px;
    border: 2px solid var(--dark); overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
    box-shadow: 4px 4px 0 var(--dark); cursor: pointer;
  }
  .project-card:hover { transform: translate(-4px,-4px); box-shadow: 8px 8px 0 var(--dark); }
  .project-thumb {
    height: 200px; display: flex; align-items: center; justify-content: center;
    font-size: 3.5rem; position: relative; overflow: hidden;
  }
  .project-thumb::after {
    content: ''; position: absolute; inset: 0;
    background: repeating-linear-gradient(60deg, transparent, transparent 8px, rgba(255,255,255,0.1) 8px, rgba(255,255,255,0.1) 16px);
  }
  .thumb-coral { background: linear-gradient(135deg, #FFB5B5, #FF6B6B); }
  .thumb-yellow { background: linear-gradient(135deg, #FFF3A3, #FFD93D); }
  .thumb-mint { background: linear-gradient(135deg, #B5EAB9, #6BCB77); }
  .thumb-lavender { background: linear-gradient(135deg, #E5C5FF, #C77DFF); }
  .project-badge {
    position: absolute; top: 1rem; right: 1rem; z-index: 2;
    background: var(--dark); color: white;
    font-size: 0.7rem; font-weight: 500; padding: 0.25rem 0.7rem; border-radius: 50px;
  }
  .project-body { padding: 1.5rem; }
  .project-category {
    font-size: 0.72rem; font-weight: 500; letter-spacing: 1.5px;
    text-transform: uppercase; color: var(--coral); margin-bottom: 0.4rem;
  }
  .project-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 700; margin-bottom: 0.6rem;
  }
  .project-desc { font-size: 0.88rem; color: #666; line-height: 1.7; margin-bottom: 1.2rem; }
  .project-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .project-tag {
    font-size: 0.72rem; padding: 0.2rem 0.6rem; border-radius: 50px;
    border: 1px solid #ddd; color: #666;
  }
  .project-results {
    margin-top: 1rem; padding-top: 1rem; border-top: 1px dashed #eee;
    display: flex; gap: 0.8rem; flex-wrap: wrap;
  }
  .result-pill {
    background: #FFF0F0; color: var(--coral);
    font-size: 0.75rem; font-weight: 600;
    padding: 0.3rem 0.75rem; border-radius: 50px;
    border: 1px solid #FFD5D5;
  }
  .add-project-card {
    background: white; border-radius: 20px; border: 2px dashed #ccc;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    min-height: 380px; gap: 1rem; cursor: pointer;
    transition: border-color 0.2s, background 0.2s; color: var(--text-muted);
  }
  .add-project-card:hover { border-color: var(--coral); background: #fff8f8; color: var(--coral); }
  .add-icon {
    width: 56px; height: 56px; border-radius: 50%;
    background: #f5f5f5; display: flex; align-items: center; justify-content: center;
    font-size: 1.8rem; transition: background 0.2s;
  }
  .add-project-card:hover .add-icon { background: #FFE5E5; }

  /* CASE STUDY MODAL */
  .case-overlay {
    display: none; position: fixed; inset: 0; z-index: 200;
    background: rgba(10,10,20,0.75); align-items: flex-start; justify-content: center;
    padding: 3rem 1.5rem; overflow-y: auto;
  }
  .case-overlay.open { display: flex; }
  .case-modal {
    background: white; border-radius: 28px;
    max-width: 720px; width: 100%;
    border: 2px solid var(--dark); position: relative;
    box-shadow: 10px 10px 0 var(--dark);
    animation: popIn 0.3s ease both;
  }
  @keyframes popIn { from { opacity:0; transform: scale(0.95) translateY(20px); } to { opacity:1; transform: scale(1) translateY(0); } }
  .case-close {
    position: absolute; top: 1.2rem; right: 1.5rem;
    background: none; border: none; font-size: 1.6rem;
    cursor: pointer; color: #999; line-height: 1; z-index: 10;
  }
  .case-close:hover { color: var(--coral); }
  .case-thumb {
    height: 220px; border-radius: 26px 26px 0 0;
    display: flex; align-items: center; justify-content: center; font-size: 4rem;
    position: relative; overflow: hidden;
  }
  .case-thumb::after {
    content: ''; position: absolute; inset: 0;
    background: repeating-linear-gradient(60deg, transparent, transparent 8px, rgba(255,255,255,0.08) 8px, rgba(255,255,255,0.08) 16px);
  }
  .case-body { padding: 2rem 2.2rem 2.5rem; }
  .case-meta {
    display: flex; gap: 0.6rem; flex-wrap: wrap; margin-bottom: 1.2rem;
  }
  .case-meta-pill {
    font-size: 0.75rem; padding: 0.25rem 0.8rem; border-radius: 50px;
    border: 1.5px solid var(--dark); font-weight: 500;
  }
  .case-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.9rem; font-weight: 900; margin-bottom: 0.5rem; line-height: 1.2;
  }
  .case-subtitle { font-size: 0.9rem; color: #888; margin-bottom: 1.8rem; }
  .case-section-label {
    font-size: 0.72rem; font-weight: 600; letter-spacing: 2px;
    text-transform: uppercase; color: var(--coral); margin-bottom: 0.5rem; display: block;
  }
  .case-body h3 { font-family: 'Playfair Display', serif; font-size: 1.15rem; font-weight: 700; margin-bottom: 0.6rem; margin-top: 1.5rem; }
  .case-body p { font-size: 0.9rem; color: #555; line-height: 1.85; margin-bottom: 0.8rem; }
  .case-body ul { padding-left: 1.4rem; margin-bottom: 1rem; }
  .case-body li { font-size: 0.9rem; color: #555; line-height: 1.8; }
  .case-divider { border: none; border-top: 1.5px dashed #eee; margin: 1.5rem 0; }
  .post-card {
    background: var(--cream); border-radius: 14px;
    border: 1.5px solid #eee; padding: 1.2rem; margin-bottom: 1rem;
  }
  .post-card-header {
    display: flex; align-items: center; gap: 0.6rem; margin-bottom: 0.6rem;
  }
  .post-num {
    background: var(--coral); color: white;
    font-size: 0.7rem; font-weight: 700; padding: 0.2rem 0.6rem;
    border-radius: 50px;
  }
  .post-card-title { font-weight: 600; font-size: 0.9rem; color: var(--dark); }
  .post-card p { font-size: 0.85rem; color: #666; line-height: 1.7; margin: 0.3rem 0; }
  .post-card .caption {
    font-size: 0.82rem; color: #777; font-style: italic;
    border-left: 3px solid var(--yellow); padding-left: 0.8rem; margin-top: 0.5rem;
  }
  .results-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin-top: 1rem;
  }
  .result-box {
    background: #FFF0F0; border-radius: 14px; padding: 1rem;
    text-align: center; border: 1.5px solid #FFD5D5;
  }
  .result-num { font-family: 'Playfair Display', serif; font-size: 1.8rem; font-weight: 900; color: var(--coral); }
  .result-label { font-size: 0.75rem; color: #888; margin-top: 0.2rem; }

  /* CONTACT */
  #contact { background: var(--dark); color: white; text-align: center; }
  #contact .section-tag { color: var(--yellow); }
  #contact .section-title { color: white; }
  #contact .section-title .highlight { color: var(--coral); }
  #contact p { color: rgba(255,255,255,0.6); max-width: 480px; margin: 0 auto 3rem; line-height: 1.8; }
  .contact-grid { display: flex; justify-content: center; flex-wrap: wrap; gap: 1.2rem; margin-bottom: 3rem; }
  .contact-pill {
    display: flex; align-items: center; gap: 0.6rem;
    background: rgba(255,255,255,0.06); color: white;
    padding: 0.85rem 1.5rem; border-radius: 50px;
    border: 1.5px solid rgba(255,255,255,0.15);
    text-decoration: none; font-size: 0.9rem;
    transition: background 0.2s, transform 0.15s;
  }
  .contact-pill:hover { background: rgba(255,255,255,0.12); transform: translateY(-2px); }
  .contact-form {
    max-width: 560px; margin: 0 auto;
    display: flex; flex-direction: column; gap: 1rem; text-align: left;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .contact-form input, .contact-form textarea {
    width: 100%; padding: 0.9rem 1.2rem;
    background: rgba(255,255,255,0.07); color: white;
    border: 1.5px solid rgba(255,255,255,0.15);
    border-radius: 12px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem;
    outline: none; transition: border-color 0.2s; resize: vertical;
  }
  .contact-form input::placeholder, .contact-form textarea::placeholder { color: rgba(255,255,255,0.3); }
  .contact-form input:focus, .contact-form textarea:focus { border-color: var(--coral); }
  .contact-form textarea { min-height: 130px; }
  .form-submit {
    background: var(--coral); color: white;
    padding: 0.95rem 2.5rem; border-radius: 50px; border: none;
    font-family: 'DM Sans', sans-serif; font-size: 1rem; font-weight: 500;
    cursor: pointer; transition: background 0.2s, transform 0.15s; align-self: flex-start;
  }
  .form-submit:hover { background: #e55555; transform: translateY(-2px); }

  footer {
    background: #111; color: rgba(255,255,255,0.4);
    text-align: center; padding: 1.8rem; font-size: 0.82rem;
  }
  footer span { color: var(--coral); }

  /* ADD PROJECT MODAL */
  .modal-overlay {
    display: none; position: fixed; inset: 0; z-index: 999;
    background: rgba(0,0,0,0.7); align-items: center; justify-content: center; padding: 2rem;
  }
  .modal-overlay.open { display: flex; }
  .modal {
    background: white; border-radius: 24px; max-width: 560px; width: 100%;
    padding: 2.5rem; border: 2px solid var(--dark); position: relative;
    box-shadow: 8px 8px 0 var(--dark); max-height: 90vh; overflow-y: auto;
  }
  .modal-close {
    position: absolute; top: 1.2rem; right: 1.5rem;
    background: none; border: none; font-size: 1.5rem; cursor: pointer; color: #999;
  }
  .modal-close:hover { color: var(--coral); }
  .modal h2 { font-family: 'Playfair Display', serif; font-size: 1.6rem; margin-bottom: 1.5rem; }
  .modal label { display: block; font-size: 0.82rem; font-weight: 500; margin-bottom: 0.3rem; color: #444; }
  .modal input, .modal textarea, .modal select {
    width: 100%; padding: 0.75rem 1rem;
    border: 1.5px solid #ddd; border-radius: 10px;
    font-family: 'DM Sans', sans-serif; font-size: 0.9rem;
    margin-bottom: 1rem; outline: none; transition: border-color 0.2s;
  }
  .modal input:focus, .modal textarea:focus, .modal select:focus { border-color: var(--coral); }
  .modal textarea { min-height: 90px; resize: vertical; }
  .color-picker-row { display: flex; gap: 0.6rem; margin-bottom: 1rem; }
  .color-opt {
    width: 36px; height: 36px; border-radius: 50%;
    border: 2px solid transparent; cursor: pointer;
    transition: border-color 0.15s, transform 0.15s;
    display: flex; align-items: center; justify-content: center; font-size: 1rem;
  }
  .color-opt.selected { border-color: var(--dark); transform: scale(1.15); }
  .modal-actions { display: flex; gap: 0.8rem; margin-top: 0.5rem; }
  .btn-save {
    background: var(--dark); color: white; padding: 0.75rem 1.8rem; border-radius: 50px;
    border: 2px solid var(--dark); font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem; font-weight: 500; cursor: pointer;
  }
  .btn-save:hover { background: var(--coral); border-color: var(--coral); }
  .btn-cancel {
    background: transparent; color: var(--dark); padding: 0.75rem 1.8rem; border-radius: 50px;
    border: 2px solid #ddd; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; cursor: pointer;
  }
  .btn-cancel:hover { border-color: var(--dark); }

  .edit-banner {
    position: fixed; bottom: 1.5rem; right: 1.5rem; z-index: 90;
    background: var(--dark); color: white; padding: 0.7rem 1.3rem; border-radius: 50px;
    font-size: 0.85rem; font-weight: 500; box-shadow: 0 4px 20px rgba(0,0,0,0.3);
    cursor: pointer; border: none; display: flex; align-items: center; gap: 0.5rem;
    font-family: 'DM Sans', sans-serif; transition: background 0.2s, transform 0.15s;
  }
  .edit-banner:hover { background: var(--coral); transform: translateY(-2px); }

  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 4rem 1.5rem; }
    .about-inner { grid-template-columns: 1fr; gap: 2.5rem; }
    .form-row { grid-template-columns: 1fr; }
    .results-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">shraddha<span>creates</span></div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#contact" class="nav-cta">Hire me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-blobs">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>
  </div>
  <div class="hero-inner">
    <div class="hero-tag">✨ Marketing Portfolio</div>
    <h1 class="hero-title">
      Creative<br>
      <span class="highlight">Marketing</span><br>
      That Converts.
    </h1>
    <p class="hero-sub">Hi, I'm Shraddha — an aspiring digital marketer and content strategist specialising in social media growth, campaign building, and creative copywriting.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">See My Work →</a>
      <a href="#contact" class="btn-outline">Let's Talk</a>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>scroll down</span>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-inner">
    <div class="about-image-wrap">
      <div class="about-img-placeholder">🌸</div>
      <div class="about-sticker">Open to<br>opportunities 🚀</div>
    </div>
    <div class="about-text">
      <span class="section-tag">About Me</span>
      <h2 class="section-title">Marketing is storytelling with a strategy.</h2>
      <p>I'm an aspiring digital marketer who believes the best campaigns don't just sell — they create genuine connections between brands and people. I blend data-driven thinking with vibrant, on-brand content that resonates.</p>
      <p>From social media strategies and content campaigns to brand identity and copywriting, I bring a full-spectrum creative approach to every project I take on.</p>
      <div class="about-skills">
        <span class="skill-chip chip-coral">Social Media</span>
        <span class="skill-chip chip-yellow">Content Strategy</span>
        <span class="skill-chip chip-mint">Campaign Building</span>
        <span class="skill-chip chip-lavender">Copywriting</span>
        <span class="skill-chip chip-sky">Instagram Marketing</span>
        <span class="skill-chip chip-coral">Brand Identity</span>
        <span class="skill-chip chip-yellow">Analytics</span>
        <span class="skill-chip chip-mint">Creative Direction</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="projects-header">
    <div>
      <span class="section-tag">My Work</span>
      <h2 class="section-title">Selected Projects</h2>
    </div>
    <button class="btn-outline" onclick="openAddModal()" style="font-family:'DM Sans',sans-serif;cursor:pointer;">+ Add Project</button>
  </div>
  <div class="projects-grid" id="projectsGrid"></div>
</section>

<!-- CONTACT -->
<section id="contact">
  <span class="section-tag">Get In Touch</span>
  <h2 class="section-title">Let's make something <span class="highlight">amazing</span> together.</h2>
  <p>Have a project in mind? I'd love to hear about it. Drop a message and I'll get back to you soon.</p>
  <div class="contact-grid">
    <a href="mailto:dshraddha515@gmail.com" class="contact-pill"><span>✉️</span>dshraddha515@gmail.com</a>
    <a href="https://www.linkedin.com/in/shraddha-dubey-1234qwer/" class="contact-pill" target="_blank"><span>💼</span> LinkedIn</a>
  </div>
  <form class="contact-form" onsubmit="handleSubmit(event)">
    <div class="form-row">
      <input type="text" placeholder="Your name" required>
      <input type="email" placeholder="Your email" required>
    </div>
    <input type="text" placeholder="Subject">
    <textarea placeholder="Tell me about your project..."></textarea>
    <button type="submit" class="form-submit">Send Message ✨</button>
  </form>
</section>

<footer>
  <p>© 2025 <span>shraddhacreates</span> — Made with 💛 and strategy.</p>
</footer>

<button class="edit-banner" onclick="toggleEditMode()" id="editBtn">✏️ Edit Mode</button>

<!-- CASE STUDY MODAL -->
<div class="case-overlay" id="caseOverlay" onclick="closeCaseOnOverlay(event)">
  <div class="case-modal" id="caseModal">
    <button class="case-close" onclick="closeCase()">×</button>
    <div class="case-thumb thumb-coral" id="caseThumb"><span style="position:relative;z-index:2" id="caseEmoji">☕️</span></div>
    <div class="case-body" id="caseBody"></div>
  </div>
</div>

<!-- ADD PROJECT MODAL -->
<div class="modal-overlay" id="projectModal" onclick="closeModalOnOverlay(event)">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">×</button>
    <h2 id="modalTitle">Add Project</h2>
    <label>Project Title</label>
    <input type="text" id="projTitle" placeholder="e.g. Instagram Rebrand">
    <label>Category</label>
    <input type="text" id="projCategory" placeholder="e.g. Social Media Campaign">
    <label>Short Description</label>
    <textarea id="projDesc" placeholder="Brief summary shown on the card..."></textarea>
    <label>Tags (comma separated)</label>
    <input type="text" id="projTags" placeholder="e.g. Instagram, Canva, Analytics">
    <label>Results (comma separated)</label>
    <input type="text" id="projResults" placeholder="e.g. +35% traffic, 84 redemptions">
    <label>Card Colour</label>
    <div class="color-picker-row">
      <div class="color-opt selected" data-color="coral" style="background:#FF6B6B" onclick="selectColor(this)">✓</div>
      <div class="color-opt" data-color="yellow" style="background:#FFD93D" onclick="selectColor(this)"></div>
      <div class="color-opt" data-color="mint" style="background:#6BCB77" onclick="selectColor(this)"></div>
      <div class="color-opt" data-color="lavender" style="background:#C77DFF" onclick="selectColor(this)"></div>
    </div>
    <label>Emoji Icon</label>
    <input type="text" id="projEmoji" placeholder="e.g. 🚀" maxlength="4" style="width:80px">
    <label>Badge Label</label>
    <input type="text" id="projBadge" placeholder="e.g. Social">
    <div class="modal-actions">
      <button class="btn-save" onclick="saveProject()">Save Project</button>
      <button class="btn-cancel" onclick="closeModal()">Cancel</button>
      <button class="btn-cancel" id="deleteBtn" onclick="deleteProject()" style="display:none;border-color:#FF6B6B;color:#FF6B6B">Delete</button>
    </div>
  </div>
</div>

<script>
// ── Project Data ──
let projects = [
  {
    title: 'The "Mid-Week Study Oasis" Campaign',
    category: "Social Media Campaign",
    desc: "A targeted 1-week Instagram campaign for a coffee shop near a college campus, designed to boost weekday afternoon foot traffic among students.",
    tags: ["Instagram", "Copywriting", "Content Strategy", "Social Proof"],
    results: ["+35% foot traffic", "84 redemptions", "+12% followers"],
    color: "coral", emoji: "☕️", badge: "Social",
    caseStudy: {
      client: "The Daily Grind Coffee Co. (Mock Project)",
      role: "Social Media Strategist & Content Creator",
      goal: "Increase weekday afternoon foot traffic from local college students using a targeted 1-week Instagram campaign.",
      strategy: "The Daily Grind is located near a college campus but struggles with empty tables on Tuesday and Wednesday afternoons. I designed a 3-part Instagram campaign positioning the shop as the ultimate student study escape — with targeted incentives and relatable content.",
      posts: [
        {
          num: "Post 1",
          title: "The Aesthetic Invitation",
          visual: "A cozy photo of a corner table with a laptop, notebooks, and a fresh iced latte.",
          headline: '"Binge after class? ☕️"',
          caption: '"Swap the noisy campus library for your new favorite study escape. We\'ve got fast Wi-Fi, endless outlets, and the caffeine boost you need to survive finals week. Come find your cozy corner at The Daily Grind today. 📚💻"'
        },
        {
          num: "Post 2",
          title: "The Mid-Week BOGO Offer",
          visual: "A quick video clip of a barista pouring milk into a beautiful matcha latte.",
          headline: '"Thirsty noon, hungry studies? 🕒📚"',
          caption: '"Tuesday afternoon blues? ☕️ Bring your study buddy to The Daily Grind between 2 PM and 6 PM on Tuesdays or Wednesdays, show your student ID, and get Buy One, Get One 50% Off on all large drinks!"'
        },
        {
          num: "Post 3",
          title: "The Student Review (Social Proof)",
          visual: "A clean, colorful graphic showing a 5-star rating layout.",
          headline: '"Too cliché? Hear from them. 💬"',
          caption: '"Don\'t take our word for it — ask Sarah! 💻 Drop by this week and see why we\'re the neighborhood\'s favorite hidden gem."'
        }
      ],
      results: [
        { num: "+35%", label: "Weekday Foot Traffic" },
        { num: "84", label: "Student Pairs Redeemed BOGO" },
        { num: "+12%", label: "Local Instagram Followers" }
      ]
    }
  }
];

let editingIndex = -1;
let selectedColor = "coral";
let editMode = false;

// ── Render Projects ──
function renderProjects() {
  const grid = document.getElementById('projectsGrid');
  grid.innerHTML = '';
  projects.forEach((p, i) => {
    const card = document.createElement('div');
    card.className = 'project-card';
    card.onclick = () => editMode ? openEditModal(i) : openCase(i);
    card.innerHTML = `
      <div class="project-thumb thumb-${p.color}">
        <span style="position:relative;z-index:2">${p.emoji || '⭐'}</span>
        <div class="project-badge">${p.badge || ''}</div>
      </div>
      <div class="project-body">
        <div class="project-category">${p.category}</div>
        <h3 class="project-title">${p.title}</h3>
        <p class="project-desc">${p.desc}</p>
        <div class="project-tags">${p.tags.map(t => `<span class="project-tag">${t}</span>`).join('')}</div>
        ${p.results ? `<div class="project-results">${p.results.map(r => `<span class="result-pill">${r}</span>`).join('')}</div>` : ''}
      </div>
    `;
    grid.appendChild(card);
  });
  // Add card
  const addCard = document.createElement('div');
  addCard.className = 'add-project-card';
  addCard.onclick = openAddModal;
  addCard.innerHTML = `<div class="add-icon">+</div><span style="font-size:.9rem;font-weight:500">Add a new project</span>`;
  grid.appendChild(addCard);
}

// ── Case Study ──
function openCase(i) {
  const p = projects[i];
  if (!p.caseStudy) return;
  const cs = p.caseStudy;

  const thumb = document.getElementById('caseThumb');
  thumb.className = `case-thumb thumb-${p.color}`;
  document.getElementById('caseEmoji').textContent = p.emoji;

  let html = `
    <div class="case-meta">
      <span class="case-meta-pill" style="background:#FFF0F0;color:var(--coral)">${p.category}</span>
      <span class="case-meta-pill" style="background:#F9F9F9">${cs.role}</span>
    </div>
    <h2 class="case-title">${p.title}</h2>
    <p class="case-subtitle">Client: ${cs.client}</p>
    <hr class="case-divider">
    <span class="case-section-label">The Goal</span>
    <p>${cs.goal}</p>
    <span class="case-section-label">The Strategy</span>
    <p>${cs.strategy}</p>
    <hr class="case-divider">
    <span class="case-section-label">Content Breakdown</span>
  `;

  if (cs.posts) {
    cs.posts.forEach(post => {
      html += `
        <div class="post-card">
          <div class="post-card-header">
            <span class="post-num">${post.num}</span>
            <span class="post-card-title">${post.title}</span>
          </div>
          <p><strong>Visual:</strong> ${post.visual}</p>
          <p><strong>Headline:</strong> ${post.headline}</p>
          <div class="caption">${post.caption}</div>
        </div>
      `;
    });
  }

  if (cs.results) {
    html += `<hr class="case-divider"><span class="case-section-label">Campaign Results (Estimated)</span>
    <div class="results-grid">`;
    cs.results.forEach(r => {
      html += `<div class="result-box"><div class="result-num">${r.num}</div><div class="result-label">${r.label}</div></div>`;
    });
    html += `</div>`;
  }

  document.getElementById('caseBody').innerHTML = html;
  document.getElementById('caseOverlay').classList.add('open');
  document.body.style.overflow = 'hidden';
}
function closeCase() {
  document.getElementById('caseOverlay').classList.remove('open');
  document.body.style.overflow = '';
}
function closeCaseOnOverlay(e) {
  if (e.target === document.getElementById('caseOverlay')) closeCase();
}

// ── Edit Mode ──
function toggleEditMode() {
  editMode = !editMode;
  const btn = document.getElementById('editBtn');
  btn.textContent = editMode ? '👁️ View Mode' : '✏️ Edit Mode';
  btn.style.background = editMode ? '#6BCB77' : '';
  renderProjects();
}

// ── Add / Edit Modal ──
function openAddModal() {
  editingIndex = -1;
  document.getElementById('modalTitle').textContent = 'Add Project';
  ['projTitle','projCategory','projDesc','projTags','projResults','projEmoji','projBadge'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('deleteBtn').style.display = 'none';
  selectColorByName('coral');
  document.getElementById('projectModal').classList.add('open');
}
function openEditModal(i) {
  if (!editMode) return;
  editingIndex = i;
  const p = projects[i];
  document.getElementById('modalTitle').textContent = 'Edit Project';
  document.getElementById('projTitle').value = p.title;
  document.getElementById('projCategory').value = p.category;
  document.getElementById('projDesc').value = p.desc;
  document.getElementById('projTags').value = p.tags.join(', ');
  document.getElementById('projResults').value = (p.results || []).join(', ');
  document.getElementById('projEmoji').value = p.emoji || '';
  document.getElementById('projBadge').value = p.badge || '';
  document.getElementById('deleteBtn').style.display = 'block';
  selectColorByName(p.color);
  document.getElementById('projectModal').classList.add('open');
}
function closeModal() { document.getElementById('projectModal').classList.remove('open'); }
function closeModalOnOverlay(e) { if (e.target === document.getElementById('projectModal')) closeModal(); }

function selectColor(el) {
  document.querySelectorAll('.color-opt').forEach(o => { o.classList.remove('selected'); o.textContent = ''; });
  el.classList.add('selected'); el.textContent = '✓';
  selectedColor = el.dataset.color;
}
function selectColorByName(name) {
  document.querySelectorAll('.color-opt').forEach(o => {
    o.classList.remove('selected'); o.textContent = '';
    if (o.dataset.color === name) { o.classList.add('selected'); o.textContent = '✓'; }
  });
  selectedColor = name;
}
function saveProject() {
  const title = document.getElementById('projTitle').value.trim();
  if (!title) { alert('Please add a title!'); return; }
  const p = {
    title, color: selectedColor,
    category: document.getElementById('projCategory').value.trim() || 'Marketing',
    desc: document.getElementById('projDesc').value.trim() || '',
    tags: document.getElementById('projTags').value.split(',').map(t => t.trim()).filter(Boolean),
    results: document.getElementById('projResults').value.split(',').map(t => t.trim()).filter(Boolean),
    emoji: document.getElementById('projEmoji').value.trim() || '⭐',
    badge: document.getElementById('projBadge').value.trim() || ''
  };
  if (editingIndex === -1) projects.push(p);
  else { p.caseStudy = projects[editingIndex].caseStudy; projects[editingIndex] = p; }
  closeModal(); renderProjects();
}
function deleteProject() {
  if (editingIndex < 0) return;
  if (confirm('Delete this project?')) { projects.splice(editingIndex, 1); closeModal(); renderProjects(); }
}

function handleSubmit(e) {
  e.preventDefault();
  const btn = e.target.querySelector('.form-submit');
  btn.textContent = "✅ Sent! I'll be in touch.";
  btn.style.background = '#6BCB77'; btn.disabled = true;
}

document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    e.preventDefault();
    document.querySelector(a.getAttribute('href'))?.scrollIntoView({ behavior: 'smooth' });
  });
});

renderProjects();
</script>
</body>
</html>
