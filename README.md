

<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Inter:wght@300;400;500;600;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .rm-root {
    font-family: 'Inter', sans-serif;
    background: #0d1117;
    color: #e6edf3;
    min-height: 100vh;
    padding-bottom: 3rem;
    overflow: hidden;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    padding: 3rem 2rem 2.5rem;
    text-align: center;
    overflow: hidden;
    min-height: 380px;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #0d1117 0%, #0f1e38 50%, #0d1117 100%);
    z-index: 0;
  }
  .grid-lines {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(30,215,96,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(30,215,96,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    z-index: 1;
    animation: gridShift 20s linear infinite;
  }
  @keyframes gridShift { 0% { background-position: 0 0; } 100% { background-position: 40px 40px; } }
  .scanline {
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, rgba(30,215,96,0.6), transparent);
    animation: scan 4s ease-in-out infinite;
    z-index: 2;
  }
  @keyframes scan {
    0%, 100% { top: 0; opacity: 0; } 10% { opacity: 1; } 90% { opacity: 1; } 50% { top: 100%; }
  }
  .hero-inner { position: relative; z-index: 3; }

  /* ── FLOATING ROBOTS ── */
  .bot {
    position: absolute;
    z-index: 4;
    animation: floatBot 4.5s ease-in-out infinite;
    opacity: 0.92;
  }
  .bot1 { top: 14%; left: 6%; width: 46px; animation-delay: 0s; }
  .bot2 { top: 18%; right: 7%; width: 40px; animation-delay: 0.8s; animation-duration: 5.2s; }
  .bot3 { bottom: 10%; left: 11%; width: 34px; animation-delay: 1.6s; animation-duration: 4s; }
  .bot4 { bottom: 8%; right: 12%; width: 38px; animation-delay: 2.2s; animation-duration: 4.8s; }
  @keyframes floatBot {
    0%, 100% { transform: translateY(0px) rotate(-2deg); }
    50% { transform: translateY(-14px) rotate(2deg); }
  }
  .bot-eye { animation: blinkEye 3s ease-in-out infinite; }
  @keyframes blinkEye {
    0%, 92%, 100% { opacity: 1; } 95% { opacity: 0.15; }
  }
  .bot-antenna-tip { animation: pulseTip 1.6s ease-in-out infinite; }
  @keyframes pulseTip {
    0%, 100% { opacity: 0.5; r: 2.5; } 50% { opacity: 1; r: 3.5; }
  }

  .avatar-ring {
    display: inline-block; width: 90px; height: 90px; border-radius: 50%;
    background: linear-gradient(135deg, #1ed760, #0072ff, #ff6b6b);
    padding: 3px; animation: spin-ring 8s linear infinite; margin-bottom: 1rem;
  }
  @keyframes spin-ring { 0% { filter: hue-rotate(0deg); } 100% { filter: hue-rotate(360deg); } }
  .avatar-inner {
    width: 100%; height: 100%; border-radius: 50%; background: #0d1117;
    display: flex; align-items: center; justify-content: center; font-size: 2.2rem;
  }

  .hero-name {
    font-size: 2.4rem; font-weight: 700;
    background: linear-gradient(90deg, #1ed760, #00c6ff, #e040fb);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    letter-spacing: -0.5px; margin-bottom: 0.5rem;
    animation: shimmer 3s ease infinite; background-size: 200%;
  }
  @keyframes shimmer { 0%, 100% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } }

  .typing-wrap { height: 32px; display: flex; align-items: center; justify-content: center; margin-bottom: 1.2rem; }
  .typing-text {
    font-family: 'Fira Code', monospace; font-size: 1rem; color: #1ed760;
    border-right: 2px solid #1ed760; white-space: nowrap; overflow: hidden;
    animation: blink-cursor 0.75s step-end infinite;
  }
  @keyframes blink-cursor { 0%, 100% { border-color: #1ed760; } 50% { border-color: transparent; } }

  .badge-row { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 1.5rem; }
  .badge {
    font-family: 'Fira Code', monospace; font-size: 0.72rem; padding: 4px 12px;
    border-radius: 20px; border: 1px solid; letter-spacing: 0.02em;
  }
  .badge-green { color: #1ed760; border-color: #1ed760; background: rgba(30,215,96,0.08); }
  .badge-blue  { color: #58a6ff; border-color: #58a6ff; background: rgba(88,166,255,0.08); }
  .badge-purple{ color: #bc8cff; border-color: #bc8cff; background: rgba(188,140,255,0.08); }
  .badge-orange{ color: #ffa657; border-color: #ffa657; background: rgba(255,166,87,0.08); }

  /* ── SECTIONS ── */
  .section { max-width: 680px; margin: 0 auto; padding: 0 1.5rem; }
  .sec-header {
    display: flex; align-items: center; gap: 10px; margin: 2rem 0 1rem;
    padding-bottom: 8px; border-bottom: 1px solid rgba(48,54,61,0.8);
  }
  .sec-icon { font-size: 1.1rem; }
  .sec-title {
    font-family: 'Fira Code', monospace; font-size: 0.9rem; color: #8b949e;
    text-transform: uppercase; letter-spacing: 0.1em;
  }
  .sec-line { flex: 1; height: 1px; background: linear-gradient(90deg, rgba(48,54,61,0.6), transparent); }

  /* ── ADVANCED PROFILE TERMINAL ── */
  .terminal {
    background: #0a0e14;
    border: 1px solid #30363d;
    border-radius: 10px;
    overflow: hidden;
  }
  .term-bar {
    display: flex; align-items: center; gap: 6px;
    padding: 8px 12px; background: #161b22; border-bottom: 1px solid #21262d;
  }
  .term-dot { width: 10px; height: 10px; border-radius: 50%; }
  .term-label {
    margin-left: 8px; font-family: 'Fira Code', monospace; font-size: 0.7rem; color: #6e7681;
  }
  .term-body { padding: 1rem 1.2rem; font-family: 'Fira Code', monospace; font-size: 0.78rem; line-height: 1.8; }
  .term-key { color: #bc8cff; }
  .term-str { color: #a5d6ff; }
  .term-comment { color: #6e7681; }
  .term-bracket { color: #e6edf3; }
  .term-cursor-line { display: inline-block; width: 7px; height: 14px; background: #1ed760; animation: blink-cursor 0.9s step-end infinite; vertical-align: -2px; }

  /* ── SKILL METERS ── */
  .skill-row { display: flex; align-items: center; gap: 10px; margin-bottom: 10px; }
  .skill-name { font-size: 0.78rem; color: #c9d1d9; min-width: 150px; font-family: 'Fira Code', monospace; }
  .skill-track { flex: 1; height: 6px; background: #21262d; border-radius: 4px; overflow: hidden; }
  .skill-fill { height: 100%; border-radius: 4px; width: 0%; transition: width 1.4s ease; }
  .skill-pct { font-size: 0.7rem; color: #8b949e; min-width: 36px; text-align: right; font-family: 'Fira Code', monospace; }

  /* ── CARDS ── */
  .card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .card {
    background: #161b22; border: 1px solid #30363d; border-radius: 10px;
    padding: 1rem 1.1rem; transition: border-color 0.2s, transform 0.2s; cursor: default;
  }
  .card:hover { border-color: #58a6ff; transform: translateY(-2px); }
  .card-title { font-family: 'Fira Code', monospace; font-size: 0.82rem; font-weight: 600; margin-bottom: 0.5rem; }
  .card-items { list-style: none; }
  .card-items li {
    font-size: 0.78rem; color: #8b949e; padding: 2px 0; display: flex; align-items: baseline; gap: 6px;
  }
  .card-items li::before { content: '▸'; color: #1ed760; font-size: 0.65rem; flex-shrink: 0; }

  /* ── TECH STACK ── */
  .tech-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-pill {
    font-family: 'Fira Code', monospace; font-size: 0.72rem; padding: 5px 12px; border-radius: 6px;
    background: #161b22; border: 1px solid #30363d; color: #c9d1d9;
    display: flex; align-items: center; gap: 6px; transition: all 0.2s;
  }
  .tech-pill:hover { border-color: #1ed760; color: #1ed760; transform: scale(1.04); }
  .tech-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }

  /* ── STAT CARDS ── */
  .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .stat-card {
    background: #161b22; border: 1px solid #30363d; border-radius: 10px;
    padding: 1.1rem; text-align: center; position: relative; overflow: hidden;
  }
  .stat-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; }
  .stat-card.green::before { background: linear-gradient(90deg, #1ed760, transparent); }
  .stat-card.blue::before  { background: linear-gradient(90deg, #58a6ff, transparent); }
  .stat-card.purple::before { background: linear-gradient(90deg, #bc8cff, transparent); }
  .stat-card.orange::before { background: linear-gradient(90deg, #ffa657, transparent); }
  .stat-num { font-size: 1.8rem; font-weight: 700; font-family: 'Fira Code', monospace; line-height: 1; margin-bottom: 4px; }
  .stat-label { font-size: 0.72rem; color: #8b949e; letter-spacing: 0.05em; }

  /* ── ROBOT BUILD LAB ── */
  .lab-wrap {
    background: #161b22; border: 1px solid #30363d; border-radius: 10px;
    padding: 1.2rem; display: flex; align-items: center; gap: 1.5rem;
  }
  .lab-bot-stage { width: 100px; height: 100px; flex-shrink: 0; position: relative; }
  .lab-text { flex: 1; }
  .lab-text-title { font-family: 'Fira Code', monospace; font-size: 0.85rem; color: #1ed760; margin-bottom: 6px; }
  .lab-text-sub { font-size: 0.78rem; color: #8b949e; line-height: 1.6; }
  .gear-spin { animation: gearSpin 6s linear infinite; transform-origin: center; }
  @keyframes gearSpin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
  .gear-spin-rev { animation: gearSpinRev 5s linear infinite; transform-origin: center; }
  @keyframes gearSpinRev { from { transform: rotate(360deg); } to { transform: rotate(0deg); } }

  /* ── CONTRIBUTION GRID ── */
  .contrib-grid { display: grid; grid-template-columns: repeat(52, 1fr); gap: 3px; margin-top: 0.5rem; }
  .contrib-cell { aspect-ratio: 1; border-radius: 2px; background: #161b22; transition: transform 0.1s; }
  .contrib-cell:hover { transform: scale(1.4); }

  /* ── LINKS ── */
  .links-row { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 0.5rem; }
  .link-card {
    flex: 1; min-width: 130px; background: #161b22; border: 1px solid #30363d; border-radius: 8px;
    padding: 0.8rem 1rem; display: flex; align-items: center; gap: 10px;
    text-decoration: none; transition: all 0.2s; cursor: pointer;
  }
  .link-card:hover { border-color: #58a6ff; background: #1c2128; }
  .link-icon { font-size: 1.2rem; }
  .link-label { font-size: 0.8rem; font-weight: 500; color: #c9d1d9; }
  .link-sub { font-size: 0.68rem; color: #8b949e; }

  /* ── COLLAB ── */
  .collab-list { display: flex; flex-direction: column; gap: 8px; }
  .collab-item {
    background: #161b22; border: 1px solid #30363d; border-left: 3px solid #1ed760;
    border-radius: 0 8px 8px 0; padding: 0.65rem 1rem; font-size: 0.8rem; color: #c9d1d9;
    display: flex; align-items: center; gap: 10px; transition: background 0.2s;
  }
  .collab-item:hover { background: #1c2128; }
  .collab-num { font-family: 'Fira Code', monospace; font-size: 0.68rem; color: #1ed760; min-width: 24px; }

  /* ── FOOTER ── */
  .footer { text-align: center; margin-top: 2.5rem; padding: 1.5rem; border-top: 1px solid #21262d; }
  .footer-text { font-family: 'Fira Code', monospace; font-size: 0.75rem; color: #484f58; }
  .footer-text span { color: #1ed760; }
</style>

<div class="rm-root">
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="grid-lines"></div>
    <div class="scanline"></div>

    <svg class="bot bot1" viewBox="0 0 60 60"><circle class="bot-antenna-tip" cx="30" cy="6" r="3" fill="#1ed760"/><line x1="30" y1="9" x2="30" y2="16" stroke="#1ed760" stroke-width="2"/><rect x="14" y="16" width="32" height="26" rx="6" fill="#161b22" stroke="#1ed760" stroke-width="1.5"/><circle class="bot-eye" cx="23" cy="28" r="4" fill="#1ed760"/><circle class="bot-eye" cx="37" cy="28" r="4" fill="#1ed760"/><rect x="20" y="36" width="20" height="3" rx="1.5" fill="#1ed760" opacity="0.5"/><rect x="6" y="22" width="6" height="14" rx="3" fill="#161b22" stroke="#1ed760" stroke-width="1.5"/><rect x="48" y="22" width="6" height="14" rx="3" fill="#161b22" stroke="#1ed760" stroke-width="1.5"/><rect x="18" y="42" width="8" height="10" rx="3" fill="#161b22" stroke="#1ed760" stroke-width="1.5"/><rect x="34" y="42" width="8" height="10" rx="3" fill="#161b22" stroke="#1ed760" stroke-width="1.5"/></svg>

    <svg class="bot bot2" viewBox="0 0 60 60"><circle class="bot-antenna-tip" cx="30" cy="5" r="3" fill="#58a6ff"/><line x1="30" y1="8" x2="30" y2="15" stroke="#58a6ff" stroke-width="2"/><circle cx="30" cy="30" r="18" fill="#161b22" stroke="#58a6ff" stroke-width="1.5"/><circle class="bot-eye" cx="23" cy="28" r="3.5" fill="#58a6ff"/><circle class="bot-eye" cx="37" cy="28" r="3.5" fill="#58a6ff"/><path d="M21 37 Q30 42 39 37" stroke="#58a6ff" stroke-width="1.8" fill="none" stroke-linecap="round"/><rect x="4" y="26" width="5" height="10" rx="2.5" fill="#161b22" stroke="#58a6ff" stroke-width="1.5"/><rect x="51" y="26" width="5" height="10" rx="2.5" fill="#161b22" stroke="#58a6ff" stroke-width="1.5"/></svg>

    <svg class="bot bot3" viewBox="0 0 60 60"><line x1="30" y1="10" x2="30" y2="17" stroke="#bc8cff" stroke-width="2"/><circle class="bot-antenna-tip" cx="30" cy="7" r="2.5" fill="#bc8cff"/><rect x="16" y="17" width="28" height="24" rx="8" fill="#161b22" stroke="#bc8cff" stroke-width="1.5"/><circle class="bot-eye" cx="24" cy="28" r="3" fill="#bc8cff"/><circle class="bot-eye" cx="36" cy="28" r="3" fill="#bc8cff"/><rect x="8" y="40" width="44" height="6" rx="3" fill="#161b22" stroke="#bc8cff" stroke-width="1.5"/></svg>

    <svg class="bot bot4" viewBox="0 0 60 60"><rect x="12" y="14" width="36" height="30" rx="5" fill="#161b22" stroke="#ffa657" stroke-width="1.5"/><circle class="bot-antenna-tip" cx="20" cy="8" r="2.5" fill="#ffa657"/><circle class="bot-antenna-tip" cx="40" cy="8" r="2.5" fill="#ffa657"/><line x1="20" y1="10" x2="20" y2="14" stroke="#ffa657" stroke-width="2"/><line x1="40" y1="10" x2="40" y2="14" stroke="#ffa657" stroke-width="2"/><rect class="bot-eye" x="18" y="24" width="8" height="6" rx="2" fill="#ffa657"/><rect class="bot-eye" x="34" y="24" width="8" height="6" rx="2" fill="#ffa657"/><rect x="22" y="36" width="16" height="3" rx="1.5" fill="#ffa657" opacity="0.6"/></svg>

    <div class="hero-inner">
      <div class="avatar-ring"><div class="avatar-inner">🤖</div></div>
      <div class="hero-name">Hi, I'm Ramani 👋</div>
      <div class="typing-wrap"><div class="typing-text" id="typer"></div></div>
      <div class="badge-row">
        <span class="badge badge-green">🤖 AI Engineer</span>
        <span class="badge badge-blue">🛡️ Security Engineer</span>
        <span class="badge badge-purple">🧠 Agent Orchestration</span>
        <span class="badge badge-orange">🚀 Forward Deployed</span>
      </div>
    </div>
  </div>

  <div class="section">

    <div class="sec-header"><span class="sec-icon">⚡</span><span class="sec-title">about.md</span><div class="sec-line"></div></div>
    <p style="font-size:0.85rem; color:#8b949e; line-height:1.7; border-left:2px solid #1ed760; padding-left:12px; font-family:'Fira Code',monospace;">
      I build production-grade AI systems that go beyond APIs — specializing in agent orchestration, LLM workflows, and real-world deployment of AI solutions at the intersection of intelligence and security.
    </p>

    <!-- ADVANCED PROFILE TERMINAL -->
    <div class="sec-header"><span class="sec-icon">🧬</span><span class="sec-title">advanced_profile.json</span><div class="sec-line"></div></div>
    <div class="terminal">
      <div class="term-bar">
        <div class="term-dot" style="background:#ff5f56;"></div>
        <div class="term-dot" style="background:#ffbd2e;"></div>
        <div class="term-dot" style="background:#27c93f;"></div>
        <span class="term-label">ramani@ai-engineer ~ %</span>
      </div>
      <div class="term-body">
        <span class="term-bracket">{</span><br>
        &nbsp;&nbsp;<span class="term-key">"role"</span>: <span class="term-str">"Advanced AI Systems Engineer"</span>,<br>
        &nbsp;&nbsp;<span class="term-key">"specialization"</span>: <span class="term-str">"Multi-agent orchestration & secure deployment"</span>,<br>
        &nbsp;&nbsp;<span class="term-key">"architecture_focus"</span>: [<span class="term-str">"planner-executor-critic"</span>, <span class="term-str">"swarm agents"</span>, <span class="term-str">"RAG+eval"</span>],<br>
        &nbsp;&nbsp;<span class="term-key">"deployment_mode"</span>: <span class="term-str">"prototype → production, on-site"</span>,<br>
        &nbsp;&nbsp;<span class="term-key">"security_layer"</span>: <span class="term-str">"threat-modeled, sandboxed, red-teamed"</span>,<br>
        &nbsp;&nbsp;<span class="term-key">"status"</span>: <span class="term-str">"actively building autonomous systems"</span><span class="term-cursor-line"></span><br>
        <span class="term-bracket">}</span>
      </div>
    </div>

    <!-- SKILL METERS -->
    <div class="sec-header"><span class="sec-icon">📡</span><span class="sec-title">core_competencies.sys</span><div class="sec-line"></div></div>
    <div id="skills-block">
      <div class="skill-row"><span class="skill-name">Agent orchestration</span><div class="skill-track"><div class="skill-fill" data-pct="96" style="background:#1ed760;"></div></div><span class="skill-pct">96%</span></div>
      <div class="skill-row"><span class="skill-name">LLM application eng</span><div class="skill-track"><div class="skill-fill" data-pct="93" style="background:#58a6ff;"></div></div><span class="skill-pct">93%</span></div>
      <div class="skill-row"><span class="skill-name">AI security / red-team</span><div class="skill-track"><div class="skill-fill" data-pct="90" style="background:#bc8cff;"></div></div><span class="skill-pct">90%</span></div>
      <div class="skill-row"><span class="skill-name">Forward deployment</span><div class="skill-track"><div class="skill-fill" data-pct="88" style="background:#ffa657;"></div></div><span class="skill-pct">88%</span></div>
      <div class="skill-row"><span class="skill-name">RAG & retrieval systems</span><div class="skill-track"><div class="skill-fill" data-pct="91" style="background:#f778ba;"></div></div><span class="skill-pct">91%</span></div>
    </div>

    <!-- WHAT I BUILD -->
    <div class="sec-header"><span class="sec-icon">🧠</span><span class="sec-title">what_i_build.ts</span><div class="sec-line"></div></div>
    <div class="card-grid">
      <div class="card">
        <div class="card-title" style="color:#1ed760;">🤖 Agentic AI Systems</div>
        <ul class="card-items">
          <li>Multi-agent orchestration pipelines</li>
          <li>Tool-using autonomous agents</li>
          <li>Memory + context-aware agents</li>
          <li>Human-in-the-loop AI</li>
          <li>Long-running agent workflows</li>
        </ul>
      </div>
      <div class="card">
        <div class="card-title" style="color:#58a6ff;">⚙️ LLM Orchestration</div>
        <ul class="card-items">
          <li>RAG pipelines with eval loops</li>
          <li>LangGraph state machines</li>
          <li>Prompt routing & tool selection</li>
          <li>LLM chaining & workflow graphs</li>
          <li>Observability for LLM outputs</li>
        </ul>
      </div>
      <div class="card">
        <div class="card-title" style="color:#bc8cff;">🛡️ Security Engineering</div>
        <ul class="card-items">
          <li>AI system threat modeling</li>
          <li>Prompt injection defenses</li>
          <li>Red-teaming LLM applications</li>
          <li>Secure agent sandboxing</li>
          <li>Access control for AI tools</li>
        </ul>
      </div>
      <div class="card">
        <div class="card-title" style="color:#ffa657;">🚀 Forward Deployed (FDE)</div>
        <ul class="card-items">
          <li>Custom AI for real workflows</li>
          <li>Rapid proto → production</li>
          <li>Enterprise API integrations</li>
          <li>Workflow automation (CRM, docs)</li>
          <li>On-site AI problem solving</li>
        </ul>
      </div>
    </div>

    <!-- ROBOT BUILD LAB -->
    <div class="sec-header"><span class="sec-icon">🦾</span><span class="sec-title">build_lab.live</span><div class="sec-line"></div></div>
    <div class="lab-wrap">
      <svg class="lab-bot-stage" viewBox="0 0 100 100">
        <g class="gear-spin" opacity="0.18"><path d="M50 30 L54 30 L55 36 L60 38 L65 34 L68 37 L64 42 L66 47 L72 48 L72 52 L66 53 L64 58 L68 63 L65 66 L60 62 L55 64 L54 70 L50 70 L49 64 L44 62 L39 66 L36 63 L40 58 L38 53 L32 52 L32 48 L38 47 L40 42 L36 37 L39 34 L44 38 L49 36 Z" fill="#1ed760"/></g>
        <rect x="32" y="34" width="36" height="32" rx="7" fill="#0d1117" stroke="#1ed760" stroke-width="1.6"/>
        <circle class="bot-eye" cx="42" cy="48" r="4" fill="#1ed760"/>
        <circle class="bot-eye" cx="58" cy="48" r="4" fill="#1ed760"/>
        <rect x="40" y="58" width="20" height="3" rx="1.5" fill="#1ed760" opacity="0.6"/>
        <line x1="50" y1="34" x2="50" y2="26" stroke="#1ed760" stroke-width="2"/>
        <circle class="bot-antenna-tip" cx="50" cy="23" r="3" fill="#1ed760"/>
        <rect x="20" y="42" width="8" height="16" rx="4" fill="#0d1117" stroke="#1ed760" stroke-width="1.6"/>
        <rect x="72" y="42" width="8" height="16" rx="4" fill="#0d1117" stroke="#1ed760" stroke-width="1.6"/>
      </svg>
      <div class="lab-text">
        <div class="lab-text-title">$ deploying autonomous agents...</div>
        <div class="lab-text-sub">Every system I ship is wired for memory, tool use, and self-correction — built like a teammate, not a script.</div>
      </div>
    </div>

    <!-- TECH STACK -->
    <div class="sec-header"><span class="sec-icon">🔧</span><span class="sec-title">tech_stack.json</span><div class="sec-line"></div></div>
    <div class="tech-grid">
      <div class="tech-pill"><div class="tech-dot" style="background:#f7df1e"></div>Python</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#007acc"></div>TypeScript</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#ff6f00"></div>LangGraph</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#00acd7"></div>LangChain</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#1ed760"></div>Claude API</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#74aa9c"></div>OpenAI</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#ff9900"></div>AWS</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#4285f4"></div>GCP</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#326ce5"></div>Kubernetes</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#0db7ed"></div>Docker</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#f05032"></div>Git</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#ff4154"></div>FastAPI</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#009688"></div>Pinecone</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#e74c3c"></div>Redis</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#336791"></div>PostgreSQL</div>
      <div class="tech-pill"><div class="tech-dot" style="background:#bc8cff"></div>MCP Protocol</div>
    </div>

    <!-- STATS -->
    <div class="sec-header"><span class="sec-icon">📊</span><span class="sec-title">stats.live</span><div class="sec-line"></div></div>
    <div class="stat-grid">
      <div class="stat-card green"><div class="stat-num" style="color:#1ed760;" id="commits">0</div><div class="stat-label">TOTAL COMMITS</div></div>
      <div class="stat-card blue"><div class="stat-num" style="color:#58a6ff;" id="repos">0</div><div class="stat-label">PUBLIC REPOS</div></div>
      <div class="stat-card purple"><div class="stat-num" style="color:#bc8cff;" id="agents">0</div><div class="stat-label">AGENTS SHIPPED</div></div>
      <div class="stat-card orange"><div class="stat-num" style="color:#ffa657;" id="prs">0</div><div class="stat-label">PULL REQUESTS</div></div>
    </div>

    <!-- CONTRIBUTION GRID -->
    <div class="sec-header"><span class="sec-icon">🐍</span><span class="sec-title">contributions.svg</span><div class="sec-line"></div></div>
    <div class="contrib-grid" id="contrib-grid"></div>

    <!-- COLLAB -->
    <div class="sec-header"><span class="sec-icon">🤝</span><span class="sec-title">open_to_collaborate.md</span><div class="sec-line"></div></div>
    <div class="collab-list">
      <div class="collab-item"><span class="collab-num">01</span>AI Agent Platforms & Frameworks</div>
      <div class="collab-item"><span class="collab-num">02</span>LLM Security & Red-teaming</div>
      <div class="collab-item"><span class="collab-num">03</span>Multi-agent Research Projects</div>
      <div class="collab-item"><span class="collab-num">04</span>Enterprise AI Deployment</div>
      <div class="collab-item"><span class="collab-num">05</span>Open Source AI Tooling</div>
    </div>

    <!-- CONNECT -->
    <div class="sec-header"><span class="sec-icon">🔗</span><span class="sec-title">connect.sh</span><div class="sec-line"></div></div>
    <div class="links-row">
      <div class="link-card"><span class="link-icon">💼</span><div><div class="link-label">LinkedIn</div><div class="link-sub">Let's connect</div></div></div>
      <div class="link-card"><span class="link-icon">🐙</span><div><div class="link-label">GitHub</div><div class="link-sub">View my code</div></div></div>
      <div class="link-card"><span class="link-icon">🐦</span><div><div class="link-label">Twitter / X</div><div class="link-sub">AI thoughts</div></div></div>
      <div class="link-card"><span class="link-icon">✉️</span><div><div class="link-label">Email</div><div class="link-sub">Get in touch</div></div></div>
    </div>

  </div>

  <div class="footer">
    <div class="footer-text"><span>Built with ❤️ by Ramani</span> · <span style="color:#58a6ff;">AI Engineer</span> · <span style="color:#bc8cff;">Security Engineer</span></div>
    <div class="footer-text" style="margin-top:6px; font-size:0.65rem;"><span>Powered by Claude</span> · agents running 24/7 · <span>$ ./deploy --prod</span></div>
  </div>
</div>

<script>
  const lines = ['🤖 AI Engineer', '🛡️ Security Engineer', '🧠 Agent Orchestration Engineer', '🚀 Forward Deployed Engineer'];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById('typer');
  function type() {
    const word = lines[li];
    if (!deleting) {
      el.textContent = word.slice(0, ci + 1); ci++;
      if (ci === word.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = word.slice(0, ci - 1); ci--;
      if (ci === 0) { deleting = false; li = (li + 1) % lines.length; setTimeout(type, 300); return; }
    }
    setTimeout(type, deleting ? 45 : 80);
  }
  type();

  function countUp(id, target) {
    const el = document.getElementById(id);
    let current = 0;
    const step = Math.ceil(target / 60);
    const interval = setInterval(() => {
      current = Math.min(current + step, target);
      el.textContent = current.toLocaleString();
      if (current >= target) clearInterval(interval);
    }, 25);
  }
  setTimeout(() => {
    countUp('commits', 1247);
    countUp('repos', 38);
    countUp('agents', 24);
    countUp('prs', 312);
  }, 400);

  setTimeout(() => {
    document.querySelectorAll('.skill-fill').forEach(el => {
      el.style.width = el.getAttribute('data-pct') + '%';
    });
  }, 300);

  const grid = document.getElementById('contrib-grid');
  const weights = [0,0,0,0,1,1,1,2,2,3,4];
  const colors = ['#161b22','#0e4429','#006d32','#26a641','#39d353'];
  for (let i = 0; i < 52 * 7; i++) {
    const cell = document.createElement('div');
    const w = weights[Math.floor(Math.random() * weights.length)];
    cell.className = 'contrib-cell';
    cell.style.background = colors[w];
    grid.appendChild(cell);
  }
  let snakeIdx = 0;
  const cells = grid.querySelectorAll('.contrib-cell');
  function snakeStep() {
    if (cells[snakeIdx]) {
      cells[snakeIdx].style.background = '#39d353';
      setTimeout(() => {
        if (cells[snakeIdx]) {
          const lvl = weights[Math.floor(Math.random() * weights.length)];
          cells[snakeIdx].style.background = colors[lvl];
        }
      }, 600);
    }
    snakeIdx = (snakeIdx + 1) % cells.length;
    setTimeout(snakeStep, 30);
  }
  setTimeout(snakeStep, 800);
</script>
