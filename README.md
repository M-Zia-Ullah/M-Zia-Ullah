<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Muhammad — AI Full Stack Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c10;
    --surface: #0e1318;
    --surface2: #131a21;
    --border: rgba(255,255,255,0.07);
    --accent: #00e5a0;
    --accent2: #0099ff;
    --text: #e8edf2;
    --muted: #5a6678;
    --soft: #8a96a8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    min-height: 100vh;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,160,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,160,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .page {
    position: relative;
    z-index: 1;
    max-width: 820px;
    margin: 0 auto;
    padding: 60px 24px 80px;
  }

  /* HEADER */
  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding-bottom: 52px;
    border-bottom: 1px solid var(--border);
    animation: fadeUp 0.7s ease both;
  }

  .status-pill {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    background: rgba(0,229,160,0.08);
    border: 1px solid rgba(0,229,160,0.2);
    color: var(--accent);
    font-size: 11.5px;
    font-weight: 500;
    letter-spacing: 0.8px;
    text-transform: uppercase;
    padding: 5px 14px;
    border-radius: 100px;
    margin-bottom: 26px;
  }
  .status-pill::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    box-shadow: 0 0 8px var(--accent);
    animation: pulse 2s infinite;
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 5vw, 3.2rem);
    font-weight: 800;
    letter-spacing: -1px;
    line-height: 1.1;
    color: #fff;
    margin-bottom: 12px;
  }
  h1 span {
    background: linear-gradient(120deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .roles {
    font-size: 13px;
    font-weight: 300;
    color: var(--soft);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 18px;
  }

  .tagline {
    font-size: 15px;
    font-style: italic;
    color: var(--soft);
    margin-bottom: 28px;
    max-width: 500px;
  }

  .cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--accent);
    color: #000;
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 0.5px;
    padding: 12px 26px;
    border-radius: 6px;
    text-decoration: none;
    transition: all 0.2s;
    box-shadow: 0 0 24px rgba(0,229,160,0.25);
  }
  .cta-btn:hover {
    background: #fff;
    box-shadow: 0 0 36px rgba(0,229,160,0.4);
    transform: translateY(-1px);
  }

  /* SECTIONS */
  section {
    margin-top: 52px;
    animation: fadeUp 0.7s ease both;
  }
  section:nth-of-type(1) { animation-delay: 0.1s; }
  section:nth-of-type(2) { animation-delay: 0.2s; }
  section:nth-of-type(3) { animation-delay: 0.3s; }

  .section-label {
    font-family: 'Syne', sans-serif;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
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

  /* ABOUT */
  .about-text {
    color: var(--soft);
    font-size: 15px;
    line-height: 1.8;
    margin-bottom: 28px;
    max-width: 680px;
  }
  .about-text strong { color: var(--text); font-weight: 500; }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 12px;
  }
  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 18px;
    display: flex;
    gap: 12px;
    align-items: flex-start;
    transition: border-color 0.2s, transform 0.2s;
  }
  .stat-card:hover {
    border-color: rgba(0,229,160,0.25);
    transform: translateY(-2px);
  }
  .stat-icon { font-size: 18px; line-height: 1; margin-top: 2px; flex-shrink: 0; }
  .stat-text { font-size: 13px; color: var(--soft); line-height: 1.5; }
  .stat-text strong { display: block; color: var(--text); font-weight: 500; font-size: 13px; margin-bottom: 2px; }

  /* TECH STACK */
  .stack-group { margin-bottom: 20px; }
  .stack-group-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 10px;
  }
  .pill-row { display: flex; flex-wrap: wrap; gap: 7px; }
  .pill {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 5px 13px;
    border-radius: 4px;
    font-size: 12px;
    font-weight: 500;
    border: 1px solid transparent;
    transition: all 0.2s;
    cursor: default;
  }
  .pill:hover { transform: translateY(-1px); filter: brightness(1.2); }
  .pill-dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }

  /* WHAT I BUILD */
  .build-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  @media (max-width: 560px) { .build-grid { grid-template-columns: 1fr; } }

  .build-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .build-card:hover {
    border-color: rgba(0,153,255,0.3);
    transform: translateY(-2px);
  }
  .build-card-title {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: var(--accent2);
    margin-bottom: 7px;
  }
  .build-card-body {
    font-size: 12.5px;
    color: var(--soft);
    line-height: 1.6;
  }

  /* FOOTER */
  .footer {
    margin-top: 64px;
    padding-top: 40px;
    border-top: 1px solid var(--border);
    text-align: center;
    animation: fadeUp 0.7s ease 0.4s both;
  }
  .footer p {
    font-style: italic;
    color: var(--muted);
    font-size: 13px;
    margin-bottom: 20px;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }
