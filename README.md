

<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;600&display=swap');

  :root {
    --navy: #0b0f1a;
    --panel: #111827;
    --card: #161d2e;
    --border: #1e2d45;
    --cyan: #22d3ee;
    --cyan2: #0ea5e9;
    --amber: #f59e0b;
    --green: #10b981;
    --muted: #64748b;
    --text: #e2e8f0;
    --subtext: #94a3b8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .readme-root {
    background: var(--navy);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    min-height: 100vh;
    padding: 0 0 40px;
    position: relative;
    overflow: hidden;
  }

  .grid-bg {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background-image:
      linear-gradient(rgba(34,211,238,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(34,211,238,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
  }

  .top-bar {
    background: var(--panel);
    border-bottom: 1px solid var(--border);
    padding: 12px 24px;
    display: flex;
    align-items: center;
    gap: 10px;
    position: relative;
    z-index: 2;
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ef4444; }
  .dot-y { background: #f59e0b; }
  .dot-g { background: #22c55e; }

  .top-bar-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-left: 8px;
  }

  .hero {
    position: relative;
    z-index: 2;
    padding: 48px 32px 36px;
    text-align: center;
  }

  .avatar-ring {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--cyan), var(--cyan2));
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
    position: relative;
    animation: pulse-ring 3s ease-in-out infinite;
  }

  @keyframes pulse-ring {
    0%, 100% { box-shadow: 0 0 0 0 rgba(34,211,238,0.3); }
    50% { box-shadow: 0 0 0 14px rgba(34,211,238,0); }
  }

  .avatar-inner {
    width: 88px;
    height: 88px;
    border-radius: 50%;
    background: var(--navy);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px;
    font-weight: 600;
    color: var(--cyan);
  }

  .hero-name {
    font-size: 30px;
    font-weight: 700;
    letter-spacing: -0.5px;
    color: #f0f6ff;
  }

  .hero-name span { color: var(--cyan); }

  .hero-role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--amber);
    margin: 6px 0 16px;
    letter-spacing: 1px;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin-bottom: 20px;
  }

  .badge {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 5px 14px;
    font-size: 12px;
    color: var(--subtext);
    font-family: 'JetBrains Mono', monospace;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .badge .bdot { width: 7px; height: 7px; border-radius: 50%; }

  .terminal-card {
    position: relative;
    z-index: 2;
    margin: 0 24px 32px;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .term-header {
    background: var(--card);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid var(--border);
  }

  .term-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-left: 4px;
  }

  .term-body {
    padding: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.8;
    min-height: 130px;
  }

  .term-prompt { color: var(--green); }
  .term-cmd { color: var(--cyan); }
  .term-out { color: var(--subtext); }
  .term-val { color: var(--amber); }
  .cursor {
    display: inline-block;
    width: 8px;
    height: 15px;
    background: var(--cyan);
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 50% { opacity: 0; } }

  .section {
    position: relative;
    z-index: 2;
    padding: 0 24px;
    margin-bottom: 28px;
  }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--cyan);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
    gap: 10px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 12px;
    text-align: center;
    transition: all 0.25s ease;
    cursor: default;
  }

  .skill-card:hover {
    border-color: var(--cyan);
    transform: translateY(-3px);
    background: #172036;
  }

  .skill-icon {
    font-size: 22px;
    margin-bottom: 7px;
    display: block;
  }

  .skill-name {
    font-size: 12px;
    font-weight: 600;
    color: var(--text);
    display: block;
    margin-bottom: 3px;
  }

  .skill-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
  }

  .metrics-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }

  .metric-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 12px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .metric-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--cyan), var(--cyan2));
  }

  .metric-val {
    font-size: 22px;
    font-weight: 700;
    color: var(--cyan);
    font-family: 'JetBrains Mono', monospace;
    display: block;
  }

  .metric-lbl {
    font-size: 11px;
    color: var(--muted);
    margin-top: 4px;
    display: block;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s;
  }

  .project-card:hover { border-color: var(--cyan); }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 80px; height: 80px;
    border-radius: 50%;
    opacity: 0.04;
    background: var(--cyan);
  }

  .project-name {
    font-size: 15px;
    font-weight: 600;
    color: #f0f6ff;
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .project-emoji { font-size: 18px; }

  .project-desc {
    font-size: 12px;
    color: var(--subtext);
    line-height: 1.6;
    margin-bottom: 12px;
  }

  .project-tags {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .project-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    background: rgba(34,211,238,0.08);
    color: var(--cyan);
    border: 1px solid rgba(34,211,238,0.2);
    border-radius: 4px;
    padding: 3px 8px;
  }

  .connect-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }

  .connect-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
    transition: all 0.2s;
  }

  .connect-card:hover {
    border-color: var(--cyan);
    transform: translateY(-2px);
    background: #172036;
  }

  .connect-icon {
    width: 36px;
    height: 36px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 17px;
    flex-shrink: 0;
  }

  .connect-label {
    font-size: 11px;
    color: var(--muted);
    display: block;
  }

  .connect-val {
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
  }

  .cert-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .cert-pill {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    font-weight: 500;
    color: var(--text);
  }

  .cert-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--amber);
    flex-shrink: 0;
  }

  .stat-bar-row {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .stat-bar-item {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 12px;
  }

  .stat-bar-label {
    width: 90px;
    color: var(--subtext);
    font-family: 'JetBrains Mono', monospace;
    flex-shrink: 0;
  }

  .stat-bar-track {
    flex: 1;
    height: 6px;
    background: var(--border);
    border-radius: 3px;
    overflow: hidden;
  }

  .stat-bar-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, var(--cyan2), var(--cyan));
    width: 0;
    transition: width 1.5s cubic-bezier(0.25, 1, 0.5, 1);
  }

  .stat-pct {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--cyan);
    width: 36px;
    text-align: right;
  }

  .footer-line {
    position: relative;
    z-index: 2;
    text-align: center;
    padding: 20px 24px 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    border-top: 1px solid var(--border);
    margin: 0 24px;
  }

  .footer-line span { color: var(--cyan); }

  .animate-in {
    opacity: 0;
    transform: translateY(16px);
    animation: fadeUp 0.6s ease forwards;
  }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }
