
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
    --text-muted: #888;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--dark); overflow-x: hidden; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.2rem 2.5rem;
    background: rgba(255,248,240,0.88); backdrop-filter: blur(12px);
    border-bottom: 1.5px dashed rgba(255,107,107,0.25);
  }
  .nav-logo { font-family: 'Playfair Display', serif; font-size: 1.3rem; font-weight: 900; color: var(--coral); }
  .nav-logo span { color: var(--dark); }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--dark); font-size: 0.9rem; font-weight: 500; transition: color 0.2s; }
  .nav-links a:hover { color: var(--coral); }
  .nav-cta { background: var(--coral); color: white !important; padding: 0.45rem 1.2rem; border-radius: 50px; }
  .nav-cta:hover { background: #e55555 !important; }

  /* HERO */
  #hero { min-height: 100vh; display: flex; align-items: center; padding: 7rem 2.5rem 4rem; position: relative; overflow: hidden; }
  .hero-blobs { position: absolute; inset: 0; pointer-events: none; z-index: 0; }
  .blob { position: absolute; border-radius: 50%; filter: blur(70px); opacity: 0.35; animation: float 8s ease-in-out infinite; }
  .blob-1 { width: 420px; height: 420px; background: var(--coral); top: -100px; right: -80px; }
  .blob-2 { width: 320px; height: 320px; background: var(--yellow); bottom: 0; left: -80px; animation-delay: 2s; }
  .blob-3 { width: 250px; height: 250px; background: var(--lavender); top: 40%; right: 20%; animation-delay: 4s; }
  @keyframes float { 0%,100%{transform:translateY(0) scale(1);} 50%{transform:translateY(-30px) scale(1.05);} }

  .hero-inner { max-width: 1100px; margin: 0 auto; width: 100%; position: relative; z-index: 1; display: grid; grid-template-columns: 1fr auto; gap: 4rem; align-items: center; }
  .hero-text {}
  .hero-tag { display: inline-block; background: var(--yellow); color: var(--dark); font-size: 0.8rem; font-weight: 500; padding: 0.3rem 1rem; border-radius: 50px; margin-bottom: 1.5rem; border: 2px solid var(--dark); animation: slideDown 0.7s ease both; }
  .hero-title { font-family: 'Playfair Display', serif; font-size: clamp(2.4rem, 5vw, 4.5rem); font-weight: 900; line-height: 1.05; margin-bottom: 1.5rem; animation: slideUp 0.8s 0.1s ease both; }
  .hero-title .highlight { color: var(--coral); position: relative; display: inline-block; }
  .hero-title .highlight::after { content:''; position:absolute; bottom:4px; left:0; right:0; height:6px; background:var(--yellow); z-index:-1; border-radius:3px; }
  .hero-sub { font-size: 1.05rem; color: #555; max-width: 520px; line-height: 1.85; margin-bottom: 2.5rem; animation: slideUp 0.8s 0.2s ease both; }
  .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; animation: slideUp 0.8s 0.3s ease both; }

  .hero-photo-wrap { position: relative; flex-shrink: 0; animation: slideUp 0.9s 0.2s ease both; }
  .hero-photo {
    width: 280px; height: 360px; border-radius: 24px;
    object-fit: cover; object-position: top;
    border: 3px solid var(--dark);
    box-shadow: 8px 8px 0 var(--dark);
    display: block;
  }
  .hero-photo-badge {
    position: absolute; bottom: -18px; left: -18px;
    background: var(--yellow); color: var(--dark);
    font-weight: 700; font-size: 0.8rem;
    padding: 0.8rem 1rem; border-radius: 14px;
    border: 2px solid var(--dark); line-height: 1.4;
    box-shadow: 3px 3px 0 var(--dark);
  }

  .btn-primary { background: var(--dark); color: white; padding: 0.85rem 2rem; border-radius: 50px; text-decoration: none; font-weight: 500; font-size: 0.95rem; border: 2px solid var(--dark); transition: transform 0.2s, background 0.2s; display: inline-block; }
  .btn-primary:hover { transform: translateY(-2px); background: var(--coral); border-color: var(--coral); }
  .btn-outline { background: transparent; color: var(--dark); padding: 0.85rem 2rem; border-radius: 50px; text-decoration: none; font-weight: 500; font-size: 0.95rem; border: 2px solid var(--dark); transition: transform 0.2s, background 0.2s; display: inline-block; }
  .btn-outline:hover { transform: translateY(-2px); background: var(--yellow); }

  .hero-scroll { position: absolute; bottom: 2.5rem; left: 2.5rem; z-index: 1; display: flex; align-items: center; gap: 0.7rem; font-size: 0.8rem; color: var(--text-muted); font-weight: 500; }
  .scroll-line { width: 50px; height: 1.5px; background: var(--text-muted); animation: scrollLine 1.5s ease-in-out infinite alternate; }
  @keyframes scrollLine { from{width:20px;} to{width:60px;} }
  @keyframes slideDown { from{opacity:0;transform:translateY(-20px);} to{opacity:1;transform:translateY(0);} }
  @keyframes slideUp { from{opacity:0;transform:translateY(30px);} to{opacity:1;transform:translateY(0);} }

  /* SECTION BASE */
  section { padding: 6rem 2.5rem; }
  .section-inner { max-width: 1100px; margin: 0 auto; }
  .section-tag { font-size: 0.78rem; font-weight: 500; letter-spacing: 2px; text-transform: uppercase; color: var(--coral); margin-bottom: 0.8rem; display: block; }
  .section-title { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 4vw, 3rem); font-weight: 700; line-height: 1.15; margin-bottom: 1.2rem; }

  /* ABOUT */
  #about { background: white; }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; }
  .about-col { min-width: 0; }
  .about-col p { color: #555; line-height: 1.9; margin-bottom: 1.2rem; font-size: 0.97rem; }
  .about-col-right { display: flex; flex-direction: column; gap: 1.2rem; }
  .about-quote-card { background: var(--dark); border-radius: 20px; padding: 1.8rem; border: 2px solid var(--dark); }
  .about-quote-icon { font-size: 1.8rem; margin-bottom: 0.8rem; }
  .about-quote-text { font-size: 1rem; line-height: 1.75; color: rgba(255,255,255,0.88); font-style: italic; margin-bottom: 0.8rem; }
  .about-quote-name { font-size: 0.82rem; color: var(--yellow); font-weight: 600; }
  .about-passion-card { background: white; border-radius: 20px; padding: 1.6rem; border: 2px solid var(--dark); box-shadow: 4px 4px 0 var(--dark); display: flex; flex-direction: column; gap: 1.1rem; }
  .about-passion-row { display: flex; align-items: flex-start; gap: 0.9rem; }
  .about-passion-icon { font-size: 1.3rem; flex-shrink: 0; margin-top: 2px; }
  .about-passion-label { font-size: 0.7rem; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; color: var(--coral); margin-bottom: 0.2rem; }
  .about-passion-value { font-size: 0.9rem; color: #444; font-weight: 500; }
  .about-skills { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 2rem; }
  .skill-chip { padding: 0.35rem 1rem; border-radius: 50px; font-size: 0.82rem; font-weight: 500; border: 1.5px solid var(--dark); transition: transform 0.15s; cursor: default; }
  .skill-chip:hover { transform: translateY(-2px); }
  .chip-coral{background:#FFE5E5;color:#c0392b;} .chip-yellow{background:#FFF8D6;color:#8a6d00;} .chip-mint{background:#E5F7E8;color:#1e7a2f;} .chip-lavender{background:#F2E0FF;color:#6a0dad;} .chip-sky{background:#E0F5FF;color:#0277a8;}

  
  .about-stat-card { background: var(--cream); border-radius: 20px; border: 2px solid var(--dark); padding: 1.8rem; margin-bottom: 1.2rem; box-shadow: 4px 4px 0 var(--dark); }
  .about-stat-card h3 { font-family: 'Playfair Display', serif; font-size: 2.2rem; font-weight: 900; color: var(--coral); margin-bottom: 0.2rem; }
  .about-stat-card p { font-size: 0.88rem; color: #666; }
  .about-stat-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }

  /* PROJECTS */
  #projects { background: var(--cream); }
  .projects-header { display: flex; justify-content: space-between; align-items: flex-end; flex-wrap: wrap; gap: 1rem; margin-bottom: 3.5rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1.8rem; }
  .project-card { background: white; border-radius: 20px; border: 2px solid var(--dark); overflow: hidden; transition: transform 0.25s, box-shadow 0.25s; box-shadow: 4px 4px 0 var(--dark); cursor: pointer; }
  .project-card:hover { transform: translate(-4px,-4px); box-shadow: 8px 8px 0 var(--dark); }
  .project-thumb { height: 200px; display: flex; align-items: center; justify-content: center; font-size: 3.5rem; position: relative; overflow: hidden; }
  .project-thumb::after { content:''; position:absolute; inset:0; background:repeating-linear-gradient(60deg,transparent,transparent 8px,rgba(255,255,255,0.1) 8px,rgba(255,255,255,0.1) 16px); }
  .thumb-coral{background:linear-gradient(135deg,#FFB5B5,#FF6B6B);} .thumb-yellow{background:linear-gradient(135deg,#FFF3A3,#FFD93D);} .thumb-mint{background:linear-gradient(135deg,#B5EAB9,#6BCB77);} .thumb-lavender{background:linear-gradient(135deg,#E5C5FF,#C77DFF);}
  .project-badge { position:absolute; top:1rem; right:1rem; z-index:2; background:var(--dark); color:white; font-size:0.7rem; font-weight:500; padding:0.25rem 0.7rem; border-radius:50px; }
  .project-body { padding: 1.5rem; }
  .project-category { font-size:0.72rem; font-weight:500; letter-spacing:1.5px; text-transform:uppercase; color:var(--coral); margin-bottom:0.4rem; }
  .project-title { font-family:'Playfair Display',serif; font-size:1.3rem; font-weight:700; margin-bottom:0.6rem; }
  .project-desc { font-size:0.88rem; color:#666; line-height:1.7; margin-bottom:1.2rem; }
  .project-tags { display:flex; flex-wrap:wrap; gap:0.4rem; }
  .project-tag { font-size:0.72rem; padding:0.2rem 0.6rem; border-radius:50px; border:1px solid #ddd; color:#666; }
  .project-results { margin-top:1rem; padding-top:1rem; border-top:1px dashed #eee; display:flex; gap:0.8rem; flex-wrap:wrap; }
  .result-pill { background:#FFF0F0; color:var(--coral); font-size:0.75rem; font-weight:600; padding:0.3rem 0.75rem; border-radius:50px; border:1px solid #FFD5D5; }
  .view-case-btn { display:inline-flex; align-items:center; gap:0.4rem; margin-top:1rem; font-size:0.82rem; font-weight:600; color:var(--coral); background:none; border:none; cursor:pointer; font-family:'DM Sans',sans-serif; padding:0; }
  .view-case-btn:hover { text-decoration:underline; }

  .add-project-card { background:white; border-radius:20px; border:2px dashed #ccc; display:flex; flex-direction:column; align-items:center; justify-content:center; min-height:380px; gap:1rem; cursor:pointer; transition:border-color 0.2s,background 0.2s; color:var(--text-muted); }
  .add-project-card:hover { border-color:var(--coral); background:#fff8f8; color:var(--coral); }
  .add-icon { width:56px; height:56px; border-radius:50%; background:#f5f5f5; display:flex; align-items:center; justify-content:center; font-size:1.8rem; transition:background 0.2s; }
  .add-project-card:hover .add-icon { background:#FFE5E5; }

  /* CASE STUDY MODAL */
  .case-overlay { display:none; position:fixed; inset:0; z-index:200; background:rgba(10,10,20,0.8); overflow-y:auto; padding:2rem 1rem; }
  .case-overlay.open { display:block; }
  .case-modal { background:white; border-radius:28px; max-width:760px; width:100%; margin:0 auto; border:2px solid var(--dark); box-shadow:10px 10px 0 var(--dark); animation:popIn 0.3s ease both; overflow:hidden; position:relative; }
  @keyframes popIn { from{opacity:0;transform:scale(0.95) translateY(20px);} to{opacity:1;transform:scale(1) translateY(0);} }
  .case-close { position:absolute; top:1.2rem; right:1.5rem; background:white; border:2px solid var(--dark); border-radius:50%; width:36px; height:36px; font-size:1.2rem; cursor:pointer; color:#555; z-index:10; display:flex; align-items:center; justify-content:center; }
  .case-close:hover { background:var(--coral); color:white; border-color:var(--coral); }

  .case-hero-band { padding:2.5rem 2.5rem 2rem; }
  .case-meta { display:flex; gap:0.6rem; flex-wrap:wrap; margin-bottom:1rem; }
  .case-meta-pill { font-size:0.75rem; padding:0.25rem 0.8rem; border-radius:50px; border:1.5px solid var(--dark); font-weight:500; }
  .case-title { font-family:'Playfair Display',serif; font-size:2rem; font-weight:900; margin-bottom:0.4rem; line-height:1.2; }
  .case-client { font-size:0.88rem; color:#888; }

  .case-section { padding:1.8rem 2.5rem; border-top:1.5px solid #f0f0f0; }
  .case-section:last-child { padding-bottom:2.5rem; }
  .case-label { font-size:0.7rem; font-weight:700; letter-spacing:2px; text-transform:uppercase; color:var(--coral); margin-bottom:0.8rem; display:block; }
  .case-section h3 { font-family:'Playfair Display',serif; font-size:1.25rem; font-weight:700; margin-bottom:0.6rem; }
  .case-section p { font-size:0.9rem; color:#555; line-height:1.85; }

  /* PROBLEM / GOAL boxes */
  .case-two-col { display:grid; grid-template-columns:1fr 1fr; gap:1rem; }
  .case-box { border-radius:14px; padding:1.2rem 1.4rem; border:1.5px solid; }
  .case-box-problem { background:#FFF0F0; border-color:#FFD5D5; }
  .case-box-goal { background:#F0FFF4; border-color:#B5EAB9; }
  .case-box-label { font-size:0.7rem; font-weight:700; letter-spacing:2px; text-transform:uppercase; margin-bottom:0.5rem; display:block; }
  .case-box-problem .case-box-label { color:var(--coral); }
  .case-box-goal .case-box-label { color:#1e7a2f; }
  .case-box p { font-size:0.88rem; color:#555; line-height:1.7; }

  /* STRATEGY STEPS */
  .strategy-steps { display:flex; flex-direction:column; gap:0.8rem; margin-top:0.5rem; }
  .strategy-step { display:flex; gap:1rem; align-items:flex-start; }
  .step-num { background:var(--coral); color:white; font-weight:700; font-size:0.78rem; width:28px; height:28px; border-radius:50%; display:flex; align-items:center; justify-content:center; flex-shrink:0; margin-top:2px; }
  .step-text { font-size:0.9rem; color:#555; line-height:1.7; }

  /* POST CARDS */
  .posts-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:1.2rem; margin-top:0.5rem; }
  .post-card { border-radius:16px; border:2px solid var(--dark); overflow:hidden; box-shadow:3px 3px 0 var(--dark); }
  .post-photo-area {
    height:200px; display:flex; align-items:center; justify-content:center;
    background:#f5f5f5; position:relative; cursor:pointer; overflow:hidden;
    transition:background 0.2s;
  }
  .post-photo-area:hover { background:#f0f0f0; }
  .post-photo-area img { width:100%; height:100%; object-fit:cover; display:block; }
  .post-photo-placeholder { display:flex; flex-direction:column; align-items:center; gap:0.5rem; color:#aaa; }
  .post-photo-placeholder .upload-icon { font-size:2rem; }
  .post-photo-placeholder span { font-size:0.75rem; font-weight:500; }
  .post-file-input { display:none; }
  .post-num-badge { position:absolute; top:0.6rem; left:0.6rem; background:var(--dark); color:white; font-size:0.65rem; font-weight:700; padding:0.2rem 0.5rem; border-radius:50px; z-index:2; }
  .post-info { padding:0.9rem 1rem; }
  .post-title { font-weight:700; font-size:0.88rem; color:var(--dark); margin-bottom:0.3rem; }
  .post-headline { font-size:0.78rem; color:var(--coral); font-weight:600; margin-bottom:0.3rem; }
  .post-caption { font-size:0.75rem; color:#777; line-height:1.55; font-style:italic; border-left:2px solid var(--yellow); padding-left:0.5rem; }

  /* RESULTS */
  .results-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:1rem; margin-top:0.5rem; }
  .result-box { background:#FFF0F0; border-radius:14px; padding:1.2rem; text-align:center; border:1.5px solid #FFD5D5; }
  .result-num { font-family:'Playfair Display',serif; font-size:2rem; font-weight:900; color:var(--coral); }
  .result-label { font-size:0.75rem; color:#888; margin-top:0.3rem; line-height:1.4; }

  /* CONTACT */
  #contact { background:var(--dark); color:white; text-align:center; }
  #contact .section-tag { color:var(--yellow); }
  #contact .section-title { color:white; }
  #contact .section-title .highlight { color:var(--coral); }
  #contact > .section-inner > p { color:rgba(255,255,255,0.6); max-width:480px; margin:0 auto 3rem; line-height:1.8; }
  .contact-grid { display:flex; justify-content:center; flex-wrap:wrap; gap:1.2rem; margin-bottom:3rem; }
  .contact-pill { display:flex; align-items:center; gap:0.6rem; background:rgba(255,255,255,0.06); color:white; padding:0.85rem 1.5rem; border-radius:50px; border:1.5px solid rgba(255,255,255,0.15); text-decoration:none; font-size:0.9rem; transition:background 0.2s,transform 0.15s; }
  .contact-pill:hover { background:rgba(255,255,255,0.12); transform:translateY(-2px); }
  .contact-form { max-width:560px; margin:0 auto; display:flex; flex-direction:column; gap:1rem; text-align:left; }
  .form-row { display:grid; grid-template-columns:1fr 1fr; gap:1rem; }
  .contact-form input,.contact-form textarea { width:100%; padding:0.9rem 1.2rem; background:rgba(255,255,255,0.07); color:white; border:1.5px solid rgba(255,255,255,0.15); border-radius:12px; font-family:'DM Sans',sans-serif; font-size:0.9rem; outline:none; transition:border-color 0.2s; resize:vertical; }
  .contact-form input::placeholder,.contact-form textarea::placeholder { color:rgba(255,255,255,0.3); }
  .contact-form input:focus,.contact-form textarea:focus { border-color:var(--coral); }
  .contact-form textarea { min-height:130px; }
  .form-submit { background:var(--coral); color:white; padding:0.95rem 2.5rem; border-radius:50px; border:none; font-family:'DM Sans',sans-serif; font-size:1rem; font-weight:500; cursor:pointer; transition:background 0.2s,transform 0.15s; align-self:flex-start; }
  .form-submit:hover { background:#e55555; transform:translateY(-2px); }

  footer { background:#111; color:rgba(255,255,255,0.4); text-align:center; padding:1.8rem; font-size:0.82rem; }
  footer span { color:var(--coral); }

  .edit-banner { position:fixed; bottom:1.5rem; right:1.5rem; z-index:90; background:var(--dark); color:white; padding:0.7rem 1.3rem; border-radius:50px; font-size:0.85rem; font-weight:500; box-shadow:0 4px 20px rgba(0,0,0,0.3); cursor:pointer; border:none; display:flex; align-items:center; gap:0.5rem; font-family:'DM Sans',sans-serif; transition:background 0.2s,transform 0.15s; }
  .edit-banner:hover { background:var(--coral); transform:translateY(-2px); }

  /* ADD PROJECT MODAL */
  .modal-overlay { display:none; position:fixed; inset:0; z-index:999; background:rgba(0,0,0,0.7); align-items:center; justify-content:center; padding:2rem; }
  .modal-overlay.open { display:flex; }
  .modal { background:white; border-radius:24px; max-width:560px; width:100%; padding:2.5rem; border:2px solid var(--dark); position:relative; box-shadow:8px 8px 0 var(--dark); max-height:90vh; overflow-y:auto; }
  .modal-close { position:absolute; top:1.2rem; right:1.5rem; background:none; border:none; font-size:1.5rem; cursor:pointer; color:#999; }
  .modal-close:hover { color:var(--coral); }
  .modal h2 { font-family:'Playfair Display',serif; font-size:1.6rem; margin-bottom:1.5rem; }
  .modal label { display:block; font-size:0.82rem; font-weight:500; margin-bottom:0.3rem; color:#444; }
  .modal input,.modal textarea { width:100%; padding:0.75rem 1rem; border:1.5px solid #ddd; border-radius:10px; font-family:'DM Sans',sans-serif; font-size:0.9rem; margin-bottom:1rem; outline:none; transition:border-color 0.2s; }
  .modal input:focus,.modal textarea:focus { border-color:var(--coral); }
  .modal textarea { min-height:80px; resize:vertical; }
  .color-picker-row { display:flex; gap:0.6rem; margin-bottom:1rem; }
  .color-opt { width:36px; height:36px; border-radius:50%; border:2px solid transparent; cursor:pointer; transition:border-color 0.15s,transform 0.15s; display:flex; align-items:center; justify-content:center; font-size:1rem; }
  .color-opt.selected { border-color:var(--dark); transform:scale(1.15); }
  .modal-actions { display:flex; gap:0.8rem; margin-top:0.5rem; }
  .btn-save { background:var(--dark); color:white; padding:0.75rem 1.8rem; border-radius:50px; border:2px solid var(--dark); font-family:'DM Sans',sans-serif; font-size:0.9rem; font-weight:500; cursor:pointer; }
  .btn-save:hover { background:var(--coral); border-color:var(--coral); }
  .btn-cancel { background:transparent; color:var(--dark); padding:0.75rem 1.8rem; border-radius:50px; border:2px solid #ddd; font-family:'DM Sans',sans-serif; font-size:0.9rem; cursor:pointer; }
  .btn-cancel:hover { border-color:var(--dark); }

  @media(max-width:900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 4rem 1.5rem; }

    /* Hero */
    #hero { padding: 6rem 1.5rem 3rem; }
    .hero-inner { grid-template-columns: 1fr; gap: 2rem; }
    .hero-photo-wrap { display: flex; justify-content: center; order: -1; }
    .hero-photo { width: 200px; height: 260px; }
    .hero-photo-badge { bottom: -14px; left: -10px; font-size: 0.7rem; padding: 0.6rem 0.8rem; }
    .hero-title { font-size: clamp(2.2rem, 10vw, 3.2rem); }
    .hero-sub { font-size: 0.96rem; }
    .hero-btns { gap: 0.8rem; }
    .btn-primary, .btn-outline { padding: 0.75rem 1.5rem; font-size: 0.88rem; }

    /* About */
    .about-grid { grid-template-columns: 1fr; gap: 2rem; }

    /* Projects */
    .projects-grid { grid-template-columns: 1fr; }
    .projects-header { flex-direction: column; align-items: flex-start; }

    /* Case study */
    .case-two-col { grid-template-columns: 1fr; }
    .posts-grid { grid-template-columns: 1fr; }
    .results-grid { grid-template-columns: 1fr 1fr; }
    .case-modal { border-radius: 20px; }
    .case-hero-band { padding: 1.8rem 1.5rem 1.5rem; }
    .case-section { padding: 1.4rem 1.5rem; }
    .case-title { font-size: 1.5rem; }

    /* Contact */
    .contact-grid { flex-direction: column; align-items: stretch; }
    .contact-pill { justify-content: center; }
    .form-row { grid-template-columns: 1fr; }

    /* Section titles */
    .section-title { font-size: clamp(1.7rem, 6vw, 2.4rem); }

    /* Edit button */
    .edit-banner { bottom: 1rem; right: 1rem; font-size: 0.78rem; padding: 0.55rem 1rem; }
  }
  @media(max-width: 480px) {
    .hero-photo { width: 160px; height: 210px; }
    .results-grid { grid-template-columns: 1fr; }
    .section-title { font-size: 1.6rem; }
    .about-passion-card { padding: 1.2rem; }
    .about-quote-card { padding: 1.4rem; }
  }
  @media(max-width:480px) {
    .hero-photo { width:180px; height:230px; }
    .about-stat-row { grid-template-columns:1fr; }
    .section-title { font-size:1.8rem; }
    .case-title { font-size:1.5rem; }
  }
</style>
</head>
<body>

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
    <div class="hero-text">
      <div class="hero-tag">✨ Marketing Portfolio</div>
      <h1 class="hero-title">Creative<br><span class="highlight">Marketing</span><br>That Converts.</h1>
      <p class="hero-sub">Hi there! I am Shraddha — a marketer in the making.</p>
      <div class="hero-btns">
        <a href="#projects" class="btn-primary">See My Work →</a>
        <a href="#contact" class="btn-outline">Let's Talk</a>
      </div>
    </div>
    <div class="hero-photo-wrap">
      <img src="data:image/jpeg;base64,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" alt="Shraddha" class="hero-photo">
      <div class="hero-photo-badge">Open to<br>opportunities 🚀</div>
    </div>
  </div>
  <div class="hero-scroll"><div class="scroll-line"></div><span>scroll down</span></div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-inner">
    <div class="about-grid">
      <div class="about-col">
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
      <div class="about-col about-col-right">
        <div class="about-quote-card">
          <div class="about-quote-icon">✨</div>
          <p class="about-quote-text">"I love exploring how brands tell stories, connect with communities, and create experiences that make people stop scrolling."</p>
          <p class="about-quote-name">— Shraddha</p>
        </div>
        <div class="about-passion-card">
          <div class="about-passion-row">
            <div class="about-passion-icon">🎯</div>
            <div>
              <div class="about-passion-label">Specialisation</div>
              <div class="about-passion-value">Social Media Growth &amp; Campaign Strategy</div>
            </div>
          </div>
          <div class="about-passion-row">
            <div class="about-passion-icon">✍️</div>
            <div>
              <div class="about-passion-label">Craft</div>
              <div class="about-passion-value">Creative Copywriting &amp; Content Creation</div>
            </div>
          </div>
          <div class="about-passion-row">
            <div class="about-passion-icon">🚀</div>
            <div>
              <div class="about-passion-label">Status</div>
              <div class="about-passion-value">Open to opportunities &amp; collaborations</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-inner">
    <div class="projects-header">
      <div>
        <span class="section-tag">My Work</span>
        <h2 class="section-title">Selected Projects</h2>
      </div>
      <button class="btn-outline" onclick="openAddModal()" id="addProjectBtn" style="font-family:'DM Sans',sans-serif;cursor:pointer;display:none;">+ Add Project</button>
    </div>
    <div class="projects-grid" id="projectsGrid"></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-inner">
    <span class="section-tag">Get In Touch</span>
    <h2 class="section-title">Let's make something <span class="highlight">amazing</span> together.</h2>
    <p>Have a project in mind? I'd love to hear about it. Drop a message and I'll get back to you soon.</p>
    <div class="contact-grid">
      <a href="mailto:dshraddha515@gmail.com" class="contact-pill"><span>✉️</span> dshraddha515@gmail.com</a>
      <a href="https://instagram.com/shraddhhaha" class="contact-pill" target="_blank"><span>📸</span> @shraddhhaha</a>
      <a href="https://linkedin.com" class="contact-pill" target="_blank"><span>💼</span> LinkedIn</a>
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
  </div>
</section>

<footer><p>© 2025 <span>shraddhacreates</span> — Made with 💛 and strategy.</p></footer>

<button class="edit-banner" onclick="toggleEditMode()" id="editBtn" style="display:none;">✏️ Edit Mode</button>

<!-- CASE STUDY MODAL -->
<div class="case-overlay" id="caseOverlay" onclick="closeCaseOnOverlay(event)">
  <div class="case-modal" id="caseModal">
    <button class="case-close" onclick="closeCase()">×</button>
    <div id="caseContent"></div>
  </div>
</div>

<!-- ADD PROJECT MODAL -->
<div class="modal-overlay" id="projectModal" onclick="closeModalOnOverlay(event)">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">×</button>
    <h2 id="modalTitle">Add Project</h2>
    <label>Project Title</label><input type="text" id="projTitle" placeholder="e.g. Instagram Rebrand">
    <label>Category</label><input type="text" id="projCategory" placeholder="e.g. Social Media Campaign">
    <label>Short Description</label><textarea id="projDesc" placeholder="Brief summary shown on the card..."></textarea>
    <label>Tags (comma separated)</label><input type="text" id="projTags" placeholder="e.g. Instagram, Canva, Analytics">
    <label>Results (comma separated)</label><input type="text" id="projResults" placeholder="e.g. +35% traffic, 84 redemptions">
    <label>Card Colour</label>
    <div class="color-picker-row">
      <div class="color-opt selected" data-color="coral" style="background:#FF6B6B" onclick="selectColor(this)">✓</div>
      <div class="color-opt" data-color="yellow" style="background:#FFD93D" onclick="selectColor(this)"></div>
      <div class="color-opt" data-color="mint" style="background:#6BCB77" onclick="selectColor(this)"></div>
      <div class="color-opt" data-color="lavender" style="background:#C77DFF" onclick="selectColor(this)"></div>
    </div>
    <label>Emoji Icon</label><input type="text" id="projEmoji" placeholder="e.g. 🚀" maxlength="4" style="width:80px">
    <label>Badge Label</label><input type="text" id="projBadge" placeholder="e.g. Social">
    <div class="modal-actions">
      <button class="btn-save" onclick="saveProject()">Save Project</button>
      <button class="btn-cancel" onclick="closeModal()">Cancel</button>
      <button class="btn-cancel" id="deleteBtn" onclick="deleteProject()" style="display:none;border-color:#FF6B6B;color:#FF6B6B">Delete</button>
    </div>
  </div>
</div>

<script>
// ── Data ──
let projects = [
  {
    title: 'The "Mid-Week Study Oasis" Campaign',
    category: "Social Media Campaign",
    desc: "A targeted 1-week Instagram campaign for a college-area coffee shop, designed to boost quiet weekday afternoons with student-focused content and a BOGO incentive.",
    tags: ["Instagram","Copywriting","Content Strategy","Social Proof","BOGO"],
    results: ["+35% foot traffic","84 BOGO redemptions","+12% followers"],
    color:"coral", emoji:"☕️", badge:"Social",
    postPhotos: [null, null, null],
    caseStudy: {
      client: "The Daily Grind Coffee Co. (Mock Project)",
      role: "Social Media Strategist & Content Creator",
      problem: "The Daily Grind sits near a college campus but struggles with nearly empty tables on Tuesday and Wednesday afternoons — prime hours that were going to waste.",
      goal: "Design a 1-week targeted Instagram campaign to drive weekday afternoon foot traffic specifically from local college students, using creative content and a compelling incentive.",
      strategy: [
        "Position The Daily Grind as the ultimate student study escape — cozy, connected, and affordable.",
        "Create 3 posts with distinct roles: aspiration, offer, and social proof — a proven content trio.",
        "Target college students with relatable language, student ID discounts, and shareable visuals.",
        "Use a time-limited BOGO offer to create urgency and bring students in pairs (multiplying reach)."
      ],
      posts: [
        { title:"The Aesthetic Invitation", headline:'"Binge after class? ☕️"', caption:'"Swap the noisy campus library for your new favorite study escape. We\'ve got fast Wi-Fi, endless outlets, and the caffeine boost you need to survive finals week. Come find your cozy corner at The Daily Grind today. 📚💻"', visual:"Cozy corner table with laptop, notebooks, and an iced latte." },
        { title:"The Mid-Week BOGO Offer", headline:'"Thirsty noon, hungry studies? 🕒📚"', caption:'"Tuesday afternoon blues? ☕️ Bring your study buddy between 2–6 PM on Tue/Wed, show your student ID, and get Buy One, Get One 50% Off on all large drinks!"', visual:"Barista pouring milk into a beautiful matcha latte — short video clip." },
        { title:"The Social Proof", headline:'"Too cliché? Hear from them. 💬"', caption:'"Don\'t take our word for it — ask Sarah! 💻 Drop by this week and see why we\'re the neighborhood\'s favorite hidden gem."', visual:"Clean 5-star rating graphic with a student testimonial." }
      ],
      results: [
        { num:"+35%", label:"Weekday afternoon foot traffic among college students" },
        { num:"84", label:"Student pairs redeemed the BOGO discount" },
        { num:"+12%", label:"Local Instagram followers gained in 7 days" }
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
        <span style="position:relative;z-index:2">${p.emoji||'⭐'}</span>
        <div class="project-badge">${p.badge||''}</div>
      </div>
      <div class="project-body">
        <div class="project-category">${p.category}</div>
        <h3 class="project-title">${p.title}</h3>
        <p class="project-desc">${p.desc}</p>
        <div class="project-tags">${p.tags.map(t=>`<span class="project-tag">${t}</span>`).join('')}</div>
        ${p.results?`<div class="project-results">${p.results.map(r=>`<span class="result-pill">${r}</span>`).join('')}</div>`:''}
        <button class="view-case-btn">View Case Study →</button>
      </div>
    `;
    grid.appendChild(card);
  });
  if (editMode) {
    const addCard = document.createElement('div');
    addCard.className = 'add-project-card';
    addCard.onclick = openAddModal;
    addCard.innerHTML = '<div class="add-icon">+</div><span style="font-size:.9rem;font-weight:500">Add a new project</span>';
    grid.appendChild(addCard);
  }
}

// ── Case Study ──
function openCase(i) {
  const p = projects[i];
  if (!p.caseStudy) return;
  const cs = p.caseStudy;

  let html = `
    <div class="case-hero-band thumb-${p.color}" style="padding:2.5rem 2.5rem 2rem;">
      <div class="case-meta">
        <span class="case-meta-pill" style="background:rgba(255,255,255,0.9)">${p.category}</span>
        <span class="case-meta-pill" style="background:rgba(255,255,255,0.7)">${cs.role}</span>
      </div>
      <div class="case-title" style="color:white;text-shadow:0 2px 12px rgba(0,0,0,0.15)">${p.title}</div>
      <div class="case-client" style="color:rgba(255,255,255,0.85)">Client: ${cs.client}</div>
    </div>

    <div class="case-section">
      <span class="case-label">The Problem & The Goal</span>
      <div class="case-two-col">
        <div class="case-box case-box-problem">
          <span class="case-box-label">🔴 The Problem</span>
          <p>${cs.problem}</p>
        </div>
        <div class="case-box case-box-goal">
          <span class="case-box-label">🎯 The Goal</span>
          <p>${cs.goal}</p>
        </div>
      </div>
    </div>

    <div class="case-section">
      <span class="case-label">The Strategy</span>
      <div class="strategy-steps">
        ${cs.strategy.map((s,idx)=>`<div class="strategy-step"><div class="step-num">${idx+1}</div><div class="step-text">${s}</div></div>`).join('')}
      </div>
    </div>

    <div class="case-section">
      <span class="case-label">My Designed Posts</span>
      <p style="font-size:0.85rem;color:#888;margin-bottom:1rem;">Click any post below to upload your design image.</p>
      <div class="posts-grid">
        ${cs.posts.map((post, pi) => {
          const hasPhoto = p.postPhotos && p.postPhotos[pi];
          return `<div class="post-card">
            <div class="post-photo-area" onclick="triggerUpload(${i}, ${pi})">
              ${hasPhoto
                ? `<img src="${p.postPhotos[pi]}" alt="Post ${pi+1}">`
                : `<div class="post-photo-placeholder"><div class="upload-icon">📸</div><span>Click to upload</span><span>your design</span></div>`
              }
              <div class="post-num-badge">Post ${pi+1}</div>
              <input type="file" accept="image/*" class="post-file-input" id="postFile_${i}_${pi}" onchange="handlePhotoUpload(${i}, ${pi}, this)">
            </div>
            <div class="post-info">
              <div class="post-title">${post.title}</div>
              <div class="post-headline">${post.headline}</div>
              <div class="post-caption">${post.caption}</div>
            </div>
          </div>`;
        }).join('')}
      </div>
    </div>

    <div class="case-section">
      <span class="case-label">Campaign Results (Estimated)</span>
      <div class="results-grid">
        ${cs.results.map(r=>`<div class="result-box"><div class="result-num">${r.num}</div><div class="result-label">${r.label}</div></div>`).join('')}
      </div>
    </div>
  `;

  document.getElementById('caseContent').innerHTML = html;
  document.getElementById('caseOverlay').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function triggerUpload(projIdx, postIdx) {
  document.getElementById(`postFile_${projIdx}_${postIdx}`).click();
}

function handlePhotoUpload(projIdx, postIdx, input) {
  if (!input.files || !input.files[0]) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    if (!projects[projIdx].postPhotos) projects[projIdx].postPhotos = [null,null,null];
    projects[projIdx].postPhotos[postIdx] = e.target.result;
    openCase(projIdx);
  };
  reader.readAsDataURL(input.files[0]);
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
  var pwd = prompt('Enter password:');
  if (pwd === 'shraddha@creates2025') {
    editMode = !editMode;
    const btn = document.getElementById('editBtn');
    const addBtn = document.getElementById('addProjectBtn');
    if (editMode) {
      btn.style.display = 'flex';
      btn.textContent = '👁️ View Mode';
      btn.style.background = '#6BCB77';
      if (addBtn) addBtn.style.display = 'inline-block';
    } else {
      btn.style.display = 'none';
      if (addBtn) addBtn.style.display = 'none';
    }
    renderProjects();
  } else if (pwd !== null) {
    alert('Incorrect password.');
  }
}

// Secret keyboard shortcut: press E then hold Shift+E to open edit mode
let _eCount = 0, _eTimer;
document.addEventListener('keydown', function(e) {
  if (e.key === 'E' && e.shiftKey) {
    _eCount++;
    clearTimeout(_eTimer);
    _eTimer = setTimeout(() => _eCount = 0, 1500);
    if (_eCount >= 3) {
      _eCount = 0;
      toggleEditMode();
    }
  }
});

function openAddModal() {
  editingIndex = -1;
  document.getElementById('modalTitle').textContent = 'Add Project';
  ['projTitle','projCategory','projDesc','projTags','projResults','projEmoji','projBadge'].forEach(id=>document.getElementById(id).value='');
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
  document.getElementById('projResults').value = (p.results||[]).join(', ');
  document.getElementById('projEmoji').value = p.emoji||'';
  document.getElementById('projBadge').value = p.badge||'';
  document.getElementById('deleteBtn').style.display = 'block';
  selectColorByName(p.color);
  document.getElementById('projectModal').classList.add('open');
}
function closeModal() { document.getElementById('projectModal').classList.remove('open'); }
function closeModalOnOverlay(e) { if (e.target===document.getElementById('projectModal')) closeModal(); }
function selectColor(el) {
  document.querySelectorAll('.color-opt').forEach(o=>{o.classList.remove('selected');o.textContent='';});
  el.classList.add('selected'); el.textContent='✓'; selectedColor=el.dataset.color;
}
function selectColorByName(name) {
  document.querySelectorAll('.color-opt').forEach(o=>{
    o.classList.remove('selected');o.textContent='';
    if(o.dataset.color===name){o.classList.add('selected');o.textContent='✓';}
  });
  selectedColor=name;
}
function saveProject() {
  const title = document.getElementById('projTitle').value.trim();
  if(!title){alert('Please add a title!');return;}
  const p = {
    title, color:selectedColor,
    category:document.getElementById('projCategory').value.trim()||'Marketing',
    desc:document.getElementById('projDesc').value.trim()||'',
    tags:document.getElementById('projTags').value.split(',').map(t=>t.trim()).filter(Boolean),
    results:document.getElementById('projResults').value.split(',').map(t=>t.trim()).filter(Boolean),
    emoji:document.getElementById('projEmoji').value.trim()||'⭐',
    badge:document.getElementById('projBadge').value.trim()||'',
    postPhotos:[null,null,null]
  };
  if(editingIndex===-1) projects.push(p);
  else { p.caseStudy=projects[editingIndex].caseStudy; p.postPhotos=projects[editingIndex].postPhotos; projects[editingIndex]=p; }
  closeModal(); renderProjects();
}
function deleteProject() {
  if(editingIndex<0) return;
  if(confirm('Delete this project?')){projects.splice(editingIndex,1);closeModal();renderProjects();}
}
function handleSubmit(e) {
  e.preventDefault();
  const btn=e.target.querySelector('.form-submit');
  btn.textContent="✅ Sent! I'll be in touch.";
  btn.style.background='#6BCB77'; btn.disabled=true;
}
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{e.preventDefault();document.querySelector(a.getAttribute('href'))?.scrollIntoView({behavior:'smooth'});});
});
renderProjects();
</script>
</body>
</html>