</style>
</head>
<body>
<div class="page">

  <header class="header">
    <div class="status-pill">Available for hire</div>
    <h1>Muhammad <span>Zia Ul Haq</span></h1>
    <div class="roles">AI Full Stack Engineer &nbsp;·&nbsp; SaaS Architect &nbsp;·&nbsp; LLM Integration Specialist</div>
    <p class="tagline">Shipping AI-powered products that actually work — on time, on budget, with clean code.</p>
    <a href="https://www.upwork.com/freelancers/muhammadziau4" target="_blank" class="cta-btn">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M18.561 13.158c-1.102 0-2.135-.467-3.074-1.227l.228-1.076.008-.042c.207-1.143.849-3.06 2.839-3.06 1.492 0 2.703 1.212 2.703 2.703-.001 1.489-1.212 2.702-2.704 2.702zm0-8.14c-2.539 0-4.51 1.649-5.31 4.366-1.22-1.834-2.148-4.036-2.687-5.892H7.828v7.112c-.002 1.406-1.141 2.546-2.547 2.546-1.405 0-2.543-1.14-2.543-2.546V3.492H0v7.112c0 2.914 2.37 5.303 5.281 5.303 2.913 0 5.283-2.389 5.283-5.303v-1.19c.529 1.107 1.182 2.229 1.974 3.221l-1.673 7.873h2.797l1.213-5.71c1.063.679 2.285 1.109 3.686 1.109 3 0 5.439-2.452 5.439-5.45 0-3-2.439-5.439-5.439-5.439z"/></svg>
      Hire me on Upwork
    </a>
  </header>

  <section>
    <div class="section-label">About</div>
    <p class="about-text">
      I'm a full-stack AI engineer specializing in SaaS products and intelligent systems. I take projects from idea to deployed product — architecting clean, scalable backends, integrating LLMs into real workflows, and building frontends that users actually enjoy.<br/><br/>
      Most developers ship code. I ship <strong>outcomes</strong>. I'm obsessed with the last 20% — the polish, edge cases, and architectural decisions most developers skip.
    </p>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-icon">🤖</div>
        <div class="stat-text"><strong>Multi-agent AI system</strong>LangChain + RAG + AWS — live in under 3 weeks</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon">📉</div>
        <div class="stat-text"><strong>70% faster ticket resolution</strong>AI support dashboard with NextJS + NestJS + OpenAI</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon">⚙️</div>
        <div class="stat-text"><strong>80% less manual ops</strong>eCommerce automation platform built end-to-end</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon">🔌</div>
        <div class="stat-text"><strong>10+ production integrations</strong>Stripe, Firebase, Twilio, PostgreSQL — zero downtime</div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-label">Tech Stack</div>

    <div class="stack-group">
      <div class="stack-group-label">Frontend</div>
      <div class="pill-row">
        <span class="pill" style="background:rgba(255,255,255,0.05);color:#e6edf3;border-color:rgba(255,255,255,0.1)"><span class="pill-dot" style="background:#fff"></span>Next.js</span>
        <span class="pill" style="background:rgba(97,218,251,0.08);color:#61DAFB;border-color:rgba(97,218,251,0.2)"><span class="pill-dot" style="background:#61DAFB"></span>React</span>
        <span class="pill" style="background:rgba(49,120,198,0.12);color:#7EB9FF;border-color:rgba(49,120,198,0.3)"><span class="pill-dot" style="background:#3178C6"></span>TypeScript</span>
        <span class="pill" style="background:rgba(6,182,212,0.1);color:#67E8F9;border-color:rgba(6,182,212,0.25)"><span class="pill-dot" style="background:#06B6D4"></span>Tailwind CSS</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Backend</div>
      <div class="pill-row">
        <span class="pill" style="background:rgba(51,153,51,0.1);color:#86EFAC;border-color:rgba(51,153,51,0.25)"><span class="pill-dot" style="background:#339933"></span>Node.js</span>
        <span class="pill" style="background:rgba(224,35,78,0.1);color:#FDA4AF;border-color:rgba(224,35,78,0.25)"><span class="pill-dot" style="background:#E0234E"></span>NestJS</span>
        <span class="pill" style="background:rgba(55,118,171,0.1);color:#93C5FD;border-color:rgba(55,118,171,0.25)"><span class="pill-dot" style="background:#3776AB"></span>Python</span>
        <span class="pill" style="background:rgba(0,150,136,0.1);color:#6EE7B7;border-color:rgba(0,150,136,0.25)"><span class="pill-dot" style="background:#009688"></span>FastAPI</span>
        <span class="pill" style="background:rgba(9,46,32,0.35);color:#86EFAC;border-color:rgba(46,204,113,0.2)"><span class="pill-dot" style="background:#2ECC71"></span>Django</span>
        <span class="pill" style="background:rgba(225,0,152,0.1);color:#F9A8D4;border-color:rgba(225,0,152,0.25)"><span class="pill-dot" style="background:#E10098"></span>GraphQL</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">AI & ML</div>
      <div class="pill-row">
        <span class="pill" style="background:rgba(65,41,145,0.15);color:#C4B5FD;border-color:rgba(65,41,145,0.35)"><span class="pill-dot" style="background:#412991"></span>OpenAI</span>
        <span class="pill" style="background:rgba(28,60,60,0.4);color:#6EE7B7;border-color:rgba(0,229,160,0.2)"><span class="pill-dot" style="background:#00e5a0"></span>LangChain</span>
        <span class="pill" style="background:rgba(255,111,0,0.1);color:#FED7AA;border-color:rgba(255,111,0,0.25)"><span class="pill-dot" style="background:#FF6F00"></span>TensorFlow</span>
        <span class="pill" style="background:rgba(238,76,44,0.1);color:#FCA5A5;border-color:rgba(238,76,44,0.25)"><span class="pill-dot" style="background:#EE4C2C"></span>PyTorch</span>
        <span class="pill" style="background:rgba(255,210,30,0.08);color:#FDE68A;border-color:rgba(255,210,30,0.2)"><span class="pill-dot" style="background:#FFD21E"></span>Hugging Face</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Database</div>
      <div class="pill-row">
        <span class="pill" style="background:rgba(65,105,225,0.1);color:#93C5FD;border-color:rgba(65,105,225,0.25)"><span class="pill-dot" style="background:#4169E1"></span>PostgreSQL</span>
        <span class="pill" style="background:rgba(71,162,72,0.1);color:#86EFAC;border-color:rgba(71,162,72,0.25)"><span class="pill-dot" style="background:#47A248"></span>MongoDB</span>
        <span class="pill" style="background:rgba(68,121,161,0.1);color:#93C5FD;border-color:rgba(68,121,161,0.25)"><span class="pill-dot" style="background:#4479A1"></span>MySQL</span>
        <span class="pill" style="background:rgba(255,202,40,0.08);color:#FDE68A;border-color:rgba(255,202,40,0.2)"><span class="pill-dot" style="background:#FFCA28"></span>Firebase</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-label">Cloud & DevOps</div>
      <div class="pill-row">
        <span class="pill" style="background:rgba(255,153,0,0.08);color:#FCD34D;border-color:rgba(255,153,0,0.2)"><span class="pill-dot" style="background:#FF9900"></span>AWS</span>
        <span class="pill" style="background:rgba(36,150,237,0.1);color:#7DD3FC;border-color:rgba(36,150,237,0.25)"><span class="pill-dot" style="background:#2496ED"></span>Docker</span>
        <span class="pill" style="background:rgba(50,108,229,0.1);color:#93C5FD;border-color:rgba(50,108,229,0.25)"><span class="pill-dot" style="background:#326CE5"></span>Kubernetes</span>
        <span class="pill" style="background:rgba(0,150,57,0.1);color:#86EFAC;border-color:rgba(0,150,57,0.25)"><span class="pill-dot" style="background:#009639"></span>Nginx</span>
      </div>
    </div>
  </section>

  <section>
    <div class="section-label">What I Build</div>
    <div class="build-grid">
      <div class="build-card">
        <div class="build-card-title">AI Agents</div>
        <div class="build-card-body">Multi-agent systems, RAG pipelines, LLM fine-tuning, autonomous task execution</div>
      </div>
      <div class="build-card">
        <div class="build-card-title">SaaS MVPs</div>
        <div class="build-card-body">End-to-end product development, multi-tenant architecture, subscription billing</div>
      </div>
      <div class="build-card">
        <div class="build-card-title">AI Integration</div>
        <div class="build-card-body">GPT / Claude / Gemini APIs, LangChain, intelligent backends, NLP features</div>
      </div>
      <div class="build-card">
        <div class="build-card-title">Full Stack Apps</div>
        <div class="build-card-body">REST & GraphQL APIs, real-time systems, cloud-native microservices</div>
      </div>
      <div class="build-card">
        <div class="build-card-title">Automation</div>
        <div class="build-card-body">Workflow automation, data pipelines, intelligent operations at scale</div>
      </div>
    </div>
  </section>

  <div class="footer">
    <p>Building something? Let's talk.</p>
    <a href="https://www.upwork.com/freelancers/muhammadziau4" target="_blank" class="cta-btn">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M18.561 13.158c-1.102 0-2.135-.467-3.074-1.227l.228-1.076.008-.042c.207-1.143.849-3.06 2.839-3.06 1.492 0 2.703 1.212 2.703 2.703-.001 1.489-1.212 2.702-2.704 2.702zm0-8.14c-2.539 0-4.51 1.649-5.31 4.366-1.22-1.834-2.148-4.036-2.687-5.892H7.828v7.112c-.002 1.406-1.141 2.546-2.547 2.546-1.405 0-2.543-1.14-2.543-2.546V3.492H0v7.112c0 2.914 2.37 5.303 5.281 5.303 2.913 0 5.283-2.389 5.283-5.303v-1.19c.529 1.107 1.182 2.229 1.974 3.221l-1.673 7.873h2.797l1.213-5.71c1.063.679 2.285 1.109 3.686 1.109 3 0 5.439-2.452 5.439-5.45 0-3-2.439-5.439-5.439-5.439z"/></svg>
      Hire me on Upwork
    </a>
  </div>

</div>
</body>
</html> 
