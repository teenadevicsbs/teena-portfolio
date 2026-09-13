<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Teenu — Data Analytics × Marketing Growth</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #fafaf9;
    --bg2: #f3f1f7;
    --ink: #1a1625;
    --ink2: #4a4560;
    --ink3: #7c7a8e;
    --violet: #6b4fbb;
    --violet-light: #8b6fd4;
    --violet-pale: #ede8f8;
    --rose: #c96fa5;
    --grad: linear-gradient(135deg, #6b4fbb 0%, #c96fa5 100%);
    --grad-subtle: linear-gradient(135deg, #ede8f8 0%, #fce4f2 100%);
    --radius: 16px;
    --shadow: 0 4px 24px rgba(107,79,187,0.08);
    --shadow-lg: 0 12px 48px rgba(107,79,187,0.14);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    font-family: 'Inter', sans-serif;
    background: var(--bg);
    color: var(--ink);
    line-height: 1.6;
    overflow-x: hidden;
  }
  h1,h2,h3,h4 { font-family: 'Syne', sans-serif; line-height: 1.2; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(250,250,249,0.88);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(107,79,187,0.08);
    padding: 0 5%;
    height: 64px;
    display: flex; align-items: center; justify-content: space-between;
  }
  .nav-logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800; font-size: 1.25rem;
    background: var(--grad); -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    text-decoration: none; color: var(--ink2);
    font-size: 0.85rem; font-weight: 500;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--violet); }
  .nav-cta {
    background: var(--grad); color: #fff;
    border: none; border-radius: 100px; padding: 0.5rem 1.25rem;
    font-size: 0.82rem; font-weight: 600; cursor: pointer;
    font-family: 'Inter', sans-serif;
    text-decoration: none;
    transition: opacity 0.2s, transform 0.2s;
  }
  .nav-cta:hover { opacity: 0.88; transform: translateY(-1px); }
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
  .hamburger span { width: 24px; height: 2px; background: var(--ink); border-radius: 2px; }

  /* HERO */
  #home {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 100px 5% 80px;
    position: relative; overflow: hidden;
  }
  .hero-bg-orb {
    position: absolute; border-radius: 50%; filter: blur(80px); pointer-events: none;
  }
  .orb1 { width: 500px; height: 500px; background: rgba(107,79,187,0.12); top: -100px; right: -100px; }
  .orb2 { width: 300px; height: 300px; background: rgba(201,111,165,0.1); bottom: 50px; left: -50px; }
  .hero-inner { max-width: 760px; position: relative; z-index: 1; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: var(--violet-pale); color: var(--violet);
    border-radius: 100px; padding: 0.35rem 1rem;
    font-size: 0.78rem; font-weight: 600; letter-spacing: 0.01em;
    margin-bottom: 2rem;
  }
  .hero-badge::before { content: '●'; font-size: 0.6rem; color: var(--rose); }
  h1.hero-headline {
    font-size: clamp(2.6rem, 6vw, 4.8rem);
    font-weight: 800;
    color: var(--ink);
    margin-bottom: 1.25rem;
    letter-spacing: -0.02em;
  }
  .hero-headline span {
    background: var(--grad); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }
  .hero-tags {
    display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2rem;
  }
  .hero-tag {
    background: #fff; border: 1px solid rgba(107,79,187,0.2);
    border-radius: 100px; padding: 0.3rem 0.9rem;
    font-size: 0.8rem; color: var(--violet); font-weight: 500;
  }
  .hero-intro {
    font-size: 0.95rem; color: var(--ink2);
    max-width: 520px; line-height: 1.7; margin-bottom: 2.5rem;
  }
  .hero-btns { display: flex; flex-wrap: wrap; gap: 0.75rem; }
  .btn-primary {
    background: var(--grad); color: #fff;
    border: none; border-radius: 100px; padding: 0.8rem 2rem;
    font-size: 0.9rem; font-weight: 600; cursor: pointer;
    font-family: 'Inter', sans-serif; text-decoration: none;
    transition: opacity 0.2s, transform 0.15s;
    display: inline-block;
  }
  .btn-primary:hover { opacity: 0.88; transform: translateY(-2px); }
  .btn-outline {
    background: #fff; color: var(--violet);
    border: 1.5px solid var(--violet); border-radius: 100px; padding: 0.8rem 2rem;
    font-size: 0.9rem; font-weight: 600; cursor: pointer;
    font-family: 'Inter', sans-serif; text-decoration: none;
    transition: background 0.2s, color 0.2s, transform 0.15s;
    display: inline-block;
  }
  .btn-outline:hover { background: var(--violet-pale); transform: translateY(-2px); }
  .hero-proof {
    margin-top: 3.5rem; display: flex; align-items: center; gap: 1rem;
    padding-top: 2rem; border-top: 1px solid rgba(107,79,187,0.1);
  }
  .proof-num { font-family: 'Syne', sans-serif; font-size: 1.8rem; font-weight: 800; color: var(--violet); }
  .proof-label { font-size: 0.8rem; color: var(--ink3); line-height: 1.4; }
  .proof-divider { width: 1px; height: 36px; background: rgba(107,79,187,0.15); }

  /* SECTION BASE */
  section { padding: 100px 5%; }
  .section-label {
    font-size: 0.75rem; font-weight: 600; color: var(--violet);
    text-transform: uppercase; letter-spacing: 0.12em;
    margin-bottom: 0.75rem;
  }
  .section-title {
    font-size: clamp(2rem, 4vw, 3rem); font-weight: 800;
    color: var(--ink); letter-spacing: -0.02em;
    margin-bottom: 1rem;
  }
  .section-sub {
    font-size: 1rem; color: var(--ink2); max-width: 560px; line-height: 1.7;
    margin-bottom: 3rem;
  }
  .container { max-width: 1100px; margin: 0 auto; }

  /* METRICS SECTION */
  #growth { background: var(--ink); }
  #growth .section-label { color: var(--rose); }
  #growth .section-title { color: #fff; }
  #growth .section-sub { color: rgba(255,255,255,0.55); }
  .metrics-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 1.25rem; margin-top: 2.5rem;
  }
  .metric-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: var(--radius); padding: 1.75rem 1.5rem;
    transition: transform 0.25s, background 0.25s;
    position: relative; overflow: hidden;
  }
  .metric-card::before {
    content: ''; position: absolute; inset: 0;
    background: var(--grad); opacity: 0; transition: opacity 0.25s;
  }
  .metric-card:hover { transform: translateY(-4px); }
  .metric-card:hover::before { opacity: 0.06; }
  .metric-card.featured {
    border-color: rgba(107,79,187,0.5);
    background: rgba(107,79,187,0.1);
  }
  .metric-card.featured::before { opacity: 0.05; }
  .metric-value {
    font-family: 'Syne', sans-serif; font-size: 2.2rem; font-weight: 800;
    color: #fff; margin-bottom: 0.25rem; position: relative; z-index: 1;
  }
  .metric-card.featured .metric-value { color: #d4beff; font-size: 2.6rem; }
  .metric-growth {
    font-size: 0.85rem; font-weight: 700; color: #7eda9c;
    margin-bottom: 0.5rem; position: relative; z-index: 1;
  }
  .metric-label {
    font-size: 0.78rem; color: rgba(255,255,255,0.45);
    position: relative; z-index: 1;
  }
  .profile-stats {
    display: flex; gap: 2.5rem; margin-bottom: 3rem;
    border-bottom: 1px solid rgba(255,255,255,0.08); padding-bottom: 2.5rem;
  }
  .profile-stat-val { font-family: 'Syne', sans-serif; font-size: 2rem; font-weight: 800; color: #fff; }
  .profile-stat-label { font-size: 0.8rem; color: rgba(255,255,255,0.4); margin-top: 0.15rem; }

  /* CHART BAR */
  .chart-wrap { margin-top: 3.5rem; }
  .chart-title { font-size: 0.8rem; font-weight: 600; color: rgba(255,255,255,0.4); margin-bottom: 1.5rem; }
  .bar-row { display: flex; align-items: center; gap: 1rem; margin-bottom: 1rem; }
  .bar-label { font-size: 0.78rem; color: rgba(255,255,255,0.5); width: 120px; flex-shrink: 0; }
  .bar-track { flex: 1; height: 8px; background: rgba(255,255,255,0.06); border-radius: 4px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 4px; background: var(--grad); width: 0; transition: width 1.2s cubic-bezier(.25,.8,.25,1); }
  .bar-pct { font-size: 0.78rem; font-weight: 700; color: #7eda9c; width: 50px; text-align: right; }

  /* FUNNEL */
  #funnel { background: var(--bg2); }
  .funnel-step {
    flex: 1; min-width: 120px;
    background: #fff; border: 1px solid rgba(107,79,187,0.12);
    border-radius: var(--radius); padding: 1.5rem 1rem;
    text-align: center; position: relative;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .funnel-step:hover { transform: translateY(-4px); box-shadow: var(--shadow-lg); }
  .funnel-icon { font-size: 1.6rem; margin-bottom: 0.75rem; }
  .funnel-step-title { font-family: 'Syne', sans-serif; font-size: 0.85rem; font-weight: 700; color: var(--ink); margin-bottom: 0.3rem; }
  .funnel-step-sub { font-size: 0.72rem; color: var(--ink3); }
  .funnel-arrow { display: flex; align-items: center; color: var(--violet); font-size: 1.2rem; padding: 0 0.3rem; flex-shrink: 0; }
  .funnel-grid {
    display: flex; align-items: center; gap: 0.5rem;
    overflow-x: auto; padding-bottom: 0.5rem;
    margin-top: 2.5rem;
  }

  /* CASE STUDY */
  #case-study { background: var(--bg); }
  .case-header { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; margin-bottom: 3rem; }
  .case-role-tag { display: inline-flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 1.5rem; }
  .tag {
    background: var(--violet-pale); color: var(--violet);
    border-radius: 100px; padding: 0.3rem 0.85rem;
    font-size: 0.75rem; font-weight: 600;
  }
  .did-item { display: flex; gap: 0.75rem; margin-bottom: 0.6rem; align-items: flex-start; }
  .did-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--violet); flex-shrink: 0; margin-top: 0.45rem; }
  .did-text { font-size: 0.9rem; color: var(--ink2); line-height: 1.5; }
  .screenshots-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2.5rem; }
  .screenshot-card {
    border-radius: var(--radius); overflow: hidden;
    border: 1px solid rgba(107,79,187,0.12);
    box-shadow: var(--shadow);
  }
  .screenshot-card img { width: 100%; height: auto; display: block; }
  .screenshot-label { padding: 0.75rem 1rem; font-size: 0.78rem; color: var(--ink3); background: #fff; }

  /* WORKFLOW */
  #workflow { background: var(--bg2); }
  .workflow-steps { display: grid; grid-template-columns: repeat(5, 1fr); gap: 0; position: relative; margin-top: 3rem; }
  .workflow-steps::before {
    content: ''; position: absolute;
    top: 32px; left: 80px; right: 80px; height: 2px;
    background: linear-gradient(90deg, var(--violet) 0%, var(--rose) 100%);
    z-index: 0;
  }
  .workflow-step { text-align: center; position: relative; z-index: 1; padding: 0 0.5rem; }
  .workflow-num {
    width: 64px; height: 64px; border-radius: 50%;
    background: var(--grad); color: #fff;
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.1rem;
    margin: 0 auto 1rem;
    box-shadow: 0 4px 20px rgba(107,79,187,0.3);
  }
  .workflow-step-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 0.95rem; margin-bottom: 0.5rem; }
  .workflow-step-desc { font-size: 0.78rem; color: var(--ink3); line-height: 1.5; }

  /* SKILLS */
  #analytics { background: var(--bg); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1.5rem; margin-top: 2.5rem; }
  .skill-group {
    background: #fff; border-radius: var(--radius); padding: 1.75rem;
    border: 1px solid rgba(107,79,187,0.1); box-shadow: var(--shadow);
  }
  .skill-group-title {
    font-family: 'Syne', sans-serif; font-weight: 700; font-size: 0.9rem;
    color: var(--violet); margin-bottom: 1.25rem;
    padding-bottom: 0.75rem; border-bottom: 1px solid var(--violet-pale);
  }
  .skill-pill-wrap { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .skill-pill {
    background: var(--violet-pale); color: var(--ink2);
    border-radius: 100px; padding: 0.3rem 0.85rem;
    font-size: 0.78rem; font-weight: 500;
  }

  /* PROJECTS */
  #projects { background: var(--bg2); }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; margin-top: 2.5rem; }
  .project-card {
    background: #fff; border-radius: var(--radius);
    border: 1px solid rgba(107,79,187,0.1); box-shadow: var(--shadow);
    padding: 2rem; transition: transform 0.25s, box-shadow 0.25s;
    display: flex; flex-direction: column;
  }
  .project-card:hover { transform: translateY(-6px); box-shadow: var(--shadow-lg); }
  .project-card.featured-project { border-color: rgba(107,79,187,0.3); }
  .project-icon { font-size: 2rem; margin-bottom: 1rem; }
  .project-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.05rem; margin-bottom: 0.5rem; }
  .project-desc { font-size: 0.85rem; color: var(--ink2); line-height: 1.6; margin-bottom: 1.25rem; flex: 1; }
  .project-stats { display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 1.25rem; }
  .project-stat { background: var(--grad-subtle); color: var(--violet); border-radius: 8px; padding: 0.3rem 0.7rem; font-size: 0.75rem; font-weight: 700; }
  .project-tags { display: flex; gap: 0.4rem; flex-wrap: wrap; }
  .project-tag { background: var(--bg2); color: var(--ink3); border-radius: 100px; padding: 0.22rem 0.7rem; font-size: 0.72rem; }

  /* WHY DIFFERENT */
  #why { background: var(--ink); }
  #why .section-title { color: #fff; }
  #why .section-sub { color: rgba(255,255,255,0.5); }
  .why-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 2.5rem; }
  .why-card {
    background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08);
    border-radius: var(--radius); padding: 2.25rem 2rem;
    transition: background 0.25s;
  }
  .why-card:hover { background: rgba(255,255,255,0.07); }
  .why-num { font-family: 'Syne', sans-serif; font-size: 2.5rem; font-weight: 800; background: var(--grad); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 1rem; }
  .why-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.05rem; color: #fff; margin-bottom: 0.75rem; }
  .why-desc { font-size: 0.88rem; color: rgba(255,255,255,0.5); line-height: 1.65; }

  /* RESUME */
  #resume { background: var(--bg2); }
  .looking-grid { display: flex; flex-wrap: wrap; gap: 0.75rem; margin: 2rem 0; }
  .looking-item { background: #fff; border: 1.5px solid rgba(107,79,187,0.2); border-radius: 100px; padding: 0.5rem 1.25rem; font-size: 0.85rem; color: var(--ink); font-weight: 500; }
  .open-text { font-size: 1rem; color: var(--ink2); max-width: 480px; line-height: 1.7; margin-bottom: 2rem; font-style: italic; }

  /* SOCIAL BUTTONS */
  .social-row { display: flex; flex-wrap: wrap; gap: 0.85rem; margin-top: 2rem; }
  .social-btn {
    display: inline-flex; align-items: center; gap: 0.75rem;
    padding: 0.7rem 1.25rem; border-radius: 100px;
    text-decoration: none; font-family: 'Inter', sans-serif;
    font-size: 0.82rem; font-weight: 600;
    border: 1.5px solid transparent;
    transition: transform 0.2s, box-shadow 0.2s, background 0.2s, border-color 0.2s;
  }
  .social-btn:hover { transform: translateY(-3px); }
  .social-icon { width: 18px; height: 18px; flex-shrink: 0; }
  .social-label { display: flex; flex-direction: column; line-height: 1.2; }
  .social-name { font-size: 0.82rem; font-weight: 700; }
  .social-sub { font-size: 0.68rem; font-weight: 400; opacity: 0.75; }
  .pinterest-btn { background: #fff; color: #e60023; border-color: rgba(230,0,35,0.25); }
  .pinterest-btn:hover { background: #fff0f1; border-color: #e60023; box-shadow: 0 8px 28px rgba(230,0,35,0.18); }
  .instagram-btn { background: #fff; color: #c13584; border-color: rgba(193,53,132,0.25); }
  .instagram-btn:hover { background: #fff0fa; border-color: #c13584; box-shadow: 0 8px 28px rgba(193,53,132,0.18); }

  /* CONNECT SECTION */
  #connect { background: var(--bg); }
  .connect-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2.5rem; }
  .connect-card {
    border-radius: var(--radius); padding: 2.25rem 2rem;
    display: flex; flex-direction: column; gap: 1.25rem;
    text-decoration: none; transition: transform 0.25s, box-shadow 0.25s;
    border: 1.5px solid transparent;
  }
  .connect-card:hover { transform: translateY(-5px); }
  .connect-card.pinterest { background: linear-gradient(135deg, #fff5f5 0%, #ffe4e6 100%); border-color: rgba(230,0,35,0.15); }
  .connect-card.pinterest:hover { box-shadow: 0 16px 48px rgba(230,0,35,0.15); border-color: rgba(230,0,35,0.35); }
  .connect-card.instagram { background: linear-gradient(135deg, #fdf4ff 0%, #fce4f5 100%); border-color: rgba(193,53,132,0.15); }
  .connect-card.instagram:hover { box-shadow: 0 16px 48px rgba(193,53,132,0.15); border-color: rgba(193,53,132,0.35); }
  .connect-card-icon { width: 52px; height: 52px; border-radius: 14px; display: flex; align-items: center; justify-content: center; }
  .connect-card.pinterest .connect-card-icon { background: #e60023; }
  .connect-card.instagram .connect-card-icon { background: linear-gradient(135deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); }
  .connect-card-icon svg { width: 26px; height: 26px; fill: #fff; }
  .connect-card-title { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.15rem; color: var(--ink); }
  .connect-card-handle { font-size: 0.82rem; font-weight: 600; margin-top: -0.75rem; }
  .connect-card.pinterest .connect-card-handle { color: #e60023; }
  .connect-card.instagram .connect-card-handle { color: #c13584; }
  .connect-card-desc { font-size: 0.85rem; color: var(--ink2); line-height: 1.6; }
  .connect-card-cta { display: inline-flex; align-items: center; gap: 0.4rem; font-size: 0.82rem; font-weight: 700; margin-top: auto; padding-top: 0.5rem; }
  .connect-card.pinterest .connect-card-cta { color: #e60023; }
  .connect-card.instagram .connect-card-cta { color: #c13584; }

  /* FOOTER */
  footer { background: var(--ink); color: rgba(255,255,255,0.4); padding: 3rem 5%; text-align: center; font-size: 0.82rem; }
  footer a { color: var(--violet-light); text-decoration: none; }

  /* REVEAL ANIMATION */
  .reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .reveal.visible { opacity: 1; transform: none; }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    h1.hero-headline { font-size: 2.4rem; }
    .hero-proof { flex-direction: column; align-items: flex-start; gap: 1.5rem; }
    .proof-divider { width: 40px; height: 1px; }
    .metrics-grid { grid-template-columns: repeat(2, 1fr); }
    .case-header { grid-template-columns: 1fr; gap: 2rem; }
    .screenshots-grid { grid-template-columns: 1fr; }
    .workflow-steps { grid-template-columns: 1fr; gap: 2rem; }
    .workflow-steps::before { display: none; }
    .why-grid { grid-template-columns: 1fr; }
    .funnel-grid { flex-direction: column; }
    .funnel-arrow { transform: rotate(90deg); margin: 0 auto; }
    section { padding: 64px 5%; }
    .profile-stats { flex-direction: column; gap: 1.5rem; }
    .connect-grid { grid-template-columns: 1fr; }
    .social-row { flex-direction: column; }
    .social-btn { justify-content: flex-start; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Daily Dress Trends</div>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#growth">Growth Story</a></li>
    <li><a href="#case-study">Case Study</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#analytics">Skills</a></li>
    <li><a href="#resume">Resume</a></li>
  </ul>
  <a href="#connect" class="nav-cta">Let's Connect</a>
  <div class="hamburger"><span></span><span></span><span></span></div>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-bg-orb orb1"></div>
  <div class="hero-bg-orb orb2"></div>
  <div class="hero-inner">
    <div class="hero-badge">Real-world Pinterest Growth Case Study</div>
    <h1 class="hero-headline">I Turn Content Into <span>Measurable Growth.</span></h1>
    <div class="hero-tags">
      <span class="hero-tag">Data Analytics</span>
      <span class="hero-tag">Marketing Analytics</span>
      <span class="hero-tag">Affiliate Marketing</span>
      <span class="hero-tag">AI Content Creation</span>
    </div>
    <p class="hero-intro">I combine creative content creation with data-driven decision making — building, analyzing and optimizing digital content using audience insights, performance metrics and marketing strategies that produce real, measurable outcomes.</p>
    <div class="hero-btns">
      <a href="#growth" class="btn-primary">View My Growth Story</a>
      <a href="#projects" class="btn-outline">View Projects</a>
      <a href="#resume" class="btn-outline">Resume</a>
    </div>
    <div class="social-row">
      <a href="https://in.pinterest.com/daily_dress_trends/" target="_blank" rel="noopener noreferrer" class="social-btn pinterest-btn">
        <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.373 0 0 5.373 0 12c0 5.084 3.163 9.426 7.627 11.174-.105-.949-.2-2.405.042-3.441.218-.937 1.407-5.965 1.407-5.965s-.359-.719-.359-1.782c0-1.668.967-2.914 2.171-2.914 1.023 0 1.518.769 1.518 1.69 0 1.029-.655 2.568-.994 3.995-.283 1.194.599 2.169 1.777 2.169 2.133 0 3.772-2.249 3.772-5.495 0-2.873-2.064-4.882-5.012-4.882-3.414 0-5.418 2.561-5.418 5.207 0 1.031.397 2.138.893 2.738a.36.36 0 0 1 .083.345l-.333 1.36c-.053.22-.174.267-.402.161-1.499-.698-2.436-2.889-2.436-4.649 0-3.785 2.75-7.262 7.929-7.262 4.163 0 7.398 2.967 7.398 6.931 0 4.136-2.607 7.464-6.227 7.464-1.216 0-2.359-.632-2.75-1.378l-.748 2.853c-.271 1.043-1.002 2.35-1.492 3.146C9.57 23.812 10.763 24 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0z"/></svg>
        <span class="social-label">
          <span class="social-name">Pinterest</span>
          <span class="social-sub">Growth Case Study ↗</span>
        </span>
      </a>
      <a href="https://www.instagram.com/style.withteenu?stkn=MWI1bWFwMjRtMmVoOQ==" target="_blank" rel="noopener noreferrer" class="social-btn instagram-btn">
        <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
        <span class="social-label">
          <span class="social-name">@style.withteenu</span>
          <span class="social-sub">AI Fashion Content ↗</span>
        </span>
      </a>
    </div>
    <div class="hero-proof">
      <div>
        <div class="proof-num">208K+</div>
        <div class="proof-label">Monthly Pinterest<br>Views</div>
      </div>
      <div class="proof-divider"></div>
      <div>
        <div class="proof-num">+918%</div>
        <div class="proof-label">Saves Growth<br>Last 30 Days</div>
      </div>
      <div class="proof-divider"></div>
      <div>
        <div class="proof-num">+672%</div>
        <div class="proof-label">Outbound Clicks<br>Last 30 Days</div>
      </div>
    </div>
  </div>
</section>

<!-- GROWTH / METRICS -->
<section id="growth">
  <div class="container">
    <div class="section-label reveal">Real Growth. Real Metrics.</div>
    <h2 class="section-title reveal">Daily Dress Trends — Pinterest Performance</h2>
    <p class="section-sub reveal">I built and manage <strong style="color:#fff">Daily Dress Trends</strong>, a fashion-focused Pinterest channel where I experiment with content strategy, creative formats, audience behaviour and performance optimization to drive measurable traffic and affiliate conversions.</p>
    <div class="profile-stats reveal">
      <div><div class="profile-stat-val">35</div><div class="profile-stat-label">Followers</div></div>
      <div><div class="profile-stat-val">208.2K</div><div class="profile-stat-label">Monthly Views</div></div>
    </div>
    <div class="metrics-grid">
      <div class="metric-card reveal">
        <div class="metric-value count-up" data-target="233410" data-suffix="K" data-divide="1000">0</div>
        <div class="metric-growth">+409%</div>
        <div class="metric-label">Impressions — Last 30 Days</div>
      </div>
      <div class="metric-card reveal">
        <div class="metric-value count-up" data-target="11060" data-suffix="K" data-divide="1000">0</div>
        <div class="metric-growth">+472%</div>
        <div class="metric-label">Engagements</div>
      </div>
      <div class="metric-card featured reveal">
        <div class="metric-value count-up" data-target="689">0</div>
        <div class="metric-growth">+672%</div>
        <div class="metric-label">Outbound Clicks ↗ Affiliate Traffic</div>
      </div>
      <div class="metric-card featured reveal">
        <div class="metric-value count-up" data-target="799">0</div>
        <div class="metric-growth">+918%</div>
        <div class="metric-label">Saves — Highest Intent Signal</div>
      </div>
      <div class="metric-card reveal">
        <div class="metric-value count-up" data-target="155390" data-suffix="K" data-divide="1000">0</div>
        <div class="metric-growth">+377%</div>
        <div class="metric-label">Total Audience</div>
      </div>
      <div class="metric-card reveal">
        <div class="metric-value count-up" data-target="7970" data-suffix="K" data-divide="1000">0</div>
        <div class="metric-growth">+503%</div>
        <div class="metric-label">Engaged Audience</div>
      </div>
    </div>
    <div class="chart-wrap reveal">
      <div class="chart-title">GROWTH vs PREVIOUS 30-DAY PERIOD</div>
      <div class="bar-row"><div class="bar-label">Saves</div><div class="bar-track"><div class="bar-fill" data-width="100"></div></div><div class="bar-pct">+918%</div></div>
      <div class="bar-row"><div class="bar-label">Outbound Clicks</div><div class="bar-track"><div class="bar-fill" data-width="73"></div></div><div class="bar-pct">+672%</div></div>
      <div class="bar-row"><div class="bar-label">Engaged Audience</div><div class="bar-track"><div class="bar-fill" data-width="55"></div></div><div class="bar-pct">+503%</div></div>
      <div class="bar-row"><div class="bar-label">Engagements</div><div class="bar-track"><div class="bar-fill" data-width="51"></div></div><div class="bar-pct">+472%</div></div>
      <div class="bar-row"><div class="bar-label">Impressions</div><div class="bar-track"><div class="bar-fill" data-width="44"></div></div><div class="bar-pct">+409%</div></div>
      <div class="bar-row"><div class="bar-label">Total Audience</div><div class="bar-track"><div class="bar-fill" data-width="41"></div></div><div class="bar-pct">+377%</div></div>
      <p style="font-size:0.8rem;color:rgba(255,255,255,0.3);margin-top:1.5rem;font-style:italic;">"Growth driven by consistent content, creative optimization, audience insights and data-driven decisions."</p>
    </div>
  </div>
</section>

<!-- FUNNEL -->
<section id="funnel">
  <div class="container">
    <div class="section-label reveal">End-to-End Marketing</div>
    <h2 class="section-title reveal">From Attention → Action → Revenue</h2>
    <p class="section-sub reveal">My work goes beyond generating views. I track how content moves users from discovery and engagement toward outbound clicks, product traffic and affiliate outcomes — connecting content strategy with business results.</p>
    <div class="funnel-grid reveal">
      <div class="funnel-step"><div class="funnel-icon">📌</div><div class="funnel-step-title">Pinterest Content</div><div class="funnel-step-sub">Fashion creatives & pins</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">💬</div><div class="funnel-step-title">Engagement</div><div class="funnel-step-sub">Reactions & interactions</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">🔖</div><div class="funnel-step-title">Saves</div><div class="funnel-step-sub">High-intent signals</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">🔗</div><div class="funnel-step-title">Outbound Clicks</div><div class="funnel-step-sub">Link-through traffic</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">🛍️</div><div class="funnel-step-title">Meesho Traffic</div><div class="funnel-step-sub">Product page visits</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">📦</div><div class="funnel-step-title">Orders</div><div class="funnel-step-sub">Conversions</div></div>
      <div class="funnel-arrow">→</div>
      <div class="funnel-step"><div class="funnel-icon">💰</div><div class="funnel-step-title">Affiliate Revenue</div><div class="funnel-step-sub">Commission earned</div></div>
    </div>
    <p style="margin-top:2.5rem;font-size:0.9rem;color:var(--ink3);max-width:600px;line-height:1.7;" class="reveal">This end-to-end view demonstrates the connection between <strong>Content Strategy + Marketing Metrics + Data Analysis + Business Outcome</strong> — the kind of thinking MNCs and growth teams value.</p>
  </div>
</section>

<!-- CASE STUDY -->
<section id="case-study">
  <div class="container">
    <div class="section-label reveal">Pinterest Case Study</div>
    <h2 class="section-title reveal">Daily Dress Trends</h2>
    <p class="section-sub reveal">A real-world project at the intersection of content creation, affiliate marketing and performance analytics.</p>
    <div class="case-header">
      <div>
        <div class="case-role-tag">
          <span class="tag">Content Creator</span>
          <span class="tag">Affiliate Marketer</span>
          <span class="tag">Marketing Analytics</span>
        </div>
        <h3 style="font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:700;margin-bottom:1.25rem;color:var(--violet);">What I Did</h3>
        <div class="what-i-did">
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Created fashion-focused Pinterest content and product-focused creatives</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Tested different content formats to identify what resonates</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Used audience behaviour insights to improve content strategy</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Monitored impressions, engagements and audience growth</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Tracked outbound clicks as a proxy for affiliate intent</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Analyzed saves and engaged audience to measure content quality</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Used performance data to optimize future content decisions</div></div>
          <div class="did-item"><div class="did-dot"></div><div class="did-text">Connected Pinterest traffic with Meesho affiliate marketing</div></div>
        </div>
      </div>
      <div>
        <h3 style="font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:700;margin-bottom:1.25rem;color:var(--violet);">Skills Demonstrated</h3>
        <div style="display:flex;flex-wrap:wrap;gap:0.5rem;margin-bottom:2rem;">
          <span class="tag">Content Strategy</span><span class="tag">Affiliate Marketing</span><span class="tag">Audience Analysis</span><span class="tag">Marketing Analytics</span><span class="tag">Data-Driven Decisions</span><span class="tag">Creative Optimization</span><span class="tag">Performance Tracking</span>
        </div>
        <div style="background:var(--grad-subtle);border-radius:var(--radius);padding:1.5rem;">
          <div style="font-size:0.75rem;font-weight:600;color:var(--violet);margin-bottom:0.75rem;">KEY OUTCOME (Last 30 Days)</div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:1rem;">
            <div><div style="font-family:'Syne',sans-serif;font-size:1.5rem;font-weight:800;color:var(--ink);">233K+</div><div style="font-size:0.75rem;color:var(--ink3);">Impressions</div></div>
            <div><div style="font-family:'Syne',sans-serif;font-size:1.5rem;font-weight:800;color:var(--ink);">689+</div><div style="font-size:0.75rem;color:var(--ink3);">Outbound Clicks</div></div>
            <div><div style="font-family:'Syne',sans-serif;font-size:1.5rem;font-weight:800;color:var(--ink);">799+</div><div style="font-size:0.75rem;color:var(--ink3);">Saves</div></div>
            <div><div style="font-family:'Syne',sans-serif;font-size:1.5rem;font-weight:800;color:var(--ink);">11K+</div><div style="font-size:0.75rem;color:var(--ink3);">Engagements</div></div>
          </div>
        </div>
      </div>
    </div>
    <h3 style="font-family:'Syne',sans-serif;font-weight:700;font-size:1rem;margin-bottom:1.25rem;color:var(--ink3);" class="reveal">VERIFIED ANALYTICS — ACTUAL SCREENSHOTS</h3>
    <div class="screenshots-grid reveal">
      <div class="screenshot-card">
        <img src="pinterest-profile.png" alt="Daily Dress Trends Pinterest Profile — 35 followers, 208.2K monthly views">
        <div class="screenshot-label">Pinterest Profile — Daily Dress Trends · 208.2K monthly views</div>
      </div>
      <div class="screenshot-card">
        <img src="pinterest-analytics.png" alt="Pinterest Analytics — 233.41K impressions +409%, 689 outbound clicks +672%, 799 saves +918%">
        <div class="screenshot-label">Pinterest Analytics Overview — Last 30 Days (8/14/2026 – 9/13/2026)</div>
      </div>
    </div>
  </div>
</section>

<!-- WORKFLOW -->
<section id="workflow">
  <div class="container">
    <div class="section-label reveal">My Approach</div>
    <h2 class="section-title reveal">The Analytics Workflow</h2>
    <p class="section-sub reveal">Every content decision is grounded in data. Here's the cycle I follow to drive consistent improvement.</p>
    <div class="workflow-steps reveal">
      <div class="workflow-step"><div class="workflow-num">1</div><div class="workflow-step-title">Create</div><div class="workflow-step-desc">Develop fashion content and product creatives optimized for Pinterest formats</div></div>
      <div class="workflow-step"><div class="workflow-num">2</div><div class="workflow-step-title">Measure</div><div class="workflow-step-desc">Track impressions, engagements, saves, outbound clicks and audience metrics</div></div>
      <div class="workflow-step"><div class="workflow-num">3</div><div class="workflow-step-title">Analyze</div><div class="workflow-step-desc">Identify which content formats, topics and styles drive the most intent</div></div>
      <div class="workflow-step"><div class="workflow-num">4</div><div class="workflow-step-title">Optimize</div><div class="workflow-step-desc">Improve titles, descriptions, creative direction and content strategy</div></div>
      <div class="workflow-step"><div class="workflow-num">5</div><div class="workflow-step-title">Repeat</div><div class="workflow-step-desc">Use performance insights to guide the next content cycle</div></div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="analytics">
  <div class="container">
    <div class="section-label reveal">Capabilities</div>
    <h2 class="section-title reveal">Skills & Tools</h2>
    <p class="section-sub reveal">I am building practical analytics skills alongside real marketing experience. The combination of data tools and live marketing execution sets my profile apart.</p>
    <div class="skills-grid">
      <div class="skill-group reveal">
        <div class="skill-group-title">📊 Analytics</div>
        <div class="skill-pill-wrap">
          <span class="skill-pill">Python</span><span class="skill-pill">Excel</span><span class="skill-pill">Data Analysis</span><span class="skill-pill">Data Cleaning</span><span class="skill-pill">Data Visualization</span><span class="skill-pill">Marketing Analytics</span><span class="skill-pill">Audience Analysis</span>
        </div>
      </div>
      <div class="skill-group reveal">
        <div class="skill-group-title">📣 Marketing</div>
        <div class="skill-pill-wrap">
          <span class="skill-pill">Affiliate Marketing</span><span class="skill-pill">Content Strategy</span><span class="skill-pill">Digital Marketing</span><span class="skill-pill">Performance Tracking</span><span class="skill-pill">Data-Driven Decisions</span><span class="skill-pill">Audience Analysis</span>
        </div>
      </div>
      <div class="skill-group reveal">
        <div class="skill-group-title">🎨 Creative & AI</div>
        <div class="skill-pill-wrap">
          <span class="skill-pill">AI Content Creation</span><span class="skill-pill">Visual Content</span><span class="skill-pill">Creative Optimization</span><span class="skill-pill">Social Media Content</span>
        </div>
      </div>
      <div class="skill-group reveal">
        <div class="skill-group-title">🛠️ Tools</div>
        <div class="skill-pill-wrap">
          <span class="skill-pill">Pinterest</span><span class="skill-pill">Power BI</span><span class="skill-pill">Excel</span><span class="skill-pill">Python</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="section-label reveal">Portfolio</div>
    <h2 class="section-title reveal">Projects</h2>
    <p class="section-sub reveal">Work that spans data, marketing and creative content — built to solve real problems.</p>
    <div class="projects-grid">
      <div class="project-card featured-project reveal">
        <div class="project-icon">📌</div>
        <div class="project-title">Pinterest Growth & Affiliate Marketing</div>
        <div class="project-desc">Built and managed a fashion-focused Pinterest channel. Used content performance metrics to improve audience engagement, outbound traffic and affiliate marketing outcomes across a full content-to-conversion funnel.</div>
        <div class="project-stats"><span class="project-stat">233K+ Impressions</span><span class="project-stat">689+ Clicks</span><span class="project-stat">799+ Saves</span></div>
        <div class="project-tags"><span class="project-tag">Content Strategy</span><span class="project-tag">Affiliate Marketing</span><span class="project-tag">Marketing Analytics</span></div>
      </div>
      <div class="project-card reveal">
        <div class="project-icon">🐍</div>
        <div class="project-title">Student Marks Management System</div>
        <div class="project-desc">A Python-based academic management project for storing, processing and retrieving student marks data — demonstrating data handling, logic building and basic data processing skills.</div>
        <div class="project-tags"><span class="project-tag">Python</span><span class="project-tag">Data Management</span><span class="project-tag">Data Processing</span></div>
      </div>
      <div class="project-card reveal">
        <div class="project-icon">📊</div>
        <div class="project-title">Power BI Sales Dashboard</div>
        <div class="project-desc">Interactive dashboard project focused on transforming sales data into clear visual business insights — covering KPI tracking, trend analysis and dashboard design for business decision support.</div>
        <div class="project-tags"><span class="project-tag">Power BI</span><span class="project-tag">Data Visualization</span><span class="project-tag">KPI Tracking</span><span class="project-tag">Business Insights</span></div>
      </div>
      <div class="project-card reveal">
        <div class="project-icon">✨</div>
        <div class="project-title">AI Outfit Content Creation</div>
        <div class="project-desc">Experimented with AI-assisted fashion and outfit visuals to create social-media-ready content — exploring creative content production workflows and digital marketing applications of generative AI tools.</div>
        <div class="project-tags"><span class="project-tag">AI Content Creation</span><span class="project-tag">Fashion Content</span><span class="project-tag">Social Media</span><span class="project-tag">Creative Strategy</span></div>
      </div>
    </div>
  </div>
</section>

<!-- WHY DIFFERENT -->
<section id="why">
  <div class="container">
    <div class="section-label reveal" style="color:var(--rose);">What Sets This Apart</div>
    <h2 class="section-title reveal">Why This Portfolio Is Different</h2>
    <p class="section-sub reveal">Most student portfolios show coursework. This one shows a live audience, real platform analytics and a working affiliate funnel.</p>
    <div class="why-grid">
      <div class="why-card reveal">
        <div class="why-num">01</div>
        <div class="why-title">A Real Audience</div>
        <div class="why-desc">Daily Dress Trends has an actual audience on Pinterest — not a classroom exercise. The metrics shown here come from a live platform with real users discovering, saving and clicking through to products.</div>
      </div>
      <div class="why-card reveal">
        <div class="why-num">02</div>
        <div class="why-title">Data Meets Marketing</div>
        <div class="why-desc">I don't just create content — I measure it, analyze it and use the findings to make better decisions. This loop of creative execution and analytical thinking is what growth teams actually need.</div>
      </div>
      <div class="why-card reveal">
        <div class="why-num">03</div>
        <div class="why-title">Business-Aware Thinking</div>
        <div class="why-desc">I track the journey from content discovery to saves to outbound clicks to affiliate traffic — understanding that business value comes from conversions, not just views.</div>
      </div>
    </div>
  </div>
</section>

<!-- RESUME -->
<section id="resume">
  <div class="container">
    <div class="section-label reveal">Open to Opportunities</div>
    <h2 class="section-title reveal">What I'm Looking For</h2>
    <p class="open-text reveal">"Open to learning, experimenting and solving real business problems with data."</p>
    <p style="font-size:0.9rem;color:var(--ink2);margin-bottom:1rem;" class="reveal">I'm interested in internship opportunities in:</p>
    <div class="looking-grid reveal">
      <span class="looking-item">Marketing Analytics</span>
      <span class="looking-item">Growth Analytics</span>
      <span class="looking-item">Data Analytics</span>
      <span class="looking-item">Digital Marketing</span>
      <span class="looking-item">Business Analytics</span>
      <span class="looking-item">Data-Driven Marketing</span>
    </div>
    <div style="display:flex;gap:1rem;flex-wrap:wrap;margin-top:2rem;" class="reveal">
      <a href="mailto:your@email.com" class="btn-primary">Get in Touch</a>
      <span class="btn-outline" style="cursor:default;">Resume — Available on Request</span>
    </div>
    <p style="margin-top:1.5rem;font-size:0.8rem;color:var(--ink3);" class="reveal">B.Tech Computer Science & Business Systems · Data Analytics × Marketing Growth</p>
  </div>
</section>

<!-- CONNECT / SOCIAL -->
<section id="connect">
  <div class="container">
    <div class="section-label reveal">Find Me Online</div>
    <h2 class="section-title reveal">Connect & Follow</h2>
    <p class="section-sub reveal">See the real work in action — live content, real analytics and ongoing experiments across Pinterest and Instagram.</p>
    <div class="connect-grid">
      <a href="https://in.pinterest.com/daily_dress_trends/" target="_blank" rel="noopener noreferrer" class="connect-card pinterest reveal">
        <div class="connect-card-icon">
          <svg viewBox="0 0 24 24"><path d="M12 0C5.373 0 0 5.373 0 12c0 5.084 3.163 9.426 7.627 11.174-.105-.949-.2-2.405.042-3.441.218-.937 1.407-5.965 1.407-5.965s-.359-.719-.359-1.782c0-1.668.967-2.914 2.171-2.914 1.023 0 1.518.769 1.518 1.69 0 1.029-.655 2.568-.994 3.995-.283 1.194.599 2.169 1.777 2.169 2.133 0 3.772-2.249 3.772-5.495 0-2.873-2.064-4.882-5.012-4.882-3.414 0-5.418 2.561-5.418 5.207 0 1.031.397 2.138.893 2.738a.36.36 0 0 1 .083.345l-.333 1.36c-.053.22-.174.267-.402.161-1.499-.698-2.436-2.889-2.436-4.649 0-3.785 2.75-7.262 7.929-7.262 4.163 0 7.398 2.967 7.398 6.931 0 4.136-2.607 7.464-6.227 7.464-1.216 0-2.359-.632-2.75-1.378l-.748 2.853c-.271 1.043-1.002 2.35-1.492 3.146C9.57 23.812 10.763 24 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0z"/></svg>
        </div>
        <div class="connect-card-title">Daily Dress Trends</div>
        <div class="connect-card-handle">pinterest.com/daily_dress_trends</div>
        <div class="connect-card-desc">My primary growth case study — fashion content, affiliate marketing and live Pinterest analytics. 208K+ monthly views, +918% saves, +672% outbound clicks in the last 30 days.</div>
        <div class="connect-card-cta">View Pinterest Profile <svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M3 8h10M9 4l4 4-4 4"/></svg></div>
      </a>
      <a href="https://www.instagram.com/style.withteenu?stkn=MWI1bWFwMjRtMmVoOQ==" target="_blank" rel="noopener noreferrer" class="connect-card instagram reveal">
        <div class="connect-card-icon">
          <svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
        </div>
        <div class="connect-card-title">style.withteenu</div>
        <div class="connect-card-handle">@style.withteenu</div>
        <div class="connect-card-desc">My AI-assisted fashion and outfit content profile — experimenting with generative AI for creative content production, social media strategy and digital fashion storytelling.</div>
        <div class="connect-card-cta">View Instagram Profile <svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M3 8h10M9 4l4 4-4 4"/></svg></div>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p style="font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:700;color:#fff;margin-bottom:0.5rem;">Daily Dress Trends</p>
  <p>Data Analytics × Marketing Growth × Affiliate Marketing</p>
  <div style="display:flex;justify-content:center;gap:1.25rem;margin-top:1.5rem;flex-wrap:wrap;">
    <a href="https://in.pinterest.com/daily_dress_trends/" target="_blank" rel="noopener noreferrer" style="display:inline-flex;align-items:center;gap:0.5rem;color:#fff;text-decoration:none;font-size:0.82rem;font-weight:600;background:rgba(230,0,35,0.2);border:1px solid rgba(230,0,35,0.35);border-radius:100px;padding:0.4rem 1rem;transition:background 0.2s;" onmouseover="this.style.background='rgba(230,0,35,0.35)'" onmouseout="this.style.background='rgba(230,0,35,0.2)'">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="#e60023"><path d="M12 0C5.373 0 0 5.373 0 12c0 5.084 3.163 9.426 7.627 11.174-.105-.949-.2-2.405.042-3.441.218-.937 1.407-5.965 1.407-5.965s-.359-.719-.359-1.782c0-1.668.967-2.914 2.171-2.914 1.023 0 1.518.769 1.518 1.69 0 1.029-.655 2.568-.994 3.995-.283 1.194.599 2.169 1.777 2.169 2.133 0 3.772-2.249 3.772-5.495 0-2.873-2.064-4.882-5.012-4.882-3.414 0-5.418 2.561-5.418 5.207 0 1.031.397 2.138.893 2.738a.36.36 0 0 1 .083.345l-.333 1.36c-.053.22-.174.267-.402.161-1.499-.698-2.436-2.889-2.436-4.649 0-3.785 2.75-7.262 7.929-7.262 4.163 0 7.398 2.967 7.398 6.931 0 4.136-2.607 7.464-6.227 7.464-1.216 0-2.359-.632-2.75-1.378l-.748 2.853c-.271 1.043-1.002 2.35-1.492 3.146C9.57 23.812 10.763 24 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0z"/></svg>
      Pinterest
    </a>
    <a href="https://www.instagram.com/style.withteenu?stkn=MWI1bWFwMjRtMmVoOQ==" target="_blank" rel="noopener noreferrer" style="display:inline-flex;align-items:center;gap:0.5rem;color:#fff;text-decoration:none;font-size:0.82rem;font-weight:600;background:rgba(193,53,132,0.2);border:1px solid rgba(193,53,132,0.35);border-radius:100px;padding:0.4rem 1rem;transition:background 0.2s;" onmouseover="this.style.background='rgba(193,53,132,0.35)'" onmouseout="this.style.background='rgba(193,53,132,0.2)'">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="#c13584"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
      @style.withteenu
    </a>
  </div>
  <p style="margin-top:1.5rem;opacity:0.4;">Built with real metrics from Daily Dress Trends on Pinterest. No exaggerated claims.</p>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const revealObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        revealObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => revealObserver.observe(el));

  // Count-up animation
  function countUp(el) {
    const target = parseInt(el.dataset.target);
    const divide = parseInt(el.dataset.divide) || 1;
    const suffix = el.dataset.suffix || '';
    const step = target / (1600 / 16);
    let current = 0;
    const timer = setInterval(() => {
      current += step;
      if (current >= target) { current = target; clearInterval(timer); }
      const display = divide > 1 ? (current / divide).toFixed(1) : Math.floor(current).toLocaleString();
      el.textContent = display + suffix;
    }, 16);
  }
  const countEls = document.querySelectorAll('.count-up');
  const countObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) { countUp(entry.target); countObserver.unobserve(entry.target); }
    });
  }, { threshold: 0.3 });
  countEls.forEach(el => countObserver.observe(el));

  // Bar chart animation
  const bars = document.querySelectorAll('.bar-fill');
  const barObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.width = entry.target.dataset.width + '%';
        barObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.3 });
  bars.forEach(bar => barObserver.observe(bar));
</script>
</body>
</html>