</style>

<div class="readme-root">
  <div class="grid-bg"></div>

  <div class="top-bar">
    <div class="dot dot-r"></div>
    <div class="dot dot-y"></div>
    <div class="dot dot-g"></div>
    <span class="top-bar-label">~/sandy-pandit/README.md</span>
  </div>

  <div class="hero animate-in" style="animation-delay:0.1s">
    <div class="avatar-ring">
      <div class="avatar-inner">SP</div>
    </div>
    <div class="hero-name">Sandeep <span>Pandit</span></div>
    <div class="hero-role">// SENIOR DEVOPS ENGINEER</div>
    <div class="badges">
      <div class="badge"><div class="bdot" style="background:#22d3ee"></div>AWS Certified</div>
      <div class="badge"><div class="bdot" style="background:#f59e0b"></div>HashiCorp Certified</div>
      <div class="badge"><div class="bdot" style="background:#10b981"></div>TCS — Gurugram, IN</div>
      <div class="badge"><div class="bdot" style="background:#a78bfa"></div>5 yrs experience</div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.2s">
    <div class="terminal-card">
      <div class="term-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="term-title">bash — who is sandy</span>
      </div>
      <div class="term-body" id="terminal-body">
        <div id="term-lines"></div>
        <span class="cursor" id="cursor"></span>
      </div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.3s">
    <div class="section-label">// Impact metrics</div>
    <div class="metrics-row">
      <div class="metric-card">
        <span class="metric-val" data-target="70">0</span>
        <span class="metric-lbl">% faster infra provisioning</span>
      </div>
      <div class="metric-card">
        <span class="metric-val" data-target="60">0</span>
        <span class="metric-lbl">% Docker image size cut</span>
      </div>
      <div class="metric-card">
        <span class="metric-val" data-target="40">0</span>
        <span class="metric-lbl">% build cycle reduction</span>
      </div>
      <div class="metric-card">
        <span class="metric-val" data-target="30">0</span>
        <span class="metric-lbl">% cloud cost savings</span>
      </div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.35s">
    <div class="section-label">// Tech stack</div>
    <div class="skills-grid">
      <div class="skill-card"><span class="skill-icon">☁️</span><span class="skill-name">AWS</span><span class="skill-tag">EKS · ECS · Lambda</span></div>
      <div class="skill-card"><span class="skill-icon">🏗️</span><span class="skill-name">Terraform</span><span class="skill-tag">IaC · Modules</span></div>
      <div class="skill-card"><span class="skill-icon">🐳</span><span class="skill-name">Docker</span><span class="skill-tag">Containers</span></div>
      <div class="skill-card"><span class="skill-icon">⚙️</span><span class="skill-name">Kubernetes</span><span class="skill-tag">EKS · Helm</span></div>
      <div class="skill-card"><span class="skill-icon">🔁</span><span class="skill-name">CI/CD</span><span class="skill-tag">Jenkins · GitHub</span></div>
      <div class="skill-card"><span class="skill-icon">📊</span><span class="skill-name">Observability</span><span class="skill-tag">Prometheus · Grafana</span></div>
      <div class="skill-card"><span class="skill-icon">🔐</span><span class="skill-name">DevSecOps</span><span class="skill-tag">Trivy · SonarQube</span></div>
      <div class="skill-card"><span class="skill-icon">🐚</span><span class="skill-name">Scripting</span><span class="skill-tag">Bash · Python</span></div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.4s">
    <div class="section-label">// Expertise depth</div>
    <div class="stat-bar-row" id="bars">
      <div class="stat-bar-item"><span class="stat-bar-label">AWS</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="95"></div></div><span class="stat-pct">95%</span></div>
      <div class="stat-bar-item"><span class="stat-bar-label">Terraform</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="92"></div></div><span class="stat-pct">92%</span></div>
      <div class="stat-bar-item"><span class="stat-bar-label">Kubernetes</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="88"></div></div><span class="stat-pct">88%</span></div>
      <div class="stat-bar-item"><span class="stat-bar-label">Docker</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="90"></div></div><span class="stat-pct">90%</span></div>
      <div class="stat-bar-item"><span class="stat-bar-label">Jenkins</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="85"></div></div><span class="stat-pct">85%</span></div>
      <div class="stat-bar-item"><span class="stat-bar-label">Bash/Python</span><div class="stat-bar-track"><div class="stat-bar-fill" data-w="80"></div></div><span class="stat-pct">80%</span></div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.45s">
    <div class="section-label">// Personal projects</div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-name"><span class="project-emoji">🗺️</span>EKSAtlas</div>
        <div class="project-desc">Production-style EKS cluster automation — VPC, node groups, IAM, ALB ingress, and Helm chart deployment in one Terraform workflow.</div>
        <div class="project-tags">
          <span class="project-tag">Terraform</span>
          <span class="project-tag">EKS</span>
          <span class="project-tag">Helm</span>
          <span class="project-tag">AWS</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-name"><span class="project-emoji">🔩</span>CloudSculptor</div>
        <div class="project-desc">Modular AWS infrastructure library — reusable, version-controlled Terraform modules for VPC, EC2, RDS, ECS, and security baselines.</div>
        <div class="project-tags">
          <span class="project-tag">Terraform</span>
          <span class="project-tag">Modules</span>
          <span class="project-tag">VPC</span>
          <span class="project-tag">RDS</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.5s">
    <div class="section-label">// Certifications</div>
    <div class="cert-row">
      <div class="cert-pill"><div class="cert-dot"></div>AWS DevOps Engineer — Professional</div>
      <div class="cert-pill"><div class="cert-dot"></div>AWS Cloud Practitioner</div>
      <div class="cert-pill"><div class="cert-dot"></div>HashiCorp Terraform Associate</div>
    </div>
  </div>

  <div class="section animate-in" style="animation-delay:0.55s">
    <div class="section-label">// Connect</div>
    <div class="connect-row">
      <a class="connect-card" href="https://www.linkedin.com/in/sandeep-pandit-540b32150/" target="_blank">
        <div class="connect-icon" style="background:rgba(10,102,194,0.15);color:#0a66c2">in</div>
        <div>
          <span class="connect-label">LinkedIn</span>
          <span class="connect-val">sandeep-pandit</span>
        </div>
      </a>
      <a class="connect-card" href="https://github.com/sandy24998" target="_blank">
        <div class="connect-icon" style="background:rgba(255,255,255,0.06);color:#e2e8f0;font-size:20px">⌥</div>
        <div>
          <span class="connect-label">GitHub</span>
          <span class="connect-val">sandy24998</span>
        </div>
      </a>
      <a class="connect-card" href="mailto:24panditsandeep@gmail.com">
        <div class="connect-icon" style="background:rgba(239,68,68,0.12);color:#ef4444;font-size:16px">✉</div>
        <div>
          <span class="connect-label">Email</span>
          <span class="connect-val">24panditsandeep@gmail.com</span>
        </div>
      </a>
    </div>
  </div>

  <div class="footer-line animate-in" style="animation-delay:0.6s">
    <span>Provisioned with Terraform</span> · <span>Deployed on EKS</span> · <span>Monitored by Prometheus</span>
  </div>
