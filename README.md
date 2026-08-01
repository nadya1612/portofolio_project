<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nadya Divia Go — Data Analyst Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #0B1220;
    --bg-alt: #0E1626;
    --surface: #121A2B;
    --surface-hi: #17223A;
    --line: #223050;
    --teal: #2DD4BF;
    --amber: #F5A524;
    --text: #E8ECF3;
    --muted: #8B96AC;
    --faint: #56637E;
    --radius: 14px;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:
      radial-gradient(1200px 600px at 85% -10%, rgba(45,212,191,0.08), transparent 60%),
      radial-gradient(900px 500px at -10% 30%, rgba(245,165,36,0.06), transparent 55%),
      var(--bg);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit; text-decoration:none;}
  h1,h2,h3{font-family:'Space Grotesk', sans-serif; letter-spacing:-0.01em;}
  .mono{font-family:'JetBrains Mono', monospace;}
  .wrap{max-width:1080px; margin:0 auto; padding:0 28px;}
  ::selection{background:var(--teal); color:#06110F;}

  /* focus states */
  a:focus-visible, button:focus-visible{
    outline:2px solid var(--teal);
    outline-offset:3px;
    border-radius:4px;
  }

  /* ---------- NAV ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgba(11,18,32,0.82);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  nav.wrap{
    display:flex; align-items:center; justify-content:space-between;
    height:68px;
  }
  .brand{
    font-family:'Space Grotesk', sans-serif;
    font-weight:600; font-size:17px;
    display:flex; align-items:center; gap:9px;
  }
  .brand .dot{
    width:9px; height:9px; border-radius:2px;
    background:var(--teal);
    box-shadow:0 0 12px rgba(45,212,191,0.7);
    display:inline-block;
    transform:rotate(45deg);
  }
  .navlinks{display:flex; gap:32px; font-size:14px; color:var(--muted);}
  .navlinks a{transition:color .2s ease; position:relative;}
  .navlinks a:hover{color:var(--text);}
  @media (max-width:720px){ .navlinks{display:none;} }

  /* ---------- HERO ---------- */
  .hero{
    padding:96px 0 88px;
    position:relative;
    overflow:hidden;
    border-bottom:1px solid var(--line);
  }
  .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    color:var(--teal);
    letter-spacing:.06em;
    display:flex; align-items:center; gap:10px;
    margin-bottom:22px;
  }
  .eyebrow::before{
    content:"";
    width:26px; height:1px;
    background:var(--teal);
    display:inline-block;
  }
  .hero h1{
    font-size:clamp(38px, 6vw, 62px);
    font-weight:700;
    line-height:1.05;
    max-width:820px;
  }
  .hero .role{
    color:var(--faint);
    font-weight:500;
  }
  .hero p.lede{
    margin-top:22px;
    max-width:560px;
    color:var(--muted);
    font-size:16.5px;
  }
  .hero-actions{
    margin-top:36px;
    display:flex; gap:14px; flex-wrap:wrap;
    align-items:center;
  }
  .btn{
    display:inline-flex; align-items:center; gap:8px;
    padding:12px 22px;
    border-radius:8px;
    font-size:14px; font-weight:600;
    font-family:'Inter', sans-serif;
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease, border-color .18s ease;
    border:1px solid transparent;
  }
  .btn-primary{
    background:var(--teal);
    color:#06110F;
  }
  .btn-primary:hover{transform:translateY(-2px); box-shadow:0 10px 24px rgba(45,212,191,0.25);}
  .btn-ghost{
    border-color:var(--line);
    color:var(--text);
  }
  .btn-ghost:hover{border-color:var(--teal); color:var(--teal); transform:translateY(-2px);}

  .sparkline{
    position:absolute;
    right:-40px; top:40px;
    width:520px; max-width:60vw;
    opacity:.55;
  }
  @media (max-width:720px){ .sparkline{display:none;} }

  /* stat strip */
  .stats{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
  }
  .stats div{
    padding:26px 28px;
    border-right:1px solid var(--line);
  }
  .stats div:last-child{border-right:none;}
  .stats .num{
    font-family:'Space Grotesk', sans-serif;
    font-size:28px; font-weight:700; color:var(--teal);
  }
  .stats .label{
    font-family:'JetBrains Mono', monospace;
    font-size:11.5px; color:var(--muted); margin-top:4px; letter-spacing:.03em;
  }
  @media (max-width:720px){
    .stats{grid-template-columns:repeat(2,1fr);}
    .stats div:nth-child(2){border-right:none;}
  }

  /* ---------- SECTION SHELL ---------- */
  section{padding:88px 0;}
  .section-head{
    display:flex; align-items:baseline; justify-content:space-between;
    margin-bottom:42px; flex-wrap:wrap; gap:12px;
  }
  .section-head h2{font-size:30px; font-weight:700;}
  .section-index{
    font-family:'JetBrains Mono', monospace;
    color:var(--faint); font-size:13px;
  }
  .section-sub{color:var(--muted); max-width:560px; margin-top:10px; font-size:15px;}

  /* ---------- ABOUT ---------- */
  #about{border-bottom:1px solid var(--line); background:var(--bg-alt);}
  .about-grid{
    display:grid; grid-template-columns:1.3fr 1fr; gap:56px;
  }
  @media (max-width:800px){ .about-grid{grid-template-columns:1fr;} }
  .about-grid p{color:var(--muted); font-size:15.5px; margin-bottom:16px;}
  .about-grid p strong{color:var(--text); font-weight:600;}
  .toolbox{
    background:var(--surface);
    border:1px solid var(--line);
    border-radius:var(--radius);
    padding:26px;
  }
  .toolbox h3{
    font-size:13px; font-family:'JetBrains Mono', monospace;
    color:var(--faint); text-transform:uppercase; letter-spacing:.06em;
    margin-bottom:18px;
  }
  .tool-row{
    display:flex; justify-content:space-between; align-items:center;
    padding:11px 0;
    border-bottom:1px solid var(--line);
    font-size:14.5px;
  }
  .tool-row:last-child{border-bottom:none;}
  .tool-bar{
    width:96px; height:4px; background:var(--line); border-radius:4px; overflow:hidden;
  }
  .tool-bar i{display:block; height:100%; background:var(--teal); border-radius:4px;}

  /* ---------- DASHBOARDS (Tableau) ---------- */
  #dashboards{border-bottom:1px solid var(--line);}
  .card-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:22px;
  }
  @media (max-width:760px){ .card-grid{grid-template-columns:1fr;} }

  .viz-card{
    border:1px solid var(--line);
    border-radius:var(--radius);
    background:var(--surface);
    overflow:hidden;
    transition:transform .22s ease, border-color .22s ease, box-shadow .22s ease;
    display:flex; flex-direction:column;
  }
  .viz-card:hover{
    transform:translateY(-4px);
    border-color:rgba(45,212,191,0.45);
    box-shadow:0 18px 40px rgba(0,0,0,0.35);
  }
  .viz-thumb{
    height:150px;
    position:relative;
    display:flex; align-items:flex-end;
    padding:18px;
    background:
      linear-gradient(180deg, transparent 0%, rgba(0,0,0,0.35) 100%),
      var(--viz-color, linear-gradient(135deg, #16324a, #0e1626));
    border-bottom:1px solid var(--line);
  }
  .viz-thumb svg{position:absolute; inset:0; width:100%; height:100%;}
  .viz-tag{
    font-family:'JetBrains Mono', monospace;
    font-size:10.5px;
    background:rgba(0,0,0,0.5);
    padding:4px 9px;
    border-radius:5px;
    color:var(--teal);
    position:relative; z-index:2;
    border:1px solid rgba(45,212,191,0.35);
  }
  .viz-body{padding:22px 22px 24px; flex:1; display:flex; flex-direction:column;}
  .viz-body h3{font-size:17px; margin-bottom:8px;}
  .viz-body p{color:var(--muted); font-size:14px; flex:1;}
  .viz-link{
    margin-top:16px;
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    color:var(--teal);
    display:inline-flex; align-items:center; gap:6px;
  }
  .viz-link svg{width:12px; height:12px; transition:transform .18s ease;}
  .viz-card:hover .viz-link svg{transform:translate(2px,-2px);}

  /* ---------- GITHUB PROJECTS ---------- */
  #projects{border-bottom:1px solid var(--line); background:var(--bg-alt);}
  .proj-list{display:flex; flex-direction:column;}
  .proj-row{
    display:grid;
    grid-template-columns:36px 1.6fr 2fr auto;
    gap:20px;
    align-items:center;
    padding:22px 4px;
    border-bottom:1px solid var(--line);
    transition:background .18s ease, padding-left .18s ease;
  }
  .proj-row:first-child{border-top:1px solid var(--line);}
  .proj-row:hover{background:rgba(45,212,191,0.04); padding-left:12px;}
  .proj-num{font-family:'JetBrains Mono', monospace; color:var(--faint); font-size:13px;}
  .proj-name{font-weight:600; font-size:16px;}
  .proj-name .repo-owner{color:var(--faint); font-weight:400; font-size:13px; display:block; font-family:'JetBrains Mono', monospace; margin-top:3px;}
  .proj-desc{color:var(--muted); font-size:13.8px;}
  .proj-link{
    font-family:'JetBrains Mono', monospace; font-size:12.5px;
    color:var(--teal); white-space:nowrap;
    display:inline-flex; align-items:center; gap:6px;
  }
  .proj-link svg{width:12px; height:12px;}
  @media (max-width:760px){
    .proj-row{grid-template-columns:24px 1fr; row-gap:8px;}
    .proj-desc{grid-column:2; }
    .proj-link{grid-column:2;}
  }

  /* ---------- CONTACT ---------- */
  #contact{padding:100px 0 110px;}
  .contact-inner{
    border:1px solid var(--line);
    border-radius:20px;
    padding:56px;
    background:
      radial-gradient(600px 240px at 90% 0%, rgba(45,212,191,0.08), transparent 60%),
      var(--surface);
    display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:32px;
  }
  .contact-inner h2{font-size:32px; max-width:460px; line-height:1.2;}
  .contact-inner .lede{color:var(--muted); margin-top:12px; max-width:420px; font-size:15px;}
  .contact-links{display:flex; flex-direction:column; gap:14px; align-items:flex-start;}
  .contact-link{
    font-family:'JetBrains Mono', monospace;
    font-size:14.5px;
    display:flex; align-items:center; gap:10px;
    padding:11px 18px;
    border:1px solid var(--line);
    border-radius:8px;
    transition:border-color .18s ease, color .18s ease, transform .18s ease;
    min-width:280px;
  }
  .contact-link:hover{border-color:var(--teal); color:var(--teal); transform:translateX(3px);}
  .contact-link svg{width:15px; height:15px; flex-shrink:0;}

  footer{
    text-align:center;
    padding:34px 0 46px;
    color:var(--faint);
    font-size:12.5px;
    font-family:'JetBrains Mono', monospace;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation:none !important; transition:none !important;}
  }

  .reveal{opacity:0; transform:translateY(16px); transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1; transform:translateY(0);}
</style>
</head>
<body>

<header>
  <nav class="wrap">
    <div class="brand"><span class="dot"></span>Nadya Divia Go</div>
    <div class="navlinks">
      <a href="#about">About</a>
      <a href="#dashboards">Dashboards</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </div>
    <a href="#contact" class="btn btn-ghost" style="padding:9px 18px; font-size:13px;">Get in touch</a>
  </nav>
</header>

<section class="hero">
  <div class="wrap">
    <div class="eyebrow mono">DATA ANALYST — DASHBOARDS · SQL · PYTHON</div>
    <h1>Turning raw data into<br>decisions people can <span style="color:var(--teal);">act on.</span></h1>
    <p class="lede">I'm Nadya — a data analyst who builds clear, business-ready dashboards and analyses. Below is a working set of Tableau dashboards and GitHub projects covering retention, sales, marketing and machine learning.</p>
    <div class="hero-actions">
      <a href="#dashboards" class="btn btn-primary">View dashboards</a>
      <a href="#projects" class="btn btn-ghost">Browse GitHub projects</a>
    </div>
  </div>

  <svg class="sparkline" viewBox="0 0 520 220" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
    <polyline points="0,170 40,150 80,160 120,110 160,130 200,80 240,95 280,50 320,70 360,30 400,55 440,20 480,40 520,10"
      stroke="#2DD4BF" stroke-width="2" opacity="0.55"/>
    <polyline points="0,190 40,195 80,175 120,185 160,150 200,165 240,120 280,140 320,100 360,115 400,80 440,95 480,60 520,75"
      stroke="#F5A524" stroke-width="2" opacity="0.35"/>
    <circle cx="520" cy="10" r="4" fill="#2DD4BF"/>
    <circle cx="520" cy="75" r="4" fill="#F5A524"/>
  </svg>
</section>

<div class="stats wrap" style="max-width:1080px; margin:0 auto; padding-left:0; padding-right:0;">
  <div><div class="num">4</div><div class="label mono">TABLEAU DASHBOARDS</div></div>
  <div><div class="num">6</div><div class="label mono">GITHUB PROJECTS</div></div>
  <div><div class="num">3</div><div class="label mono">DOMAINS · RETAIL / FINANCE / ML</div></div>
  <div><div class="num">SQL·PY</div><div class="label mono">CORE TOOLSTACK</div></div>
</div>

<section id="about">
  <div class="wrap">
    <div class="section-head">
      <h2>About</h2>
      <span class="section-index mono">01 / PROFILE</span>
    </div>
    <div class="about-grid">
      <div class="reveal">
        <p><strong>I help teams see what their data is actually saying.</strong> My work spans exploratory analysis, dashboard design and lightweight machine learning — always aimed at a decision someone needs to make, not just a chart to look at.</p>
        <p>Recent projects include a receivables dashboard for business action-tracking, regional sales distribution analysis, customer cohort and retention studies, a bakery/café sales analysis, a capstone project for a property developer, and a bank marketing campaign model.</p>
        <p>I work primarily in <strong>Tableau, SQL and Python</strong>, and I care about dashboards that are readable at a glance and analyses that hold up under questions.</p>
      </div>
      <div class="toolbox reveal">
        <h3>Core toolstack</h3>
        <div class="tool-row"><span>Tableau</span><div class="tool-bar"><i style="width:95%"></i></div></div>
        <div class="tool-row"><span>SQL</span><div class="tool-bar"><i style="width:88%"></i></div></div>
        <div class="tool-row"><span>Python (Pandas)</span><div class="tool-bar"><i style="width:80%"></i></div></div>
        <div class="tool-row"><span>Excel / Sheets</span><div class="tool-bar"><i style="width:85%"></i></div></div>
        <div class="tool-row"><span>Machine Learning (basics)</span><div class="tool-bar"><i style="width:60%"></i></div></div>
      </div>
    </div>
  </div>
</section>

<section id="dashboards">
  <div class="wrap">
    <div class="section-head">
      <div>
        <h2>Tableau dashboards</h2>
        <p class="section-sub">Interactive dashboards published on Tableau Public — click through to explore each one live.</p>
      </div>
      <span class="section-index mono">02 / DASHBOARDS</span>
    </div>

    <div class="card-grid">

      <a class="viz-card reveal" href="https://public.tableau.com/app/profile/nadya.divia.go/viz/IPL_Receivable_Dashboard7/Dashboard3BusinessActionDashboard" target="_blank" rel="noopener">
        <div class="viz-thumb" style="--viz-color: linear-gradient(135deg, #12463f, #0e1626);">
          <svg viewBox="0 0 200 100" preserveAspectRatio="none" aria-hidden="true"><polyline points="0,80 25,60 50,70 75,40 100,50 125,25 150,35 175,15 200,20" fill="none" stroke="#2DD4BF" stroke-width="2" opacity="0.7"/></svg>
          <span class="viz-tag">Business Action Dashboard</span>
        </div>
        <div class="viz-body">
          <h3>IPL Receivable Dashboard</h3>
          <p>A receivables tracking dashboard designed to flag outstanding balances and support day-to-day collection decisions.</p>
          <span class="viz-link">Open on Tableau Public <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
        </div>
      </a>

      <a class="viz-card reveal" href="https://public.tableau.com/app/profile/nadya.divia.go/viz/Superstore_dashboard_33/Top10ProfitableProduct" target="_blank" rel="noopener">
        <div class="viz-thumb" style="--viz-color: linear-gradient(135deg, #46370f, #0e1626);">
          <svg viewBox="0 0 200 100" preserveAspectRatio="none" aria-hidden="true"><rect x="10" y="55" width="14" height="30" fill="#F5A524" opacity="0.7"/><rect x="34" y="40" width="14" height="45" fill="#F5A524" opacity="0.7"/><rect x="58" y="25" width="14" height="60" fill="#F5A524" opacity="0.7"/><rect x="82" y="45" width="14" height="40" fill="#F5A524" opacity="0.7"/><rect x="106" y="15" width="14" height="70" fill="#F5A524" opacity="0.7"/></svg>
          <span class="viz-tag">Product Profitability</span>
        </div>
        <div class="viz-body">
          <h3>Superstore Dashboard — Top 10 Profitable Products</h3>
          <p>Ranks the most profitable products from the classic Superstore dataset, highlighting where margin is actually concentrated.</p>
          <span class="viz-link">Open on Tableau Public <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
        </div>
      </a>

      <a class="viz-card reveal" href="https://public.tableau.com/app/profile/nadya.divia.go/viz/tableu_exe/DistributionSalesperRegion" target="_blank" rel="noopener">
        <div class="viz-thumb" style="--viz-color: linear-gradient(135deg, #123a46, #0e1626);">
          <svg viewBox="0 0 200 100" preserveAspectRatio="none" aria-hidden="true"><circle cx="55" cy="50" r="30" fill="none" stroke="#2DD4BF" stroke-width="10" opacity="0.6" stroke-dasharray="60 130"/><circle cx="55" cy="50" r="30" fill="none" stroke="#F5A524" stroke-width="10" opacity="0.55" stroke-dasharray="40 150" stroke-dashoffset="-60"/></svg>
          <span class="viz-tag">Regional Sales</span>
        </div>
        <div class="viz-body">
          <h3>Sales Distribution per Region</h3>
          <p>Breaks down sales performance across regions to surface where demand is strongest and where it's lagging.</p>
          <span class="viz-link">Open on Tableau Public <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
        </div>
      </a>

      <a class="viz-card reveal" href="https://public.tableau.com/app/profile/nadya.divia.go/viz/tableu_exe2/Dashboard1" target="_blank" rel="noopener">
        <div class="viz-thumb" style="--viz-color: linear-gradient(135deg, #1a1f46, #0e1626);">
          <svg viewBox="0 0 200 100" preserveAspectRatio="none" aria-hidden="true"><polyline points="0,60 30,50 60,65 90,35 120,45 150,20 180,30 200,10" fill="none" stroke="#8B96AC" stroke-width="2" opacity="0.5"/><rect x="0" y="80" width="200" height="1" fill="#223050"/></svg>
          <span class="viz-tag">Exploratory Dashboard</span>
        </div>
        <div class="viz-body">
          <h3>Dashboard Exercise 2</h3>
          <p>An exploratory dashboard build focused on practicing chart selection, layout and interactivity in Tableau.</p>
          <span class="viz-link">Open on Tableau Public <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
        </div>
      </a>

    </div>
  </div>
</section>

<section id="projects">
  <div class="wrap">
    <div class="section-head">
      <div>
        <h2>GitHub projects</h2>
        <p class="section-sub">Analysis and machine learning projects — SQL, Python and applied modelling work.</p>
      </div>
      <span class="section-index mono">03 / PROJECTS</span>
    </div>

    <div class="proj-list">

      <a class="proj-row reveal" href="https://github.com/nadya1612/cohort_analysis" target="_blank" rel="noopener">
        <span class="proj-num mono">01</span>
        <div class="proj-name">cohort_analysis<span class="repo-owner">nadya1612</span></div>
        <div class="proj-desc">Cohort-based retention analysis, tracking how customer engagement changes across acquisition groups over time.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

      <a class="proj-row reveal" href="https://github.com/nadya1612/deployment_project" target="_blank" rel="noopener">
        <span class="proj-num mono">02</span>
        <div class="proj-name">deployment_project<span class="repo-owner">nadya1612</span></div>
        <div class="proj-desc">An end-to-end project covering model or app deployment, moving analysis from notebook to a usable interface.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

      <a class="proj-row reveal" href="https://github.com/nadya1612/portfolio" target="_blank" rel="noopener">
        <span class="proj-num mono">03</span>
        <div class="proj-name">portfolio<span class="repo-owner">nadya1612</span></div>
        <div class="proj-desc">Source code and notebooks behind this portfolio's projects and write-ups.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

      <a class="proj-row reveal" href="https://github.com/nadya1612/Penjualan_Bakery_Cafe" target="_blank" rel="noopener">
        <span class="proj-num mono">04</span>
        <div class="proj-name">Penjualan_Bakery_Cafe<span class="repo-owner">nadya1612</span></div>
        <div class="proj-desc">Sales analysis for a bakery/café business, digging into product performance and revenue trends.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

      <a class="proj-row reveal" href="https://github.com/MikaMahaputra/Capstone-2-Sinarmas-Land" target="_blank" rel="noopener">
        <span class="proj-num mono">05</span>
        <div class="proj-name">Capstone-2-Sinarmas-Land<span class="repo-owner">MikaMahaputra (collaborator)</span></div>
        <div class="proj-desc">A capstone analytics project built for Sinarmas Land, applied as part of a team collaboration.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

      <a class="proj-row reveal" href="https://github.com/ElmarLeonard9/Bank_Marketing_Campaign_Analysis_-_ML" target="_blank" rel="noopener">
        <span class="proj-num mono">06</span>
        <div class="proj-name">Bank_Marketing_Campaign_Analysis_-_ML<span class="repo-owner">ElmarLeonard9 (collaborator)</span></div>
        <div class="proj-desc">Machine learning analysis of a bank marketing campaign dataset, predicting customer response to term deposit offers.</div>
        <span class="proj-link">View repo <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg></span>
      </a>

    </div>
  </div>
</section>

<section id="contact">
  <div class="wrap">
    <div class="contact-inner reveal">
      <div>
        <h2>Let's talk about your data.</h2>
        <p class="lede">Open to data analyst roles and freelance dashboard work. Reach out by email or LinkedIn — I usually reply within a day or two.</p>
      </div>
      <div class="contact-links">
        <a class="contact-link" href="mailto:nadya.diviago1612@gmail.com">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16v16H4z"/><path d="M4 4l8 8 8-8"/></svg>
          nadya.diviago1612@gmail.com
        </a>
        <a class="contact-link" href="https://www.linkedin.com/in/nadya-go-22a86041b/" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M8 11v5M8 8v.01M12 16v-5M12 11c0-1.5 1-2 2-2s2 .5 2 2v5"/></svg>
          linkedin.com/in/nadya-go
        </a>
      </div>
    </div>
  </div>
</section>

<footer>
  © 2026 Nadya Divia Go — Data Analyst Portfolio
</footer>

<script>
  const els = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    });
  }, {threshold:0.12});
  els.forEach(el=>io.observe(el));
</script>

</body>
</html>
