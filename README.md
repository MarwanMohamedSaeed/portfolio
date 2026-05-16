<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Marwan Mohamed — Aspiring Data Scientist & Data Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --bg2: #080d1a;
    --bg3: #0c1220;
    --surface: #0f1628;
    --surface2: #141d35;
    --border: rgba(100,160,255,0.12);
    --border2: rgba(100,160,255,0.22);
    --accent: #4f8eff;
    --accent2: #00e5ff;
    --accent3: #a855f7;
    --text: #e8f0ff;
    --text2: #8a9dc0;
    --text3: #4a5878;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
    --glow: 0 0 40px rgba(79,142,255,0.15);
    --glow2: 0 0 20px rgba(0,229,255,0.1);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    overflow-x: hidden;
    cursor: default;
  }

  /* SCROLLBAR */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 2px; }

  /* GRID BACKGROUND */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(79,142,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,142,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000;
    background: rgba(5,8,16,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
    padding: 0 5%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 64px;
  }

  .nav-logo {
    font-family: var(--mono);
    font-size: 14px;
    color: var(--accent);
    letter-spacing: 0.05em;
  }

  .nav-logo span { color: var(--accent2); }

  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
  }

  .nav-links a {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text2);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
    position: relative;
  }

  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 1px;
    background: var(--accent);
    transition: width 0.3s;
  }

  .nav-links a:hover { color: var(--accent); }
  .nav-links a:hover::after { width: 100%; }

  /* SECTIONS */
  section { position: relative; z-index: 1; }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 120px 8% 80px;
    position: relative;
    overflow: hidden;
  }

  .hero-inner {
    display: flex;
    align-items: center;
    gap: 60px;
  }

  .hero-content {
    flex: 1;
    min-width: 0;
  }

  .hero-photo {
    flex-shrink: 0;
    width: 280px;
    height: 280px;
    position: relative;
  }

  .hero-photo img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    border: 2px solid var(--border2);
    box-shadow: 0 0 40px rgba(79,142,255,0.2), 0 0 80px rgba(79,142,255,0.08);
    transition: all 0.4s;
    display: block;
  }

  .hero-photo img:hover {
    transform: scale(1.03);
    border-color: var(--accent);
    box-shadow: 0 0 60px rgba(79,142,255,0.3), 0 0 120px rgba(79,142,255,0.12);
  }

  .hero-photo::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    z-index: -1;
    opacity: 0.5;
    animation: heroGlow 4s ease-in-out infinite alternate;
  }

  @keyframes heroGlow {
    0% { opacity: 0.3; transform: rotate(0deg); }
    100% { opacity: 0.7; transform: rotate(360deg); }
  }

  @media (max-width: 900px) {
    .hero-inner {
      flex-direction: column-reverse;
      gap: 32px;
    }
    .hero-photo {
      width: 180px;
      height: 180px;
    }
  }

  .hero-orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
  }

  .orb1 {
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(79,142,255,0.12) 0%, transparent 70%);
    top: -100px; right: -100px;
  }

  .orb2 {
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(168,85,247,0.08) 0%, transparent 70%);
    bottom: 0; left: 10%;
  }

  .hero-tag {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .hero-tag::before {
    content: '';
    width: 32px; height: 1px;
    background: var(--accent);
  }

  h1.hero-name {
    font-size: clamp(48px, 8vw, 96px);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
  }

  h1.hero-name .first { color: var(--text); }
  h1.hero-name .last {
    color: transparent;
    -webkit-text-stroke: 1px rgba(79,142,255,0.6);
  }

  .hero-title {
    font-family: var(--mono);
    font-size: clamp(14px, 2vw, 18px);
    color: var(--accent2);
    margin: 24px 0 32px;
    letter-spacing: 0.05em;
  }

  .hero-desc {
    font-size: 17px;
    color: var(--text2);
    max-width: 560px;
    line-height: 1.7;
    margin-bottom: 48px;
  }

  .hero-ctas {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    margin-bottom: 80px;
  }

  .btn-primary {
    padding: 14px 32px;
    background: var(--accent);
    color: #fff;
    font-family: var(--mono);
    font-size: 13px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    border: none;
    cursor: pointer;
    transition: all 0.3s;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
    display: inline-block;
  }

  .btn-primary:hover {
    background: var(--accent2);
    color: var(--bg);
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(0,229,255,0.3);
  }

  .btn-outline {
    padding: 13px 32px;
    background: transparent;
    color: var(--accent);
    font-family: var(--mono);
    font-size: 13px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
    border: 1px solid var(--accent);
    cursor: pointer;
    transition: all 0.3s;
    display: inline-block;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }

  .btn-outline:hover {
    background: rgba(79,142,255,0.1);
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(79,142,255,0.2);
  }

  .hero-stats {
    display: flex;
    gap: 48px;
    flex-wrap: wrap;
  }

  .stat-item { text-align: left; }

  .stat-num {
    font-size: 36px;
    font-weight: 800;
    color: var(--accent);
    font-family: var(--mono);
  }

  .stat-label {
    font-size: 12px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    font-family: var(--mono);
    margin-top: 4px;
  }

  /* SECTION HEADERS */
  .section-header {
    margin-bottom: 60px;
    position: relative;
  }

  .section-tag {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-tag::before {
    content: '';
    width: 24px; height: 1px;
    background: var(--accent);
  }

  .section-title {
    font-size: clamp(32px, 4vw, 52px);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1;
  }

  .section-title .accent { color: var(--accent); }

  /* ABOUT */
  #about {
    padding: 120px 8%;
    background: var(--bg2);
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }

  .about-text p {
    font-size: 16px;
    color: var(--text2);
    line-height: 1.8;
    margin-bottom: 20px;
  }

  .about-text p strong { color: var(--accent2); font-weight: 600; }

  .info-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 32px;
  }

  .info-item {
    padding: 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: 2px solid var(--accent);
  }

  .info-label {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 6px;
  }

  .info-value {
    font-size: 14px;
    color: var(--text);
    font-weight: 600;
  }

  /* SKILLS */
  .skills-panel {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .skill-category {
    padding: 24px;
    background: var(--surface);
    border: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }

  .skill-category::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: linear-gradient(180deg, var(--accent), var(--accent3));
  }

  .skill-cat-title {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-bottom: 16px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .skill-tag {
    padding: 6px 14px;
    background: rgba(79,142,255,0.08);
    border: 1px solid rgba(79,142,255,0.2);
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent2);
    transition: all 0.2s;
    cursor: default;
  }

  .skill-tag:hover {
    background: rgba(79,142,255,0.15);
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  /* PROJECTS */
  #projects {
    padding: 120px 8%;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
    gap: 24px;
    margin-bottom: 48px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 32px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
    cursor: pointer;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent3));
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .project-card:hover { border-color: var(--border2); transform: translateY(-4px); box-shadow: var(--glow); }
  .project-card:hover::before { transform: scaleX(1); }

  .project-type {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 0.2em;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .project-type-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .project-title {
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 12px;
    color: var(--text);
    letter-spacing: -0.01em;
  }

  .project-desc {
    font-size: 14px;
    color: var(--text2);
    line-height: 1.7;
    margin-bottom: 24px;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 24px;
  }

  .tech-badge {
    padding: 4px 10px;
    background: rgba(168,85,247,0.08);
    border: 1px solid rgba(168,85,247,0.2);
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent3);
  }

  .project-links {
    display: flex;
    gap: 16px;
  }

  .project-link {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text2);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 6px;
    transition: color 0.2s;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;
  }

  .project-link:hover { color: var(--accent); }

  /* ADD PROJECT */
  .add-project-card {
    background: transparent;
    border: 1px dashed var(--border2);
    padding: 32px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s;
    min-height: 260px;
    text-align: center;
    gap: 16px;
  }

  .add-project-card:hover {
    border-color: var(--accent);
    background: rgba(79,142,255,0.03);
  }

  .add-icon {
    width: 48px; height: 48px;
    border: 1px solid var(--border2);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    color: var(--text3);
    transition: all 0.3s;
  }

  .add-project-card:hover .add-icon {
    border-color: var(--accent);
    color: var(--accent);
  }

  .add-project-card p {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  /* EXPERIENCE */
  #experience {
    padding: 120px 8%;
    background: var(--bg2);
  }

  .timeline {
    position: relative;
    padding-left: 32px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(180deg, var(--accent), transparent);
  }

  .timeline-item {
    position: relative;
    padding: 0 0 48px 32px;
  }

  .timeline-dot {
    position: absolute;
    left: -20px; top: 6px;
    width: 8px; height: 8px;
    border: 2px solid var(--accent);
    border-radius: 50%;
    background: var(--bg);
  }

  .timeline-dot::after {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 4px; height: 4px;
    border-radius: 50%;
    background: var(--accent);
  }

  .timeline-date {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .timeline-role {
    font-size: 20px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 4px;
  }

  .timeline-company {
    font-size: 14px;
    color: var(--accent2);
    margin-bottom: 16px;
    font-family: var(--mono);
  }

  .timeline-desc {
    font-size: 15px;
    color: var(--text2);
    line-height: 1.7;
    max-width: 680px;
  }

  .timeline-desc ul { padding-left: 20px; }
  .timeline-desc li { margin-bottom: 6px; }

  /* CERTIFICATES */
  #certificates {
    padding: 120px 8%;
  }

  .certs-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 24px;
  }

  .cert-card {
    display: flex;
    gap: 0;
    background: var(--surface);
    border: 1px solid var(--border);
    overflow: hidden;
    transition: all 0.3s;
    cursor: pointer;
    min-height: 180px;
  }

  .cert-card:hover {
    border-color: var(--border2);
    transform: translateY(-3px);
    box-shadow: var(--glow);
  }

  .cert-preview {
    width: 220px;
    min-height: 180px;
    flex-shrink: 0;
    background: var(--bg2);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    border-right: 1px solid var(--border);
    position: relative;
  }

  .cert-preview embed,
  .cert-preview object,
  .cert-preview img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .cert-preview-icon {
    font-size: 36px;
    color: var(--text3);
    opacity: 0.4;
  }

  .cert-info {
    padding: 24px 28px;
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 6px;
  }

  .cert-issuer {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .cert-name {
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
    line-height: 1.3;
  }

  .cert-date {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
  }

  .cert-open {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent2);
    text-decoration: none;
    margin-top: 6px;
    transition: color 0.2s;
  }

  .cert-open:hover {
    color: var(--accent);
  }

  .cert-upload {
    padding: 28px;
    background: transparent;
    border: 1px dashed var(--border2);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s;
    min-height: 120px;
    text-align: center;
    gap: 12px;
  }

  .cert-upload:hover {
    border-color: var(--accent);
    background: rgba(79,142,255,0.03);
  }

  .cert-upload p {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  @media (max-width: 700px) {
    .cert-card {
      flex-direction: column;
    }
    .cert-preview {
      width: 100%;
      min-height: 140px;
      border-right: none;
      border-bottom: 1px solid var(--border);
    }
  }

  /* CV */
  #cv {
    padding: 120px 8%;
    background: var(--bg2);
  }

  .cv-panel {
    max-width: 780px;
    margin: 0 auto;
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 48px;
    position: relative;
    overflow: hidden;
  }

  .cv-panel::before {
    content: 'CV';
    position: absolute;
    right: -20px; top: 20px;
    font-size: 180px;
    font-weight: 800;
    color: rgba(79,142,255,0.03);
    letter-spacing: -0.05em;
    line-height: 1;
    pointer-events: none;
  }

  .cv-header {
    display: flex;
    justify-content: space-between;
    align-items: start;
    margin-bottom: 24px;
  }

  .cv-title {
    font-size: 28px;
    font-weight: 800;
    color: var(--text);
    margin-bottom: 4px;
  }

  .cv-subtitle {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent2);
  }

  .cv-embed {
    width: 100%;
    height: 520px;
    margin-bottom: 24px;
    border: 1px solid var(--border);
    background: var(--bg2);
    overflow: hidden;
  }

  .cv-embed embed {
    width: 100%;
    height: 100%;
    display: block;
  }

  .cv-upload-zone {
    border: 2px dashed var(--border2);
    padding: 32px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s;
    background: rgba(79,142,255,0.02);
  }

  .cv-upload-zone:hover {
    border-color: var(--accent);
    background: rgba(79,142,255,0.05);
  }

  .cv-upload-icon {
    font-size: 48px;
    margin-bottom: 16px;
  }

  .cv-upload-text {
    font-size: 18px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 8px;
  }

  .cv-upload-sub {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text3);
    margin-bottom: 24px;
  }

  .cv-file-preview {
    display: none;
    align-items: center;
    justify-content: space-between;
    padding: 16px 20px;
    background: rgba(79,142,255,0.08);
    border: 1px solid rgba(79,142,255,0.2);
    margin-top: 16px;
  }

  .cv-file-name {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
  }

  /* WORK / GALLERY */
  #work {
    padding: 120px 8%;
  }

  .work-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
    gap: 24px;
  }

  .work-card {
    background: var(--surface);
    border: 1px solid var(--border);
    overflow: hidden;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
  }

  .work-card:hover {
    border-color: var(--border2);
    transform: translateY(-4px);
    box-shadow: var(--glow);
  }

  .work-card-img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    display: block;
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
  }

  .work-card-img-placeholder {
    width: 100%;
    height: 200px;
    background: var(--bg2);
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 1px solid var(--border);
    font-size: 32px;
    color: var(--text3);
  }

  .work-card-body {
    padding: 20px 24px 24px;
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .work-card-title {
    font-size: 18px;
    font-weight: 700;
    color: var(--text);
    line-height: 1.3;
  }

  .work-card-desc {
    font-size: 13px;
    color: var(--text2);
    line-height: 1.6;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .work-card-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 4px;
  }

  .work-card-skill {
    padding: 3px 10px;
    background: rgba(168,85,247,0.08);
    border: 1px solid rgba(168,85,247,0.2);
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent3);
  }

  .work-card-meta {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-top: auto;
    padding-top: 12px;
    border-top: 1px solid var(--border);
  }

  .work-card-meta-item {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .work-card-meta-item a {
    color: var(--accent2);
    text-decoration: none;
  }

  .work-card-meta-item a:hover {
    text-decoration: underline;
  }

  .work-add-btn {
    padding: 48px 24px;
    background: transparent;
    border: 1px dashed var(--border2);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    cursor: pointer;
    transition: all 0.3s;
    min-height: 200px;
    text-align: center;
  }

  .work-add-btn:hover {
    border-color: var(--accent);
    background: rgba(79,142,255,0.03);
  }

  .work-add-btn p {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  /* SOCIAL */
  #social {
    padding: 120px 8%;
    background: var(--bg2);
  }

  .social-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 16px;
  }

  .social-card {
    padding: 28px 24px;
    background: var(--surface);
    border: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    gap: 16px;
    transition: all 0.3s;
    cursor: pointer;
    text-decoration: none;
  }

  .social-card:hover {
    border-color: var(--border2);
    transform: translateY(-4px);
    box-shadow: var(--glow);
  }

  .social-icon {
    width: 44px; height: 44px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    font-weight: bold;
  }

  .social-name {
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
  }

  .social-handle {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text3);
    margin-top: -8px;
  }

  .social-arrow {
    margin-top: auto;
    font-size: 18px;
    color: var(--text3);
    transition: transform 0.2s;
  }

  .social-card:hover .social-arrow { transform: translate(4px, -4px); color: var(--accent); }

  /* CONTACT */
  #contact {
    padding: 120px 8%;
    position: relative;
    overflow: hidden;
  }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }

  .contact-info h2 {
    font-size: clamp(36px, 5vw, 64px);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
    margin-bottom: 24px;
  }

  .contact-info h2 span { color: var(--accent); }

  .contact-info p {
    font-size: 16px;
    color: var(--text2);
    line-height: 1.7;
    margin-bottom: 32px;
  }

  .contact-details {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .contact-detail {
    display: flex;
    align-items: center;
    gap: 16px;
    font-family: var(--mono);
    font-size: 14px;
    color: var(--text2);
  }

  .contact-detail-icon {
    width: 40px; height: 40px;
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
    color: var(--accent);
  }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .form-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .form-input, .form-textarea {
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--text);
    font-family: var(--sans);
    font-size: 15px;
    padding: 14px 18px;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }

  .form-input:focus, .form-textarea:focus {
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(79,142,255,0.08);
  }

  .form-textarea { min-height: 140px; resize: vertical; }

  .form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  /* FOOTER */
  footer {
    padding: 40px 8%;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 1;
  }

  footer p {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text3);
  }

  footer span { color: var(--accent); }

  /* MODALS */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(5,8,16,0.9);
    backdrop-filter: blur(8px);
    z-index: 2000;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 24px;
  }

  .modal-overlay.active { display: flex; }

  .modal {
    background: var(--surface);
    border: 1px solid var(--border2);
    padding: 40px;
    width: 100%;
    max-width: 580px;
    position: relative;
    max-height: 90vh;
    overflow-y: auto;
  }

  .modal h3 {
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 8px;
    color: var(--text);
  }

  .modal p {
    font-size: 14px;
    color: var(--text2);
    margin-bottom: 28px;
    line-height: 1.6;
  }

  .modal-close {
    position: absolute;
    top: 20px; right: 20px;
    background: none; border: none;
    color: var(--text2);
    font-size: 20px;
    cursor: pointer;
    width: 32px; height: 32px;
    display: flex; align-items: center; justify-content: center;
    transition: color 0.2s;
  }

  .modal-close:hover { color: var(--accent); }

  .modal-form { display: flex; flex-direction: column; gap: 16px; }

  /* HAMBURGER */
  .hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    background: none;
    border: none;
    padding: 4px;
  }

  .hamburger span {
    display: block;
    width: 24px; height: 1.5px;
    background: var(--text2);
    transition: all 0.3s;
  }

  /* BACK TO TOP */
  .back-top {
    position: fixed;
    bottom: 32px; right: 32px;
    width: 44px; height: 44px;
    background: var(--surface);
    border: 1px solid var(--border2);
    color: var(--accent);
    font-size: 18px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s;
    z-index: 500;
    text-decoration: none;
    clip-path: polygon(0 0, calc(100% - 8px) 0, 100% 8px, 100% 100%, 8px 100%, 0 calc(100% - 8px));
  }

  .back-top:hover {
    background: var(--accent);
    color: #fff;
    box-shadow: 0 8px 24px rgba(79,142,255,0.3);
  }

  /* FILE INPUT */
  input[type="file"] { display: none; }

  /* NOTIFICATION */
  .notif {
    position: fixed;
    bottom: 32px; left: 50%;
    transform: translateX(-50%) translateY(100px);
    background: var(--surface);
    border: 1px solid var(--accent);
    color: var(--accent);
    font-family: var(--mono);
    font-size: 13px;
    padding: 14px 28px;
    z-index: 9999;
    transition: transform 0.4s;
    white-space: nowrap;
  }

  .notif.show { transform: translateX(-50%) translateY(0); }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .about-grid, .contact-grid { grid-template-columns: 1fr; gap: 48px; }
    .work-grid { grid-template-columns: repeat(2, 1fr); }
    .form-row { grid-template-columns: 1fr; }
    .nav-links { display: none; }
    .hamburger { display: flex; }
  }

  @media (max-width: 600px) {
    .work-grid { grid-template-columns: 1fr; }
    .hero-stats { gap: 28px; }
    .info-grid { grid-template-columns: 1fr; }
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-in { opacity: 0; }
  .fade-in.visible { animation: fadeUp 0.6s ease forwards; }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .cursor {
    display: inline-block;
    width: 3px;
    height: 0.85em;
    background: var(--accent);
    margin-left: 4px;
    vertical-align: middle;
    animation: blink 1s infinite;
  }

  /* STATUS BADGE */
  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    background: rgba(0,229,255,0.05);
    border: 1px solid rgba(0,229,255,0.2);
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent2);
    margin-bottom: 32px;
  }

  .status-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #00ff88;
    animation: pulse 2s infinite;
  }

  /* SECTION DIVIDER */
  .divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border2), transparent);
    margin: 0 8%;
    width: calc(100% - 16%);
  }

  /* SCROLL PROGRESS */
  .scroll-progress {
    position: fixed;
    top: 0; left: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    z-index: 9999;
    width: 0%;
    transition: width 0.1s;
  }

  /* DELETE BUTTON */
  .delete-btn {
    position: absolute;
    top: 12px; right: 12px;
    width: 28px; height: 28px;
    background: rgba(255,60,60,0.15);
    border: 1px solid rgba(255,60,60,0.3);
    color: #ff6b6b;
    font-size: 14px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: all 0.2s;
    z-index: 10;
    border-radius: 4px;
    line-height: 1;
  }

  .project-card:hover .delete-btn,
  .timeline-item:hover .delete-btn,
  .cert-card:hover .delete-btn,
  .work-card:hover .delete-btn,
  .service-card:hover .delete-btn,
  .service-card:hover .edit-btn,
  .social-card:hover .delete-btn,
  .social-card:hover .edit-btn {
    opacity: 1;
  }

  .delete-btn:hover {
    background: rgba(255,60,60,0.3);
    border-color: #ff6b6b;
    transform: scale(1.1);
  }

  .edit-btn {
    position: absolute;
    top: 12px; right: 46px;
    width: 28px; height: 28px;
    background: rgba(79,142,255,0.15);
    border: 1px solid rgba(79,142,255,0.3);
    color: var(--accent);
    font-size: 13px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: all 0.2s;
    z-index: 10;
    border-radius: 4px;
    line-height: 1;
  }

  .edit-btn:hover {
    background: rgba(79,142,255,0.3);
    border-color: var(--accent);
    transform: scale(1.1);
  }

  /* LIGHTBOX */
  .lightbox {
    position: fixed;
    inset: 0;
    background: rgba(5,8,16,0.95);
    backdrop-filter: blur(12px);
    z-index: 3000;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 40px;
    cursor: zoom-out;
  }

  .lightbox.active { display: flex; }

  .lightbox img {
    max-width: 90vw;
    max-height: 90vh;
    object-fit: contain;
    border: 1px solid var(--border2);
    box-shadow: 0 20px 80px rgba(0,0,0,0.6);
  }

  /* FILTER BAR */
  .filter-bar {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 40px;
  }

  .filter-btn {
    padding: 8px 18px;
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text3);
    font-family: var(--mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    cursor: pointer;
    transition: all 0.2s;
  }

  .filter-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  .filter-btn.active {
    background: rgba(79,142,255,0.1);
    border-color: var(--accent);
    color: var(--accent);
  }

  /* NAV ACTIVE */
  .nav-links a.active {
    color: var(--accent);
  }

  .nav-links a.active::after {
    width: 100%;
  }

  /* SKILLS EDITOR */
  .skills-editor-trigger {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    cursor: pointer;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    margin-top: 16px;
    transition: color 0.2s;
  }

  .skills-editor-trigger:hover {
    color: var(--accent2);
  }

  .skill-editor-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 8px;
  }

  .skill-editor-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 12px;
    background: rgba(79,142,255,0.08);
    border: 1px solid rgba(79,142,255,0.2);
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent2);
    transition: all 0.2s;
  }

  .skill-editor-tag-remove {
    cursor: pointer;
    color: #ff6b6b;
    font-size: 14px;
    line-height: 1;
    transition: transform 0.2s;
  }

  .skill-editor-tag-remove:hover {
    transform: scale(1.3);
  }

  /* PROJECT CARD FILTER HIDE */
  .project-card.hidden {
    display: none;
  }

  /* SERVICES */
  #services {
    padding: 120px 8%;
    background: var(--bg2);
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
    gap: 24px;
  }

  .service-card {
    background: var(--surface);
    border: 1px solid var(--border);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    transition: all 0.3s;
    position: relative;
  }

  .service-card:hover {
    border-color: var(--border2);
    transform: translateY(-4px);
    box-shadow: var(--glow);
  }

  .service-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .service-card:hover::before {
    transform: scaleX(1);
  }

  .service-img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    display: block;
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
  }

  .service-img-placeholder {
    width: 100%;
    height: 180px;
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 48px;
  }

  .service-body {
    padding: 24px;
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .service-title {
    font-size: 20px;
    font-weight: 700;
    color: var(--text);
  }

  .service-desc {
    font-size: 14px;
    color: var(--text2);
    line-height: 1.6;
  }

  .service-offer {
    display: flex;
    flex-direction: column;
    gap: 6px;
    padding: 12px 16px;
    background: rgba(79,142,255,0.04);
    border: 1px solid var(--border);
    margin: 4px 0;
  }

  .service-offer-item {
    font-size: 13px;
    color: var(--text2);
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .service-offer-item::before {
    content: '›';
    color: var(--accent2);
    font-weight: 700;
  }

  .service-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 8px;
    padding-top: 12px;
    border-top: 1px solid var(--border);
    margin-top: auto;
  }

  .service-price {
    font-size: 24px;
    font-weight: 800;
    color: var(--accent);
    font-family: var(--mono);
  }

  .service-price small {
    font-size: 13px;
    font-weight: 400;
    color: var(--text3);
  }

  .service-duration {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .service-addons {
    display: flex;
    flex-direction: column;
    gap: 4px;
    padding: 0;
    margin-top: -4px;
  }

  .service-addon-item {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .service-addon-price {
    color: var(--accent3);
    font-weight: 600;
  }

  .service-order-btn {
    padding: 12px 24px;
    background: var(--accent);
    color: #fff;
    font-family: var(--mono);
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    border: none;
    cursor: pointer;
    transition: all 0.3s;
    width: 100%;
    margin-top: 4px;
  }

  .service-order-btn:hover {
    background: var(--accent2);
    color: var(--bg);
  }

  .add-service-btn {
    padding: 48px 24px;
    background: transparent;
    border: 1px dashed var(--border2);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    cursor: pointer;
    transition: all 0.3s;
    min-height: 200px;
    text-align: center;
  }

  .add-service-btn:hover {
    border-color: var(--accent);
    background: rgba(79,142,255,0.03);
  }

  .add-service-btn p {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  /* ORDER SUMMARY */
  .order-summary {
    background: rgba(79,142,255,0.04);
    border: 1px solid var(--border);
    padding: 20px;
    margin-bottom: 20px;
  }

  .order-summary h4 {
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 12px;
  }

  .order-summary-row {
    display: flex;
    justify-content: space-between;
    font-size: 13px;
    color: var(--text2);
    padding: 4px 0;
  }

  .order-summary-row.total {
    border-top: 1px solid var(--border);
    margin-top: 8px;
    padding-top: 8px;
    font-weight: 700;
    color: var(--accent);
    font-size: 16px;
  }
</style>
</head>
<body>

<!-- SCROLL PROGRESS -->
<div class="scroll-progress" id="scrollProgress"></div>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeLightbox()">
  <img id="lightboxImg" src="" alt="Full size view">
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">MW<span>.</span>dev</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certificates">Certs</a></li>
    <li><a href="#cv">CV</a></li>
    <li><a href="#work">Work</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#social">Social</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMobile()" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-orb orb1"></div>
  <div class="hero-orb orb2"></div>

  <div class="hero-inner">
    <div class="hero-content">
      <div class="status-badge">
        <span class="status-dot"></span>
        Available for opportunities
      </div>

      <div class="hero-tag">Aspiring Data Scientist & Data Analyst</div>

      <h1 class="hero-name">
        <div class="first">Marwan</div>
        <div class="last">Mohamed</div>
      </h1>

      <div class="hero-title">&gt; <span id="typedText">Turning data into business impact</span><span class="cursor"></span></div>

      <p class="hero-desc">
        Computer Science student at Alexandria National University with a passion for data-driven problem solving. I turn raw data into meaningful insights — from analysis and visualization to machine learning and real-world impact.
      </p>

      <div class="hero-ctas">
        <a href="#projects" class="btn-primary">View Projects</a>
        <a href="https://www.linkedin.com/in/marwanmohamedsaeed" target="_blank" class="btn-outline">LinkedIn Profile</a>
        <a href="mailto:2305425@anu.edu.eg" class="btn-outline">Email Me</a>
        <a href="https://wa.me/201225079504" target="_blank" class="btn-outline">WhatsApp</a>
      </div>

      <div class="hero-stats">
        <div class="stat-item">
          <div class="stat-num" id="counter1">0</div>
          <div class="stat-label">Projects Completed</div>
        </div>
        <div class="stat-item">
          <div class="stat-num" id="counter2">0</div>
          <div class="stat-label">Training Hours (NTI)</div>
        </div>
        <div class="stat-item">
          <div class="stat-num" id="counter3">0</div>
          <div class="stat-label">Years of Study</div>
        </div>
        <div class="stat-item">
          <div class="stat-num" id="counter4">0</div>
          <div class="stat-label">Certifications</div>
        </div>
      </div>
    </div>

    <div class="hero-photo">
      <img src="face.png" alt="Marwan Mohamed">
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <div class="section-tag">01 / About</div>
    <h2 class="section-title">Who I <span class="accent">Am</span></h2>
  </div>
  <div class="about-grid">
    <div class="about-text">
      <p>I'm <strong>Marwan Mohamed</strong>, a Computer Science student at <strong>Alexandria National University</strong> with a deep interest in data analysis, machine learning, and building intelligent systems that create real business value.</p>
      <p>I enjoy working with data from start to finish — understanding the problem, preparing and cleaning data, analyzing patterns, and presenting insights in a clear, impactful way. I'm passionate about combining <strong>analytical thinking</strong> with practical tools to solve real-world challenges.</p>
      <p>Currently training as an <strong>AI & Data Science – Microsoft Machine Learning Engineer</strong> at DEPI, and continuously growing my skills to transition from Data Analyst into a full Data Science career.</p>

      <div class="info-grid">
        <div class="info-item">
          <div class="info-label">Location</div>
          <div class="info-value">Alexandria, Egypt</div>
        </div>
        <div class="info-item">
          <div class="info-label">Status</div>
          <div class="info-value" style="color:var(--accent2)">Open to Internships</div>
        </div>
        <div class="info-item">
          <div class="info-label">Education</div>
          <div class="info-value">BSc CS — 2023–2027</div>
        </div>
        <div class="info-item">
          <div class="info-label">Contact</div>
          <div class="info-value" style="font-size:12px"><a href="https://www.linkedin.com/in/marwanmohamedsaeed" target="_blank" style="color:var(--accent2);text-decoration:none">LinkedIn Profile</a></div>
        </div>
      </div>
    </div>

    <div class="skills-panel">
      <div class="skill-category">
        <div class="skill-cat-title">Data Analysis & Science</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Pandas</span>
          <span class="skill-tag">NumPy</span>
          <span class="skill-tag">EDA</span>
          <span class="skill-tag">Statistics</span>
          <span class="skill-tag">Data Cleaning</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">Machine Learning</div>
        <div class="skill-tags">
          <span class="skill-tag">Scikit-learn</span>
          <span class="skill-tag">Logistic Regression</span>
          <span class="skill-tag">ML Fundamentals</span>
          <span class="skill-tag">Azure ML</span>
          <span class="skill-tag">Anthropic Claude</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">Databases & BI</div>
        <div class="skill-tags">
          <span class="skill-tag">SQL</span>
          <span class="skill-tag">Excel</span>
          <span class="skill-tag">Power BI</span>
          <span class="skill-tag">Data Pipelines</span>
        </div>
      </div>
      <div class="skill-category">
        <div class="skill-cat-title">Visualization & Tools</div>
        <div class="skill-tags">
          <span class="skill-tag">Matplotlib</span>
          <span class="skill-tag">Seaborn</span>
          <span class="skill-tag">Microsoft Azure</span>
          <span class="skill-tag">Git / GitHub</span>
          <span class="skill-tag">Jupyter</span>
        </div>
      </div>
    </div>
    <a class="skills-editor-trigger" onclick="openModal('skillsModal')">✎ Edit Skills</a>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-header">
    <div class="section-tag">02 / Projects</div>
    <h2 class="section-title">Featured <span class="accent">Work</span></h2>
  </div>

  <div class="filter-bar" id="projectFilters">
    <button class="filter-btn active" data-filter="all" onclick="filterProjects('all')">All</button>
    <button class="filter-btn" data-filter="Exploratory Data Analysis" onclick="filterProjects('Exploratory Data Analysis')">EDA</button>
    <button class="filter-btn" data-filter="Machine Learning" onclick="filterProjects('Machine Learning')">ML</button>
    <button class="filter-btn" data-filter="Business Intelligence" onclick="filterProjects('Business Intelligence')">BI</button>
  </div>

  <div class="projects-grid" id="projectsGrid">
    <div class="project-card" data-type="Exploratory Data Analysis">
      <button class="delete-btn" onclick="deleteProject(this)" title="Delete">✕</button>
      <div class="project-type"><span class="project-type-dot"></span>Exploratory Data Analysis</div>
      <div class="project-title">EDA on Real-World Dataset</div>
      <p class="project-desc">End-to-end exploratory data analysis project — cleaning raw data, uncovering patterns and outliers, and presenting actionable insights through visualizations.</p>
      <div class="project-tech">
        <span class="tech-badge">Python</span>
        <span class="tech-badge">Pandas</span>
        <span class="tech-badge">Matplotlib</span>
        <span class="tech-badge">Seaborn</span>
      </div>
      <div class="project-links">
        <a class="project-link" href="https://github.com/MarwanMohamedSaeed" target="_blank">⬡ GitHub</a>
      </div>
    </div>

    <div class="project-card" data-type="Machine Learning">
      <button class="delete-btn" onclick="deleteProject(this)" title="Delete">✕</button>
      <div class="project-type"><span class="project-type-dot"></span>Machine Learning</div>
      <div class="project-title">Classification Model with Logistic Regression</div>
      <p class="project-desc">Built and evaluated a binary classification model using logistic regression — covering data preprocessing, feature selection, model training, and performance metrics.</p>
      <div class="project-tech">
        <span class="tech-badge">Python</span>
        <span class="tech-badge">Scikit-learn</span>
        <span class="tech-badge">Pandas</span>
        <span class="tech-badge">Jupyter</span>
      </div>
      <div class="project-links">
        <a class="project-link" href="https://github.com/MarwanMohamedSaeed" target="_blank">⬡ GitHub</a>
      </div>
    </div>

    <div class="project-card" data-type="Business Intelligence">
      <button class="delete-btn" onclick="deleteProject(this)" title="Delete">✕</button>
      <div class="project-type"><span class="project-type-dot"></span>Business Intelligence</div>
      <div class="project-title">Interactive Dashboard — Power BI</div>
      <p class="project-desc">Designed an interactive Power BI dashboard to visualize KPIs and business metrics, enabling data-driven decision making with clean, executive-ready reports.</p>
      <div class="project-tech">
        <span class="tech-badge">Power BI</span>
        <span class="tech-badge">Excel</span>
        <span class="tech-badge">SQL</span>
      </div>
      <div class="project-links">
        <a class="project-link" href="https://github.com/MarwanMohamedSaeed" target="_blank">⬡ GitHub</a>
      </div>
    </div>

    <!-- Add Project Card -->
    <div class="add-project-card" onclick="openModal('projectModal')">
      <div class="add-icon">+</div>
      <p>Add Your Project</p>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <div class="section-tag">03 / Experience</div>
    <h2 class="section-title">Work <span class="accent">History</span></h2>
  </div>

  <div class="timeline" id="experienceTimeline">
    <div class="timeline-item">
      <button class="delete-btn" onclick="deleteExperience(this)" title="Delete">✕</button>
      <div class="timeline-dot"></div>
      <div class="timeline-date">Nov 2025 — Present</div>
      <div class="timeline-role">AI & Data Science – Microsoft ML Engineer</div>
      <div class="timeline-company">Digital Egypt Pioneers Initiative (DEPI) · Alexandria, Egypt</div>
      <div class="timeline-desc">
        <ul>
          <li>Hands-on training program applying Microsoft technologies to transform raw data from multiple pipelines into scalable, production-ready ML models</li>
          <li>Building and deploying machine learning models using Microsoft tools and Azure cloud environments</li>
          <li>Developing algorithms that enable machines to process data and identify patterns in real-world applications</li>
          <li>Practicing on Microsoft Azure through profile labs and cloud-based environments</li>
        </ul>
      </div>
    </div>

    <div class="timeline-item">
      <button class="delete-btn" onclick="deleteExperience(this)" title="Delete">✕</button>
      <div class="timeline-dot"></div>
      <div class="timeline-date">Jun 2025 — Jul 2025</div>
      <div class="timeline-role">Advanced Data Analysis Trainee</div>
      <div class="timeline-company">National Telecommunication Institute (NTI) · Alexandria, Egypt</div>
      <div class="timeline-desc">
        <ul>
          <li>Completed an intensive 120-hour Advanced Data Analytics Summer Training program — scored 99%</li>
          <li>Covered data analysis techniques, Python for data, data cleaning, and exploratory data analysis</li>
          <li>Extracted insights to support data-driven decisions across real-world datasets</li>
          <li>Additional training in freelancing and professional skills for real-world work environments</li>
        </ul>
      </div>
    </div>
  </div>

  <button class="btn-outline" style="margin-top:32px" onclick="openModal('experienceModal')">+ Add Experience</button>
</section>

<!-- CERTIFICATES -->
<section id="certificates">
  <div class="section-header">
    <div class="section-tag">04 / Certificates</div>
    <h2 class="section-title">My <span class="accent">Credentials</span></h2>
  </div>

  <div class="certs-grid" id="certsGrid">
    <div class="cert-card" onclick="window.open('Certficate/Nti.pdf','_blank')">
      <div class="cert-preview">
        <embed src="Certficate/Nti.pdf#page=1&view=FitH" type="application/pdf">
      </div>
      <div class="cert-info">
        <div class="cert-issuer">National Telecommunication Institute (NTI)</div>
        <div class="cert-name">Advanced Data Analytics Summer Training — Score: 99%</div>
        <div class="cert-date">Jul 2025</div>
        <a class="cert-open" href="Certficate/Nti.pdf" target="_blank">↗ Open Certificate</a>
      </div>
    </div>

    <div class="cert-card" onclick="window.open('Certficate/certificate-b85xynoteijk-1778859711.pdf','_blank')">
      <div class="cert-preview">
        <embed src="Certficate/certificate-b85xynoteijk-1778859711.pdf#page=1&view=FitH" type="application/pdf">
      </div>
      <div class="cert-info">
        <div class="cert-issuer">Anthropic</div>
        <div class="cert-name">Certificate of Completion: Claude 101</div>
        <div class="cert-date">2025</div>
        <a class="cert-open" href="Certficate/certificate-b85xynoteijk-1778859711.pdf" target="_blank">↗ Open Certificate</a>
      </div>
    </div>

    <div class="cert-card" onclick="window.open('Certficate/AWS_Academy_Graduate___Cloud_Foundations___Training_Badge_Badge20251211-32-1e1exn.pdf','_blank')">
      <div class="cert-preview">
        <embed src="Certficate/AWS_Academy_Graduate___Cloud_Foundations___Training_Badge_Badge20251211-32-1e1exn.pdf#page=1&view=FitH" type="application/pdf">
      </div>
      <div class="cert-info">
        <div class="cert-issuer">AWS Academy</div>
        <div class="cert-name">AWS Cloud Foundations — Training Badge</div>
        <div class="cert-date">Dec 2025</div>
        <a class="cert-open" href="Certficate/AWS_Academy_Graduate___Cloud_Foundations___Training_Badge_Badge20251211-32-1e1exn.pdf" target="_blank">↗ Open Certificate</a>
      </div>
    </div>

    <div class="cert-card" onclick="window.open('Certficate/NIVIDA.pdf','_blank')">
      <div class="cert-preview">
        <embed src="Certficate/NIVIDA.pdf#page=1&view=FitH" type="application/pdf">
      </div>
      <div class="cert-info">
        <div class="cert-issuer">NVIDIA</div>
        <div class="cert-name">NVIDIA AI Infrastructure & Fundamentals</div>
        <div class="cert-date">2025</div>
        <a class="cert-open" href="Certficate/NIVIDA.pdf" target="_blank">↗ Open Certificate</a>
      </div>
    </div>

    <div class="cert-card">
      <div class="cert-preview">
        <div class="cert-preview-icon">☁️</div>
      </div>
      <div class="cert-info">
        <div class="cert-issuer">Microsoft / DEPI</div>
        <div class="cert-name">AI & Data Science – Microsoft ML Engineer Training</div>
        <div class="cert-date">2025 — Present</div>
      </div>
    </div>

    <label class="cert-upload" for="certUpload">
      <div style="font-size:28px;color:var(--text3)">+</div>
      <p>Upload Certificate</p>
    </label>
    <input type="file" id="certUpload" accept=".pdf,.jpg,.jpeg,.png" onchange="handleCertUpload(event)">
  </div>
</section>

<!-- CV -->
<section id="cv">
  <div class="section-header">
    <div class="section-tag">05 / Resume</div>
    <h2 class="section-title">Download <span class="accent">CV</span></h2>
  </div>

  <div class="cv-panel">
    <div class="cv-header">
      <div>
        <div class="cv-title">Marwan Mohamed</div>
        <div class="cv-subtitle">Aspiring Data Scientist & Data Analyst</div>
      </div>
      <a class="btn-primary" href="Certficate/ATS_CV.pdf" target="_blank" download>Download CV</a>
    </div>

    <div class="cv-embed">
      <embed src="Certficate/ATS_CV.pdf#view=FitH" type="application/pdf">
    </div>

    <label for="cvUpload" style="display:block;cursor:pointer">
      <div class="cv-upload-zone" id="cvUploadZone">
        <div style="font-size:28px;color:var(--text3)">+</div>
        <p style="font-family:var(--mono);font-size:11px;color:var(--text3);text-transform:uppercase;letter-spacing:0.1em;margin-top:8px">Upload New CV</p>
      </div>
    </label>
    <input type="file" id="cvUpload" accept=".pdf,.doc,.docx" onchange="handleCVUpload(event)">

    <div class="cv-file-preview" id="cvPreview">
      <span class="cv-file-name" id="cvFileName"></span>
      <span style="font-family:var(--mono);font-size:11px;color:var(--accent)">✓ Uploaded</span>
    </div>
  </div>
</section>

<!-- WORK / GALLERY -->
<section id="work">
  <div class="section-header">
    <div class="section-tag">06 / Gallery</div>
    <h2 class="section-title">My <span class="accent">Work</span></h2>
  </div>

  <div class="work-grid" id="workGrid">

    <div class="work-add-btn" onclick="openModal('workModal')">
      <div style="font-size:32px;color:var(--text3)">+</div>
      <p>Add Work</p>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="section-header">
    <div class="section-tag">07 / Services</div>
    <h2 class="section-title">What I <span class="accent">Offer</span></h2>
  </div>

  <div class="services-grid" id="servicesGrid">
    <div class="add-service-btn" onclick="openServiceModal()">
      <div style="font-size:32px;color:var(--text3)">+</div>
      <p>Add Service</p>
    </div>
  </div>
</section>

<!-- SOCIAL -->
<section id="social">
  <div class="section-header">
    <div class="section-tag">08 / Connect</div>
    <h2 class="section-title">Social <span class="accent">Links</span></h2>
  </div>

  <div class="social-grid" id="socialGrid">
    <div class="social-card" style="cursor:pointer;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:12px;padding:32px;background:transparent;border:1px dashed var(--border2);text-decoration:none" onclick="openSocialModal()">
      <div style="font-size:28px;color:var(--text3)">+</div>
      <p style="font-family:var(--mono);font-size:11px;color:var(--text3);text-transform:uppercase;letter-spacing:0.1em">Add Social Link</p>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-grid">
    <div class="contact-info">
      <div class="section-tag">09 / Contact</div>
      <h2>Let's <span>Work</span><br>Together</h2>
      <p>I'm actively looking for internships, freelance projects, entry-level data roles, and learning opportunities. Feel free to reach out — I'm always open to meaningful discussions and new challenges.</p>

      <div class="contact-details">
        <div class="contact-detail">
          <div class="contact-detail-icon">✉</div>
          <a href="mailto:2305425@anu.edu.eg" style="color:var(--text2);text-decoration:none">2305425@anu.edu.eg</a>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-icon">📞</div>
          <a href="tel:01225079504" style="color:var(--text2);text-decoration:none">01225079504</a>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-icon">💬</div>
          <a href="https://wa.me/201225079504" target="_blank" style="color:var(--text2);text-decoration:none">WhatsApp</a>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-icon">📍</div>
          Alexandria, Egypt — Remote Worldwide
        </div>
        <div class="contact-detail">
          <div class="contact-detail-icon">⏰</div>
          Usually responds within 24h
        </div>
      </div>
    </div>

    <div class="contact-form">
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Name</label>
          <input class="form-input" type="text" placeholder="Your name" id="contactName">
        </div>
        <div class="form-group">
          <label class="form-label">Email</label>
          <input class="form-input" type="email" placeholder="your@email.com" id="contactEmail">
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Subject</label>
        <input class="form-input" type="text" placeholder="Project inquiry, collaboration..." id="contactSubject">
      </div>
      <div class="form-group">
        <label class="form-label">Message</label>
        <textarea class="form-textarea" placeholder="Tell me about your project or idea..." id="contactMessage"></textarea>
      </div>
      <button class="btn-primary" onclick="handleContact()">Send Message →</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025–2026 <span>Marwan Mohamed</span>. Built with precision.</p>
  <p style="font-family:var(--mono);font-size:11px;color:var(--text3)">ASPIRING DATA SCIENTIST / DATA ANALYST</p>
</footer>

<!-- BACK TO TOP -->
<a href="#hero" class="back-top" aria-label="Back to top">↑</a>

<!-- NOTIFICATION -->
<div class="notif" id="notif"></div>

<!-- MODALS -->
<!-- Project Modal -->
<div class="modal-overlay" id="projectModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('projectModal')">✕</button>
    <h3>Add New Project</h3>
    <p>Fill in your project details below.</p>
    <div class="modal-form">
      <div class="form-group">
        <label class="form-label">Project Type</label>
        <input class="form-input" type="text" placeholder="e.g. NLP, Computer Vision, Analytics" id="pType">
      </div>
      <div class="form-group">
        <label class="form-label">Project Title</label>
        <input class="form-input" type="text" placeholder="Project name" id="pTitle">
      </div>
      <div class="form-group">
        <label class="form-label">Description</label>
        <textarea class="form-textarea" placeholder="What does this project do?" id="pDesc" style="min-height:100px"></textarea>
      </div>
      <div class="form-group">
        <label class="form-label">Technologies (comma-separated)</label>
        <input class="form-input" type="text" placeholder="Python, TensorFlow, AWS..." id="pTech">
      </div>
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">GitHub URL</label>
          <input class="form-input" type="url" placeholder="https://github.com/..." id="pGithub">
        </div>
        <div class="form-group">
          <label class="form-label">Live URL</label>
          <input class="form-input" type="url" placeholder="https://..." id="pLive">
        </div>
      </div>
      <button class="btn-primary" onclick="addProject()">Add Project</button>
    </div>
  </div>
</div>

<!-- Experience Modal -->
<div class="modal-overlay" id="experienceModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('experienceModal')">✕</button>
    <h3>Add Experience</h3>
    <p>Add your work history entry.</p>
    <div class="modal-form">
      <div class="form-group">
        <label class="form-label">Period</label>
        <input class="form-input" type="text" placeholder="e.g. 2022 — 2024" id="eDate">
      </div>
      <div class="form-group">
        <label class="form-label">Role / Title</label>
        <input class="form-input" type="text" placeholder="Senior Data Scientist" id="eRole">
      </div>
      <div class="form-group">
        <label class="form-label">Company</label>
        <input class="form-input" type="text" placeholder="Company Name" id="eCompany">
      </div>
      <div class="form-group">
        <label class="form-label">Key Achievements (one per line)</label>
        <textarea class="form-textarea" placeholder="- Built ML pipeline...&#10;- Improved accuracy by 20%..." id="eDesc" style="min-height:120px"></textarea>
      </div>
      <button class="btn-primary" onclick="addExperience()">Add Experience</button>
    </div>
  </div>
</div>

<!-- Social Modal -->
<div class="modal-overlay" id="socialModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('socialModal')">✕</button>
    <h3 id="socialModalTitle">Add Social Link</h3>
    <p>Add a new social or professional link.</p>
    <div class="modal-form">
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Icon Text</label>
          <input class="form-input" type="text" placeholder="in / ⬡ / 𝕏 / M" id="socIcon" value="🌐" style="text-align:center;font-size:18px">
        </div>
        <div class="form-group">
          <label class="form-label">Icon Color</label>
          <input class="form-input" type="text" placeholder="#0077b5" id="socColor" value="#4f8eff">
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Platform Name</label>
        <input class="form-input" type="text" placeholder="LinkedIn, GitHub, Twitter..." id="socName">
      </div>
      <div class="form-group">
        <label class="form-label">URL</label>
        <input class="form-input" type="url" placeholder="https://..." id="socUrl">
      </div>
      <div class="form-group">
        <label class="form-label">Handle <span style="color:var(--text3);font-family:var(--mono);font-size:10px">(optional)</span></label>
        <input class="form-input" type="text" placeholder="@your-profile" id="socHandle">
      </div>
      <input type="hidden" id="socEditIndex" value="-1">
      <button class="btn-primary" onclick="saveSocial()">Save</button>
    </div>
  </div>
</div>

<!-- Skills Modal -->
<div class="modal-overlay" id="skillsModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('skillsModal')">✕</button>
    <h3>Edit Skills</h3>
    <p>Add or remove skills from your profile.</p>
    <div class="modal-form">
      <div class="form-group">
        <label class="form-label">Category</label>
        <select class="form-input" id="skillCategory">
          <option value="Data Analysis & Science">Data Analysis & Science</option>
          <option value="Machine Learning">Machine Learning</option>
          <option value="Databases & BI">Databases & BI</option>
          <option value="Visualization & Tools">Visualization & Tools</option>
        </select>
      </div>
      <div class="form-group">
        <label class="form-label">New Skill</label>
        <div style="display:flex;gap:8px">
          <input class="form-input" type="text" placeholder="e.g. TensorFlow" id="skillName" style="flex:1" onkeydown="if(event.key==='Enter')addSkill()">
          <button class="btn-primary" onclick="addSkill()" style="white-space:nowrap">+ Add</button>
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Current Skills</label>
        <div id="skillsEditorContainer"></div>
      </div>
      <button class="btn-primary" onclick="closeModal('skillsModal');showNotif('✓ Skills saved!')">Done</button>
    </div>
  </div>
</div>

<!-- Service Modal -->
<div class="modal-overlay" id="serviceModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('serviceModal')">✕</button>
    <h3 id="serviceModalTitle">Add Service</h3>
    <p>Create a new service offering for your portfolio.</p>
    <div class="modal-form">
      <div class="form-group">
        <label class="form-label">Icon (emoji)</label>
        <input class="form-input" type="text" placeholder="📊 🤖 📈 💻 🔧" id="sIcon" value="📊" style="font-size:24px;text-align:center">
      </div>
      <div class="form-group">
        <label class="form-label">Title</label>
        <input class="form-input" type="text" placeholder="e.g. Data Analysis & Insights" id="sTitle">
      </div>
      <div class="form-group">
        <label class="form-label">Description</label>
        <textarea class="form-textarea" placeholder="Describe the service..." id="sDesc" style="min-height:80px"></textarea>
      </div>
      <div class="form-group">
        <label class="form-label">What I Offer (one per line)</label>
        <textarea class="form-textarea" placeholder="Data cleaning & preprocessing&#10;Exploratory data analysis (EDA)&#10;..." id="sOffer" style="min-height:80px"></textarea>
      </div>
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Base Price ($)</label>
          <input class="form-input" type="number" placeholder="150" id="sPrice" min="0">
        </div>
        <div class="form-group">
          <label class="form-label">Duration</label>
          <input class="form-input" type="text" placeholder="e.g. 3–5 days" id="sDuration">
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Add-ons (name:price, one per line)</label>
        <textarea class="form-textarea" placeholder="Interactive dashboard:100&#10;API deployment:150" id="sAddons" style="min-height:60px"></textarea>
      </div>
      <input type="hidden" id="sEditIndex" value="-1">
      <button class="btn-primary" onclick="saveService()">Save Service</button>
    </div>
  </div>
</div>

<!-- Work Modal -->
<div class="modal-overlay" id="workModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('workModal')">✕</button>
    <h3>Add Work</h3>
    <p>Share details about your work or project.</p>
    <div class="modal-form">
      <div class="form-group">
        <label class="form-label">Photo</label>
        <label for="workPhotoInput" style="display:block;padding:32px;border:1px dashed var(--border2);text-align:center;cursor:pointer;transition:all 0.3s;background:rgba(79,142,255,0.02)" id="workPhotoZone" onmouseover="this.style.borderColor='var(--accent)'" onmouseout="this.style.borderColor=''" ondrop="handleWorkPhotoDrop(event)" ondragover="event.preventDefault()">
          <div id="workPhotoPlaceholder" style="font-size:32px;color:var(--text3)">📷</div>
          <p style="font-family:var(--mono);font-size:11px;color:var(--text3);text-transform:uppercase;letter-spacing:0.1em;margin-top:8px">Click to upload photo</p>
          <img id="workPhotoPreview" style="display:none;max-width:100%;max-height:200px;margin-top:8px;border:1px solid var(--border)">
        </label>
        <input type="file" id="workPhotoInput" accept="image/*" onchange="handleWorkPhotoSelect(event)" style="display:none">
      </div>
      <div class="form-group">
        <label class="form-label">Title</label>
        <input class="form-input" type="text" placeholder="e.g. Sales Dashboard, EDA Project..." id="wTitle">
      </div>
      <div class="form-group">
        <label class="form-label">Description</label>
        <textarea class="form-textarea" placeholder="What did you work on? What was the impact?" id="wDesc" style="min-height:80px"></textarea>
      </div>
      <div class="form-group">
        <label class="form-label">Skills Used (comma-separated)</label>
        <input class="form-input" type="text" placeholder="Python, Power BI, SQL..." id="wSkills">
      </div>
      <div class="form-group">
        <label class="form-label">URL <span style="color:var(--text3);font-family:var(--mono);font-size:10px">(optional)</span></label>
        <input class="form-input" type="url" placeholder="https://github.com/... or live link" id="wUrl">
      </div>
      <div class="form-group">
        <label class="form-label">Collaborators <span style="color:var(--text3);font-family:var(--mono);font-size:10px">(optional)</span></label>
        <input class="form-input" type="text" placeholder="John Doe, Jane Smith..." id="wCollab">
      </div>
      <button class="btn-primary" onclick="addWork()">Add Work</button>
    </div>
  </div>
</div>

<!-- Order Modal -->
<div class="modal-overlay" id="orderModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('orderModal')">✕</button>
    <h3 id="orderModalTitle">Order Service</h3>
    <p id="orderModalDesc">Fill in your details and I'll get back to you within 24 hours.</p>
    <div class="order-summary" id="orderSummary"></div>
    <div class="modal-form" id="orderForm">
      <div class="form-group">
        <label class="form-label">Your Name</label>
        <input class="form-input" type="text" placeholder="John Doe" id="orderName">
      </div>
      <div class="form-group">
        <label class="form-label">Email</label>
        <input class="form-input" type="email" placeholder="you@email.com" id="orderEmail">
      </div>
      <div class="form-group">
        <label class="form-label">Phone <span style="color:var(--text3);font-family:var(--mono);font-size:10px">(optional)</span></label>
        <input class="form-input" type="tel" placeholder="+20 100 000 0000" id="orderPhone">
      </div>
      <div class="form-group" id="addonsContainer">
        <label class="form-label">Add-ons</label>
        <div id="addonsList"></div>
      </div>
      <div class="form-group">
        <label class="form-label">Message <span style="color:var(--text3);font-family:var(--mono);font-size:10px">(optional)</span></label>
        <textarea class="form-textarea" placeholder="Tell me more about your project..." id="orderMessage" style="min-height:80px"></textarea>
      </div>
      <button class="btn-primary" onclick="submitOrder()">Send Order →</button>
    </div>
    <div id="orderConfirmation" style="display:none;text-align:center;padding:20px 0">
      <div style="font-size:48px;margin-bottom:16px">✅</div>
      <h3 style="color:var(--text);margin-bottom:8px">Order Sent!</h3>
      <p style="color:var(--text2);font-size:14px;line-height:1.6">I've received your order request. I'll review it and send you a confirmation email within 24 hours.</p>
    </div>
  </div>
</div>

<script>
  // COUNTER ANIMATION
  function animateCounter(id, target, suffix='') {
    let count = 0;
    const el = document.getElementById(id);
    const step = Math.ceil(target / 40);
    const timer = setInterval(() => {
      count = Math.min(count + step, target);
      el.textContent = count + suffix;
      if (count >= target) clearInterval(timer);
    }, 40);
  }

  setTimeout(() => {
    animateCounter('counter1', 10, '+');
    animateCounter('counter2', 120, '+');
    animateCounter('counter3', 2, '+');
    animateCounter('counter4', 2, '+');
  }, 500);

  // SCROLL FADE
  const observer = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.project-card, .cert-card, .timeline-item, .social-card, .work-card, .service-card').forEach(el => {
    el.classList.add('fade-in');
    observer.observe(el);
  });

  // MODALS
  function openModal(id) {
    document.getElementById(id).classList.add('active');
    document.body.style.overflow = 'hidden';
  }

  function closeModal(id) {
    document.getElementById(id).classList.remove('active');
    document.body.style.overflow = '';
  }

  document.querySelectorAll('.modal-overlay').forEach(overlay => {
    overlay.addEventListener('click', e => {
      if (e.target === overlay) {
        overlay.classList.remove('active');
        document.body.style.overflow = '';
      }
    });
  });

  // NOTIFICATION
  function showNotif(msg) {
    const n = document.getElementById('notif');
    n.textContent = msg;
    n.classList.add('show');
    setTimeout(() => n.classList.remove('show'), 3000);
  }

  // ADD PROJECT
  function addProject() {
    const type = document.getElementById('pType').value.trim();
    const title = document.getElementById('pTitle').value.trim();
    const desc = document.getElementById('pDesc').value.trim();
    const tech = document.getElementById('pTech').value.trim();
    const github = document.getElementById('pGithub').value.trim();
    const live = document.getElementById('pLive').value.trim();

    if (!title) { showNotif('Please enter a project title'); return; }

    const grid = document.getElementById('projectsGrid');
    const addBtn = grid.querySelector('.add-project-card');

    const tags = tech ? tech.split(',').map(t => `<span class="tech-badge">${t.trim()}</span>`).join('') : '';
    const links = (github ? `<a class="project-link" href="${github}" target="_blank">⬡ GitHub</a>` : '') +
                  (live ? `<a class="project-link" href="${live}" target="_blank">↗ Live Demo</a>` : '');

    const card = document.createElement('div');
    card.className = 'project-card fade-in';
    card.setAttribute('data-type', type || 'Project');
    card.innerHTML = `
      <button class="delete-btn" onclick="deleteProject(this)" title="Delete">✕</button>
      <div class="project-type"><span class="project-type-dot"></span>${type || 'Project'}</div>
      <div class="project-title">${title}</div>
      <p class="project-desc">${desc}</p>
      <div class="project-tech">${tags}</div>
      <div class="project-links">${links}</div>
    `;

    grid.insertBefore(card, addBtn);
    setTimeout(() => card.classList.add('visible'), 50);

    saveProjects();
    closeModal('projectModal');
    ['pType','pTitle','pDesc','pTech','pGithub','pLive'].forEach(id => document.getElementById(id).value = '');
    showNotif('✓ Project added!');
  }

  // ADD EXPERIENCE
  function addExperience() {
    const date = document.getElementById('eDate').value.trim();
    const role = document.getElementById('eRole').value.trim();
    const company = document.getElementById('eCompany').value.trim();
    const desc = document.getElementById('eDesc').value.trim();

    if (!role) { showNotif('Please enter a role title'); return; }

    const bullets = desc.split('\n').filter(l => l.trim()).map(l => `<li>${l.replace(/^[-•]\s*/, '')}</li>`).join('');

    const timeline = document.getElementById('experienceTimeline');
    const item = document.createElement('div');
    item.className = 'timeline-item fade-in';
    item.innerHTML = `
      <button class="delete-btn" onclick="deleteExperience(this)" title="Delete">✕</button>
      <div class="timeline-dot"></div>
      <div class="timeline-date">${date}</div>
      <div class="timeline-role">${role}</div>
      <div class="timeline-company">${company}</div>
      <div class="timeline-desc"><ul>${bullets}</ul></div>
    `;
    timeline.prepend(item);
    setTimeout(() => item.classList.add('visible'), 50);

    saveExperience();
    closeModal('experienceModal');
    ['eDate','eRole','eCompany','eDesc'].forEach(id => document.getElementById(id).value = '');
    showNotif('✓ Experience added!');
  }

  // CV UPLOAD
  function handleCVUpload(e) {
    const file = e.target.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = (ev) => {
      const data = ev.target.result;
      const embed = document.querySelector('.cv-embed embed');
      if (embed) embed.src = data;
      const btn = document.querySelector('.cv-header .btn-primary');
      if (btn) btn.href = data;
      document.getElementById('cvFileName').textContent = file.name;
      document.getElementById('cvPreview').style.display = 'flex';
      document.getElementById('cvUploadZone').innerHTML = `<div style="font-size:28px;color:var(--text3)">+</div><p style="font-family:var(--mono);font-size:11px;color:var(--text3);text-transform:uppercase;letter-spacing:0.1em;margin-top:8px">Upload New CV</p>`;
      showNotif('✓ CV uploaded successfully!');
    };
    reader.readAsDataURL(file);
  }

  // CERT UPLOAD
  function handleCertUpload(e) {
    const file = e.target.files[0];
    if (!file) return;
    const name = file.name.replace(/\.[^/.]+$/, '');
    const grid = document.getElementById('certsGrid');
    const isImage = file.type.startsWith('image/');

    const card = document.createElement('div');
    card.className = 'cert-card fade-in';

    if (isImage) {
      const reader = new FileReader();
      reader.onload = (ev) => {
        card.innerHTML = `
          <div class="cert-preview">
            <img src="${ev.target.result}" alt="${name}">
          </div>
          <div class="cert-info">
            <div class="cert-issuer">Uploaded Certificate</div>
            <div class="cert-name">${name}</div>
            <div class="cert-date">${new Date().getFullYear()}</div>
          </div>
        `;
      };
      reader.readAsDataURL(file);
    } else {
      const url = URL.createObjectURL(file);
      card.innerHTML = `
        <div class="cert-preview">
          <embed src="${url}" type="application/pdf">
        </div>
        <div class="cert-info">
          <div class="cert-issuer">Uploaded Certificate</div>
          <div class="cert-name">${name}</div>
          <div class="cert-date">${new Date().getFullYear()}</div>
        </div>
      `;
    }

    grid.querySelector('label').before(card);
    setTimeout(() => card.classList.add('visible'), 50);
    showNotif('✓ Certificate added!');
  }

  // WORK GALLERY
  let workPhotoData = null;

  function handleWorkPhotoSelect(e) {
    const file = e.target.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = (ev) => {
      workPhotoData = ev.target.result;
      const preview = document.getElementById('workPhotoPreview');
      const placeholder = document.getElementById('workPhotoPlaceholder');
      preview.src = workPhotoData;
      preview.style.display = 'block';
      placeholder.style.display = 'none';
      document.querySelector('#workPhotoZone p').textContent = 'Click to change photo';
    };
    reader.readAsDataURL(file);
  }

  function handleWorkPhotoDrop(e) {
    e.preventDefault();
    const file = e.dataTransfer.files[0];
    if (!file || !file.type.startsWith('image/')) return;
    const dt = new DataTransfer();
    dt.items.add(file);
    document.getElementById('workPhotoInput').files = dt.files;
    handleWorkPhotoSelect({ target: { files: dt.files } });
  }

  function addWork() {
    const title = document.getElementById('wTitle').value.trim();
    const desc = document.getElementById('wDesc').value.trim();
    const skills = document.getElementById('wSkills').value.trim();
    const url = document.getElementById('wUrl').value.trim();
    const collab = document.getElementById('wCollab').value.trim();

    if (!title) { showNotif('Please enter a title'); return; }

    const grid = document.getElementById('workGrid');
    const addBtn = grid.querySelector('.work-add-btn');

    const card = document.createElement('div');
    card.className = 'work-card fade-in';

    const imgHtml = workPhotoData
      ? `<img class="work-card-img" src="${workPhotoData}" alt="${title}">`
      : `<div class="work-card-img-placeholder">📷</div>`;

    const skillsHtml = skills
      ? skills.split(',').map(s => `<span class="work-card-skill">${s.trim()}</span>`).join('')
      : '';

    const urlHtml = url
      ? `<div class="work-card-meta-item">🔗 <a href="${url}" target="_blank" rel="noopener">${url}</a></div>`
      : '';

    const collabHtml = collab
      ? `<div class="work-card-meta-item">👥 ${collab}</div>`
      : '';

    card.innerHTML = `
      <button class="delete-btn" onclick="deleteWork(this)" title="Delete">✕</button>
      ${imgHtml}
      <div class="work-card-body">
        <div class="work-card-title">${title}</div>
        ${desc ? `<div class="work-card-desc">${desc}</div>` : ''}
        ${skillsHtml ? `<div class="work-card-skills">${skillsHtml}</div>` : ''}
        <div class="work-card-meta">
          ${urlHtml}
          ${collabHtml}
        </div>
      </div>
    `;

    grid.insertBefore(card, addBtn);
    setTimeout(() => card.classList.add('visible'), 50);

    saveWork();
    closeModal('workModal');
    workPhotoData = null;
    document.getElementById('workPhotoPreview').style.display = 'none';
    document.getElementById('workPhotoPlaceholder').style.display = 'block';
    document.getElementById('workPhotoZone').querySelector('p').textContent = 'Click to upload photo';
    document.getElementById('workPhotoInput').value = '';
    ['wTitle','wDesc','wSkills','wUrl','wCollab'].forEach(id => document.getElementById(id).value = '');
    showNotif('✓ Work added!');
  }

  // SOCIAL LINKS CRUD
  function openSocialModal(index) {
    document.getElementById('socialModalTitle').textContent = index >= 0 ? 'Edit Social Link' : 'Add Social Link';
    document.getElementById('socEditIndex').value = index >= 0 ? index : -1;

    if (index >= 0) {
      const socials = JSON.parse(localStorage.getItem('mwSocial') || '[]');
      const s = socials[index];
      document.getElementById('socIcon').value = s.icon || '🌐';
      document.getElementById('socColor').value = s.color || '#4f8eff';
      document.getElementById('socName').value = s.name || '';
      document.getElementById('socUrl').value = s.url || '';
      document.getElementById('socHandle').value = s.handle || '';
    } else {
      document.getElementById('socIcon').value = '🌐';
      document.getElementById('socColor').value = '#4f8eff';
      document.getElementById('socName').value = '';
      document.getElementById('socUrl').value = '';
      document.getElementById('socHandle').value = '';
    }
    openModal('socialModal');
  }

  function saveSocial() {
    const icon = document.getElementById('socIcon').value.trim() || '🌐';
    const color = document.getElementById('socColor').value.trim() || '#4f8eff';
    const name = document.getElementById('socName').value.trim();
    const url = document.getElementById('socUrl').value.trim();
    const handle = document.getElementById('socHandle').value.trim();
    const editIndex = parseInt(document.getElementById('socEditIndex').value);

    if (!name || !url) { showNotif('Please enter name and URL'); return; }

    const social = { icon, color, name, url, handle };

    let socials = JSON.parse(localStorage.getItem('mwSocial') || '[]');
    if (editIndex >= 0 && editIndex < socials.length) {
      socials[editIndex] = social;
    } else {
      socials.push(social);
    }
    localStorage.setItem('mwSocial', JSON.stringify(socials));

    closeModal('socialModal');
    renderSocial();
    showNotif(editIndex >= 0 ? '✓ Social link updated!' : '✓ Social link added!');
  }

  function deleteSocial(btn) {
    const card = btn.closest('.social-card');
    const idx = parseInt(card.getAttribute('data-index'));
    let socials = JSON.parse(localStorage.getItem('mwSocial') || '[]');
    socials.splice(idx, 1);
    localStorage.setItem('mwSocial', JSON.stringify(socials));
    card.style.transform = 'scale(0.95)'; card.style.opacity = '0';
    setTimeout(() => { renderSocial(); showNotif('✓ Social link deleted'); }, 300);
  }

  function renderSocial() {
    const grid = document.getElementById('socialGrid');
    const addBtn = grid.querySelector('.social-card[onclick*="openSocialModal"]');
    const socials = JSON.parse(localStorage.getItem('mwSocial') || '[]');

    grid.querySelectorAll('.social-card[data-index]').forEach(c => c.remove());

    socials.forEach((s, i) => {
      const card = document.createElement('a');
      card.className = 'social-card fade-in';
      card.setAttribute('data-index', i);
      card.href = s.url || '#';
      card.target = '_blank';
      card.rel = 'noopener';
      card.innerHTML = `
        <button class="delete-btn" onclick="event.stopPropagation();deleteSocial(this)" title="Delete">✕</button>
        <button class="edit-btn" onclick="event.stopPropagation();openSocialModal(${i})" title="Edit">✎</button>
        <div class="social-icon" style="background:rgba(0,0,0,0.06);color:${s.color || '#4f8eff'};font-size:18px;font-family:var(--mono);font-weight:bold">${s.icon || '🌐'}</div>
        <div class="social-name">${s.name}</div>
        ${s.handle ? `<div class="social-handle">${s.handle}</div>` : ''}
        <div class="social-arrow">↗</div>
      `;
      grid.insertBefore(card, addBtn);
      setTimeout(() => card.classList.add('visible'), 50 * i);
    });
  }

  // Init social links
  (function() {
    const socials = JSON.parse(localStorage.getItem('mwSocial') || '[]');
    if (socials.length === 0) {
      const defaults = [
        { icon: 'in', color: '#0077b5', name: 'LinkedIn', url: 'https://www.linkedin.com/in/marwanmohamedsaeed', handle: '@marwanmohamedsaeed' },
        { icon: '⬡', color: '#e8f0ff', name: 'GitHub', url: 'https://github.com/MarwanMohamedSaeed', handle: '@MarwanMohamedSaeed' },
        { icon: 'K', color: '#20b2e0', name: 'Kaggle', url: '#', handle: '@your-profile' },
        { icon: '𝕏', color: '#1d9bf0', name: 'X / Twitter', url: '#', handle: '@your-handle' },
        { icon: 'M', color: '#e8f0ff', name: 'Medium', url: '#', handle: '@your-blog' },
        { icon: '🤗', color: '#ffd300', name: 'Hugging Face', url: '#', handle: '@your-profile' }
      ];
      localStorage.setItem('mwSocial', JSON.stringify(defaults));
    }
    renderSocial();
  })();

  // CONTACT FORM
  function handleContact() {
    const name = document.getElementById('contactName').value.trim();
    const email = document.getElementById('contactEmail').value.trim();
    const msg = document.getElementById('contactMessage').value.trim();
    if (!name || !email || !msg) { showNotif('Please fill all required fields'); return; }
    showNotif('✓ Message sent! (demo mode)');
    ['contactName','contactEmail','contactSubject','contactMessage'].forEach(id => document.getElementById(id).value = '');
  }

  // MOBILE NAV
  function toggleMobile() {
    const links = document.querySelector('.nav-links');
    if (links.style.display === 'flex') {
      links.style.display = 'none';
    } else {
      links.style.cssText = 'display:flex;flex-direction:column;position:fixed;top:64px;left:0;right:0;background:rgba(5,8,16,0.98);padding:24px 8%;gap:20px;border-bottom:1px solid var(--border);z-index:999';
      links.querySelectorAll('a').forEach(a => {
        a.addEventListener('click', () => { links.style.display = 'none'; }, { once: true });
      });
    }
  }

  // DRAG AND DROP on CV zone
  const cvZone = document.getElementById('cvUploadZone');
  if (cvZone) {
    ['dragenter','dragover'].forEach(ev => {
      cvZone.addEventListener(ev, e => {
        e.preventDefault();
        cvZone.style.borderColor = 'var(--accent)';
        cvZone.style.background = 'rgba(79,142,255,0.08)';
      });
    });
    ['dragleave','drop'].forEach(ev => {
      cvZone.addEventListener(ev, e => {
        e.preventDefault();
        cvZone.style.borderColor = '';
        cvZone.style.background = '';
        if (ev === 'drop' && e.dataTransfer.files[0]) {
          const dt = new DataTransfer();
          dt.items.add(e.dataTransfer.files[0]);
          document.getElementById('cvUpload').files = dt.files;
          handleCVUpload({ target: { files: dt.files } });
        }
      });
    });
  }

  // ===== PRO FEATURES =====

  // SCROLL PROGRESS BAR
  window.addEventListener('scroll', () => {
    const h = document.documentElement;
    const pct = (h.scrollTop / (h.scrollHeight - h.clientHeight)) * 100;
    document.getElementById('scrollProgress').style.width = pct + '%';
  });

  // SCROLL SPY — active nav link
  const navLinks = document.querySelectorAll('.nav-links a');
  const sections = [...document.querySelectorAll('section[id]')];
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      const top = s.offsetTop - 150;
      if (window.scrollY >= top) current = s.id;
    });
    navLinks.forEach(a => {
      a.classList.toggle('active', a.getAttribute('href') === '#' + current);
    });
  });

  // TYPING EFFECT
  const typedEl = document.getElementById('typedText');
  if (typedEl) {
    const phrases = [
      'Turning data into business impact',
      'Building intelligent ML models',
      'Creating data-driven solutions',
      'Aspiring Data Scientist & Analyst'
    ];
    let idx = 0, charIdx = 0, isDeleting = false;
    function typeLoop() {
      const current = phrases[idx];
      if (!isDeleting) {
        typedEl.textContent = current.substring(0, charIdx + 1);
        charIdx++;
        if (charIdx === current.length) { isDeleting = true; setTimeout(typeLoop, 2000); return; }
      } else {
        typedEl.textContent = current.substring(0, charIdx - 1);
        charIdx--;
        if (charIdx === 0) { isDeleting = false; idx = (idx + 1) % phrases.length; }
      }
      setTimeout(typeLoop, isDeleting ? 30 : 60);
    }
    setTimeout(typeLoop, 1000);
  }

  // LOCAL STORAGE
  function saveProjects() {
    const cards = document.querySelectorAll('#projectsGrid .project-card:not(.add-project-card)');
    const data = [];
    cards.forEach(c => {
      const type = c.querySelector('.project-type')?.textContent?.trim() || '';
      const title = c.querySelector('.project-title')?.textContent?.trim() || '';
      const desc = c.querySelector('.project-desc')?.textContent?.trim() || '';
      const techs = [...c.querySelectorAll('.tech-badge')].map(t => t.textContent.trim());
      const links = [...c.querySelectorAll('.project-link')].map(l => ({ text: l.textContent.trim(), href: l.href }));
      data.push({ type, title, desc, techs, links });
    });
    localStorage.setItem('mwProjects', JSON.stringify(data));
  }

  function saveExperience() {
    const items = document.querySelectorAll('#experienceTimeline .timeline-item');
    const data = [];
    items.forEach(item => {
      const date = item.querySelector('.timeline-date')?.textContent?.trim() || '';
      const role = item.querySelector('.timeline-role')?.textContent?.trim() || '';
      const company = item.querySelector('.timeline-company')?.textContent?.trim() || '';
      const bullets = [...item.querySelectorAll('.timeline-desc li')].map(l => l.textContent.trim());
      data.push({ date, role, company, bullets });
    });
    localStorage.setItem('mwExperience', JSON.stringify(data));
  }

  function saveWork() {
    const cards = document.querySelectorAll('#workGrid .work-card');
    const data = [];
    cards.forEach(c => {
      const img = c.querySelector('.work-card-img');
      const title = c.querySelector('.work-card-title')?.textContent?.trim() || '';
      const desc = c.querySelector('.work-card-desc')?.textContent?.trim() || '';
      const skills = [...c.querySelectorAll('.work-card-skill')].map(s => s.textContent.trim());
      const urlEl = c.querySelector('.work-card-meta-item a');
      const collabEl = c.querySelector('.work-card-meta-item:not(:has(a))');
      data.push({
        img: img ? img.src : '',
        title, desc, skills,
        url: urlEl ? urlEl.href : '',
        collab: collabEl ? collabEl.textContent.replace(/^[^]*/, '').trim() : ''
      });
    });
    localStorage.setItem('mwWork', JSON.stringify(data));
  }

  // DELETE FUNCTIONS
  function deleteProject(btn) {
    const card = btn.closest('.project-card');
    card.style.transform = 'scale(0.95)'; card.style.opacity = '0';
    setTimeout(() => { card.remove(); saveProjects(); showNotif('✓ Project deleted'); }, 300);
  }

  function deleteExperience(btn) {
    const item = btn.closest('.timeline-item');
    item.style.transform = 'translateX(-20px)'; item.style.opacity = '0';
    setTimeout(() => { item.remove(); saveExperience(); showNotif('✓ Experience deleted'); }, 300);
  }

  function deleteWork(btn) {
    const card = btn.closest('.work-card');
    card.style.transform = 'scale(0.95)'; card.style.opacity = '0';
    setTimeout(() => { card.remove(); saveWork(); showNotif('✓ Work entry deleted'); }, 300);
  }

  // FILTER PROJECTS
  function filterProjects(type) {
    document.querySelectorAll('#projectFilters .filter-btn').forEach(b => b.classList.remove('active'));
    document.querySelector(`#projectFilters .filter-btn[data-filter="${type}"]`).classList.add('active');
    document.querySelectorAll('#projectsGrid .project-card').forEach(c => {
      if (type === 'all') { c.classList.remove('hidden'); return; }
      c.classList.toggle('hidden', c.getAttribute('data-type') !== type);
    });
  }

  // LIGHTBOX
  function openLightbox(src) {
    const lb = document.getElementById('lightbox');
    document.getElementById('lightboxImg').src = src;
    lb.classList.add('active');
    document.body.style.overflow = 'hidden';
  }
  function closeLightbox() {
    document.getElementById('lightbox').classList.remove('active');
    document.body.style.overflow = '';
  }
  document.addEventListener('keydown', e => { if (e.key === 'Escape') closeLightbox(); });

  // Click any work image to open lightbox
  document.addEventListener('click', e => {
    const img = e.target.closest('.work-card-img');
    if (img && img.src) openLightbox(img.src);
  });

  // SKILLS EDITOR
  const categoryMap = {
    'Data Analysis & Science': 0,
    'Machine Learning': 1,
    'Databases & BI': 2,
    'Visualization & Tools': 3
  };

  function loadSkillsEditor() {
    const container = document.getElementById('skillsEditorContainer');
    container.innerHTML = '';
    const cats = document.querySelectorAll('.skill-category');
    cats.forEach((cat, ci) => {
      const title = cat.querySelector('.skill-cat-title')?.textContent?.trim() || '';
      const tags = cat.querySelectorAll('.skill-tag');
      const div = document.createElement('div');
      div.style.marginBottom = '16px';
      div.innerHTML = `<div style="font-family:var(--mono);font-size:10px;color:var(--accent);text-transform:uppercase;letter-spacing:0.15em;margin-bottom:8px">${title}</div>`;
      const tagWrap = document.createElement('div');
      tagWrap.className = 'skill-editor-tags';
      tags.forEach(t => {
        const span = document.createElement('span');
        span.className = 'skill-editor-tag';
        span.innerHTML = `${t.textContent.trim()} <span class="skill-editor-tag-remove" onclick="removeSkill(this,'${title}')">✕</span>`;
        tagWrap.appendChild(span);
      });
      div.appendChild(tagWrap);
      container.appendChild(div);
    });
  }

  function addSkill() {
    const cat = document.getElementById('skillCategory').value;
    const name = document.getElementById('skillName').value.trim();
    if (!name) return;
    const catEls = document.querySelectorAll('.skill-category');
    const idx = categoryMap[cat];
    if (catEls[idx]) {
      const tags = catEls[idx].querySelector('.skill-tags');
      const span = document.createElement('span');
      span.className = 'skill-tag';
      span.textContent = name;
      tags.appendChild(span);
    }
    document.getElementById('skillName').value = '';
    loadSkillsEditor();
    showNotif('✓ Skill added!');
  }

  function removeSkill(el, category) {
    const name = el.parentElement.textContent.replace('✕', '').trim();
    const catEls = document.querySelectorAll('.skill-category');
    const idx = categoryMap[category];
    if (catEls[idx]) {
      const tags = catEls[idx].querySelectorAll('.skill-tag');
      tags.forEach(t => { if (t.textContent.trim() === name) t.remove(); });
    }
    loadSkillsEditor();
    showNotif('✓ Skill removed');
  }

  // Open skills modal — load editor
  const origSkillsOpen = openModal;
  openModal = function(id) {
    if (id === 'skillsModal') loadSkillsEditor();
    origSkillsOpen(id);
  };

  // Update counters based on actual data
  function updateCounters() {
    const projCount = document.querySelectorAll('#projectsGrid .project-card:not(.add-project-card)').length;
    const certCount = document.querySelectorAll('#certsGrid .cert-card').length;
    const expCount = document.querySelectorAll('#experienceTimeline .timeline-item').length;
    const counter1 = document.getElementById('counter1');
    const counter4 = document.getElementById('counter4');
    if (counter1) counter1.textContent = projCount + '+';
    if (counter4) counter4.textContent = certCount + '+';
  }

  // Run on page load
  setTimeout(updateCounters, 100);

  // ===== ORDER SERVICES =====
  let currentService = { name: '', basePrice: 0, addons: {} };

  function openOrderModal(name, basePrice, addons) {
    currentService = { name, basePrice, addons: addons || {} };
    document.getElementById('orderModalTitle').textContent = 'Order: ' + name;
    document.getElementById('orderModalDesc').textContent = 'Fill in your details and I\'ll get back to you within 24 hours.';
    document.getElementById('orderConfirmation').style.display = 'none';
    document.getElementById('orderForm').style.display = 'flex';
    document.getElementById('orderMessage').value = '';

    // Build summary
    const summary = document.getElementById('orderSummary');
    summary.innerHTML = `
      <h4>${name}</h4>
      <div class="order-summary-row"><span>Base price</span><span>$${basePrice}</span></div>
    `;

    // Build addons checkboxes
    const container = document.getElementById('addonsList');
    container.innerHTML = '';
    const keys = Object.keys(addons);
    if (keys.length === 0) {
      document.getElementById('addonsContainer').style.display = 'none';
    } else {
      document.getElementById('addonsContainer').style.display = 'block';
      keys.forEach(key => {
        const label = document.createElement('label');
        label.style.cssText = 'display:flex;align-items:center;gap:10px;padding:8px 12px;background:rgba(79,142,255,0.04);border:1px solid var(--border);cursor:pointer;transition:all 0.2s';
        label.onmouseover = () => label.style.borderColor = 'var(--accent)';
        label.onmouseout = () => label.style.borderColor = '';
        const cb = document.createElement('input');
        cb.type = 'checkbox';
        cb.style.cssText = 'accent-color:var(--accent);width:16px;height:16px';
        cb.onchange = () => updateOrderSummary();
        const span = document.createElement('span');
        span.style.cssText = 'flex:1;font-size:13px;color:var(--text2)';
        span.textContent = key;
        const price = document.createElement('span');
        price.style.cssText = 'font-family:var(--mono);font-size:12px;color:var(--accent3)';
        price.textContent = '+$' + addons[key];
        label.appendChild(cb);
        label.appendChild(span);
        label.appendChild(price);
        container.appendChild(label);
      });
    }

    updateOrderSummary();
    openModal('orderModal');
  }

  function updateOrderSummary() {
    const summary = document.getElementById('orderSummary');
    let total = currentService.basePrice;
    const addonLines = [];
    const checkboxes = document.querySelectorAll('#addonsList input[type="checkbox"]');
    const keys = Object.keys(currentService.addons);
    checkboxes.forEach((cb, i) => {
      if (cb.checked && keys[i]) {
        total += currentService.addons[keys[i]];
        addonLines.push(`<div class="order-summary-row"><span>+ ${keys[i]}</span><span>+$${currentService.addons[keys[i]]}</span></div>`);
      }
    });
    summary.innerHTML = `
      <h4>${currentService.name}</h4>
      <div class="order-summary-row"><span>Base price</span><span>$${currentService.basePrice}</span></div>
      ${addonLines.join('')}
      <div class="order-summary-row total"><span>Total</span><span>$${total}</span></div>
    `;
  }

  function submitOrder() {
    const name = document.getElementById('orderName').value.trim();
    const email = document.getElementById('orderEmail').value.trim();
    const phone = document.getElementById('orderPhone').value.trim();
    const msg = document.getElementById('orderMessage').value.trim();
    if (!name || !email) { showNotif('Please enter your name and email'); return; }

    // Build addon list
    let addonDetails = '';
    const checkboxes = document.querySelectorAll('#addonsList input[type="checkbox"]');
    const keys = Object.keys(currentService.addons);
    let total = currentService.basePrice;
    checkboxes.forEach((cb, i) => {
      if (cb.checked && keys[i]) {
        addonDetails += `  - ${keys[i]}: +$${currentService.addons[keys[i]]}\n`;
        total += currentService.addons[keys[i]];
      }
    });

    const orderText = `NEW SERVICE ORDER
--------------------------
Service: ${currentService.name}
Customer: ${name}
Email: ${email}
Phone: ${phone || 'N/A'}
Message: ${msg || 'N/A'}
--------------------------
Base price: $${currentService.basePrice}
${addonDetails ? `Add-ons:\n${addonDetails}` : ''}
Total: $${total}
--------------------------`;

    // Save to localStorage for record
    const orders = JSON.parse(localStorage.getItem('mwOrders') || '[]');
    orders.push({ service: currentService.name, name, email, phone, msg, total, date: new Date().toISOString() });
    localStorage.setItem('mwOrders', JSON.stringify(orders));

    // Open mailto for owner
    const mailto = `mailto:2305425@anu.edu.eg?subject=New Order: ${encodeURIComponent(currentService.name)} from ${encodeURIComponent(name)}&body=${encodeURIComponent(orderText)}`;
    window.open(mailto);

    // Show confirmation
    document.getElementById('orderForm').style.display = 'none';
    document.getElementById('orderConfirmation').style.display = 'block';
    document.getElementById('orderModalDesc').textContent = '';

    // Reset form
    document.getElementById('orderName').value = '';
    document.getElementById('orderEmail').value = '';
    document.getElementById('orderPhone').value = '';
    document.getElementById('orderMessage').value = '';

    showNotif('✓ Order sent! Check your email for confirmation.');
  }

  // ===== SERVICES CRUD =====
  function openServiceModal(index) {
    document.getElementById('serviceModalTitle').textContent = index >= 0 ? 'Edit Service' : 'Add Service';
    document.getElementById('sEditIndex').value = index >= 0 ? index : -1;

    if (index >= 0) {
      const services = JSON.parse(localStorage.getItem('mwServices') || '[]');
      const s = services[index];
      document.getElementById('sIcon').value = s.icon || '📊';
      document.getElementById('sTitle').value = s.title || '';
      document.getElementById('sDesc').value = s.desc || '';
      document.getElementById('sOffer').value = (s.offer || []).join('\n');
      document.getElementById('sPrice').value = s.price || '';
      document.getElementById('sDuration').value = s.duration || '';
      document.getElementById('sAddons').value = (s.addons || []).map(a => `${a.name}:${a.price}`).join('\n');
    } else {
      ['sIcon','sTitle','sDesc','sOffer','sPrice','sDuration','sAddons'].forEach(id => document.getElementById(id).value = '');
      document.getElementById('sIcon').value = '📊';
    }

    openModal('serviceModal');
  }

  function saveService() {
    const icon = document.getElementById('sIcon').value.trim() || '📊';
    const title = document.getElementById('sTitle').value.trim();
    const desc = document.getElementById('sDesc').value.trim();
    const offerRaw = document.getElementById('sOffer').value.trim();
    const price = parseInt(document.getElementById('sPrice').value) || 0;
    const duration = document.getElementById('sDuration').value.trim();
    const addonsRaw = document.getElementById('sAddons').value.trim();
    const editIndex = parseInt(document.getElementById('sEditIndex').value);

    if (!title) { showNotif('Please enter a service title'); return; }
    if (!price) { showNotif('Please enter a base price'); return; }

    const offer = offerRaw.split('\n').filter(l => l.trim()).map(l => l.trim());
    const addons = addonsRaw.split('\n').filter(l => l.trim()).map(l => {
      const parts = l.split(':');
      return { name: parts[0].trim(), price: parseInt(parts[1]) || 0 };
    });

    const service = { icon, title, desc, offer, price, duration, addons };

    let services = JSON.parse(localStorage.getItem('mwServices') || '[]');
    if (editIndex >= 0 && editIndex < services.length) {
      services[editIndex] = service;
    } else {
      services.push(service);
    }
    localStorage.setItem('mwServices', JSON.stringify(services));

    closeModal('serviceModal');
    renderServices();
    showNotif(editIndex >= 0 ? '✓ Service updated!' : '✓ Service added!');
  }

  function deleteService(btn) {
    const card = btn.closest('.service-card');
    const idx = parseInt(card.getAttribute('data-index'));
    let services = JSON.parse(localStorage.getItem('mwServices') || '[]');
    services.splice(idx, 1);
    localStorage.setItem('mwServices', JSON.stringify(services));
    card.style.transform = 'scale(0.95)'; card.style.opacity = '0';
    setTimeout(() => { renderServices(); showNotif('✓ Service deleted'); }, 300);
  }

  function renderServices() {
    const grid = document.getElementById('servicesGrid');
    const addBtn = grid.querySelector('.add-service-btn');
    const services = JSON.parse(localStorage.getItem('mwServices') || '[]');

    // Remove all service cards
    grid.querySelectorAll('.service-card').forEach(c => c.remove());

    // Re-render each service
    services.forEach((s, i) => {
      const offerHtml = (s.offer || []).map(o => `<div class="service-offer-item">${o}</div>`).join('');
      const addonHtml = (s.addons || []).map(a => `<div class="service-addon-item"><span>+ ${a.name}</span> <span class="service-addon-price">+$${a.price}</span></div>`).join('');

      const addonObj = {};
      (s.addons || []).forEach(a => { addonObj[a.name] = a.price; });

      const card = document.createElement('div');
      card.className = 'service-card fade-in';
      card.setAttribute('data-index', i);
      card.innerHTML = `
        <button class="delete-btn" onclick="deleteService(this)" title="Delete">✕</button>
        <button class="edit-btn" onclick="openServiceModal(${i})" title="Edit">✎</button>
        <div class="service-img-placeholder">${s.icon || '📊'}</div>
        <div class="service-body">
          <div class="service-title">${s.title}</div>
          ${s.desc ? `<div class="service-desc">${s.desc}</div>` : ''}
          <div class="service-offer">${offerHtml}</div>
          ${addonHtml ? `<div class="service-addons">${addonHtml}</div>` : ''}
          <div class="service-meta">
            <div class="service-price">$${s.price} <small>starting</small></div>
            ${s.duration ? `<div class="service-duration">⏱ ${s.duration}</div>` : ''}
          </div>
          <button class="service-order-btn" onclick='openOrderModal("${s.title.replace(/'/g, "\\'")}", ${s.price}, ${JSON.stringify(addonObj)})'>Order Now →</button>
        </div>
      `;
      grid.insertBefore(card, addBtn);
      setTimeout(() => card.classList.add('visible'), 50 * i);
    });
  }

  // Load services on page init
  (function() {
    const services = JSON.parse(localStorage.getItem('mwServices') || '[]');
    if (services.length === 0) {
      // Seed default services
      const defaults = [
        { icon: '📊', title: 'Data Analysis & Insights', desc: 'Transform raw data into actionable insights with clean analysis, visualizations, and data-driven recommendations tailored to your business.', offer: ['Data cleaning & preprocessing','Exploratory data analysis (EDA)','Statistical analysis & hypothesis testing','Visualization report (PDF / interactive)'], price: 150, duration: '3–5 days', addons: [{name:'Interactive dashboard',price:100},{name:'Predictive model integration',price:200}] },
        { icon: '🤖', title: 'Machine Learning Solutions', desc: 'End-to-end ML model development — from problem framing and data preparation to model training, evaluation, and deployment guidance.', offer: ['Problem scoping & feasibility analysis','Model selection & training','Hyperparameter tuning & evaluation','Deployment guide & documentation'], price: 300, duration: '5–10 days', addons: [{name:'API deployment (Flask/FastAPI)',price:150},{name:'Model monitoring setup',price:100}] },
        { icon: '📈', title: 'Power BI Dashboard', desc: 'Interactive, executive-ready Power BI dashboards that visualize KPIs and business metrics for data-driven decision making.', offer: ['Data source connection & modeling','DAX measures & calculated columns','Interactive visuals & slicers','Publishing & sharing setup'], price: 200, duration: '3–7 days', addons: [{name:'Automated data refresh',price:80},{name:'Mobile-optimized layout',price:60}] }
      ];
      localStorage.setItem('mwServices', JSON.stringify(defaults));
    }
    renderServices();
  })();
</script>
</body>
</html>