</div>

<script>
const lines = [
  { type: 'prompt', text: '$ whoami' },
  { type: 'out', text: 'DevOps Engineer · TCS · Gurugram, India' },
  { type: 'prompt', text: '$ cat mission.txt' },
  { type: 'out', text: 'Building resilient, automated cloud infrastructure' },
  { type: 'out', text: 'that scales with zero drama.' },
  { type: 'prompt', text: '$ echo $SPECIALIZATION' },
  { type: 'val', text: 'AWS · Terraform · EKS · Jenkins · DevSecOps' },
  { type: 'prompt', text: '$ uptime --experience' },
  { type: 'val', text: '5 years total · 3+ years dedicated DevOps · Banking & FinServ' },
];

const container = document.getElementById('term-lines');
const cursor = document.getElementById('cursor');
let lineIdx = 0;

function typeLine(lineObj, done) {
  const div = document.createElement('div');
  if (lineObj.type === 'prompt') {
    const prompt = document.createElement('span');
    prompt.className = 'term-prompt';
    prompt.textContent = '→ ';
    const cmd = document.createElement('span');
    cmd.className = 'term-cmd';
    div.appendChild(prompt);
    div.appendChild(cmd);
    container.appendChild(div);
    let i = 0;
    const iv = setInterval(() => {
      cmd.textContent = lineObj.text.slice(1, i + 2);
      i++;
      if (i >= lineObj.text.length - 1) { clearInterval(iv); setTimeout(done, 120); }
    }, 38);
  } else {
    const span = document.createElement('span');
    span.className = lineObj.type === 'val' ? 'term-val' : 'term-out';
    span.style.paddingLeft = '16px';
    span.textContent = lineObj.text;
    div.appendChild(span);
    container.appendChild(div);
    setTimeout(done, 80);
  }
}

function runTerminal() {
  if (lineIdx >= lines.length) return;
  typeLine(lines[lineIdx], () => {
    lineIdx++;
    setTimeout(runTerminal, lineIdx % 2 === 0 ? 200 : 80);
  });
}

setTimeout(runTerminal, 800);

function animateCounters() {
  document.querySelectorAll('[data-target]').forEach(el => {
    const target = parseInt(el.dataset.target);
    let cur = 0;
    const step = Math.ceil(target / 40);
    const iv = setInterval(() => {
      cur = Math.min(cur + step, target);
      el.textContent = cur + '%';
      if (cur >= target) clearInterval(iv);
    }, 28);
  });
}

function animateBars() {
  document.querySelectorAll('.stat-bar-fill').forEach(el => {
    setTimeout(() => { el.style.width = el.dataset.w + '%'; }, 200);
  });
}

setTimeout(() => { animateCounters(); animateBars(); }, 600);
</script>
