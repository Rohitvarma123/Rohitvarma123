<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muthyam Rohit Varma — AWS DevSecOps Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700;800&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #0A0C10;
    --panel: #12151C;
    --panel-2: #171B24;
    --border: #232838;
    --border-bright: #323A50;
    --text: #ECEFF4;
    --text-dim: #838B9E;
    --text-faint: #4D5568;
    --teal: #2DD9B9;
    --amber: #F5A623;
    --violet: #8B7CF6;
    --red: #F0616D;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Inter', sans-serif;
  }
  *{ box-sizing:border-box; margin:0; padding:0; }
  html{ scroll-behavior:smooth; }
  body{
    background:
      radial-gradient(ellipse 900px 500px at 12% -10%, rgba(45,217,185,0.08), transparent 60%),
      radial-gradient(ellipse 700px 500px at 100% 10%, rgba(139,124,246,0.07), transparent 60%),
      var(--bg);
    color:var(--text);
    font-family:var(--sans);
    line-height:1.5;
    -webkit-font-smoothing:antialiased;
    padding-bottom:60px;
  }
  ::selection{ background:rgba(45,217,185,0.25); color:#fff; }

  a{ color:inherit; text-decoration:none; }

  .wrap{ max-width:1080px; margin:0 auto; padding:0 24px; }

  /* ---------- top bar ---------- */
  .topbar{
    position:sticky; top:0; z-index:50;
    background:rgba(10,12,16,0.85);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--border);
  }
  .topbar-inner{
    max-width:1080px; margin:0 auto; padding:14px 24px;
    display:flex; align-items:center; justify-content:space-between;
    font-family:var(--mono); font-size:13px;
  }
  .prompt{ color:var(--teal); display:flex; align-items:center; gap:8px; }
  .prompt .cursor{
    width:7px; height:14px; background:var(--teal);
    display:inline-block; animation:blink 1.1s steps(1) infinite;
  }
  @keyframes blink{ 50%{ opacity:0; } }
  .status-pill{
    display:flex; align-items:center; gap:6px;
    color:var(--teal); border:1px solid rgba(45,217,185,0.35);
    background:rgba(45,217,185,0.08);
    padding:4px 10px; border-radius:20px; font-size:11px; letter-spacing:0.04em;
  }
  .dot{ width:6px; height:6px; border-radius:50%; background:var(--teal); box-shadow:0 0 8px var(--teal); animation:pulse 2s ease-in-out infinite; }
  @keyframes pulse{ 0%,100%{ opacity:1;} 50%{ opacity:0.4; } }

  /* ---------- hero ---------- */
  .hero{ padding:64px 0 40px; }
  .eyebrow{
    font-family:var(--mono); font-size:12px; color:var(--text-faint);
    letter-spacing:0.12em; text-transform:uppercase; margin-bottom:16px;
    display:flex; align-items:center; gap:10px;
  }
  .eyebrow::before{ content:''; width:24px; height:1px; background:var(--border-bright); }

  h1.name{
    font-family:var(--mono); font-weight:700;
    font-size:clamp(32px, 5vw, 54px);
    letter-spacing:-0.01em;
    color:#fff;
    margin-bottom:6px;
  }
  h1.name .amp{ color:var(--teal); }
  .role{
    font-family:var(--sans); font-weight:600; font-size:19px;
    color:var(--text-dim); margin-bottom:22px;
  }
  .role span{ color:var(--amber); }

  .objective{
    max-width:640px; color:var(--text-dim); font-size:15px; line-height:1.7;
    border-left:2px solid var(--border-bright); padding-left:16px; margin-bottom:28px;
  }

  .contact-row{ display:flex; flex-wrap:wrap; gap:10px; margin-bottom:8px; }
  .chip{
    font-family:var(--mono); font-size:12.5px;
    border:1px solid var(--border); background:var(--panel);
    padding:8px 14px; border-radius:8px; color:var(--text-dim);
    display:flex; align-items:center; gap:8px;
    transition:border-color .2s ease, color .2s ease, transform .2s ease;
  }
  .chip:hover{ border-color:var(--teal); color:var(--text); transform:translateY(-2px); }
  .chip b{ color:var(--text); font-weight:500; }

  /* ---------- section heading ---------- */
  .section{ padding:44px 0; border-top:1px solid var(--border); }
  .section-head{ display:flex; align-items:baseline; gap:12px; margin-bottom:26px; }
  .section-idx{ font-family:var(--mono); color:var(--text-faint); font-size:13px; }
  .section-title{ font-family:var(--sans); font-weight:800; font-size:22px; color:#fff; }
  .section-sub{ font-family:var(--mono); font-size:12px; color:var(--text-faint); margin-left:auto; }

  /* ---------- stat grid ---------- */
  .stats{ display:grid; grid-template-columns:repeat(4,1fr); gap:14px; }
  .stat-card{
    background:var(--panel); border:1px solid var(--border); border-radius:12px;
    padding:20px; position:relative; overflow:hidden;
  }
  .stat-card::after{
    content:''; position:absolute; top:0; left:0; width:100%; height:2px;
    background:linear-gradient(90deg, var(--bar), transparent);
  }
  .stat-val{ font-family:var(--mono); font-size:30px; font-weight:700; color:#fff; }
  .stat-label{ font-size:12px; color:var(--text-dim); margin-top:6px; }

  /* ---------- skills ---------- */
  .skill-groups{ display:grid; grid-template-columns:1fr 1fr; gap:16px; }
  .skill-panel{
    background:var(--panel); border:1px solid var(--border); border-radius:12px; padding:20px 22px;
  }
  .skill-panel-title{
    font-family:var(--mono); font-size:12px; letter-spacing:0.06em; text-transform:uppercase;
    color:var(--text-faint); margin-bottom:14px; display:flex; justify-content:space-between;
  }
  .meter-row{ margin-bottom:12px; }
  .meter-row:last-child{ margin-bottom:0; }
  .meter-top{ display:flex; justify-content:space-between; font-size:13px; margin-bottom:6px; }
  .meter-top span:first-child{ color:var(--text); }
  .meter-top span:last-child{ font-family:var(--mono); font-size:11px; color:var(--text-faint); }
  .meter-track{ height:6px; background:var(--panel-2); border-radius:4px; overflow:hidden; border:1px solid var(--border); }
  .meter-fill{ height:100%; border-radius:4px; width:0; transition:width 1.1s cubic-bezier(.2,.8,.2,1); }

  .tag-cloud{ display:flex; flex-wrap:wrap; gap:8px; }
  .tag{
    font-family:var(--mono); font-size:11.5px; color:var(--text-dim);
    border:1px solid var(--border); padding:6px 10px; border-radius:6px;
    background:var(--panel-2);
  }

  /* ---------- experience timeline ---------- */
  .timeline{ position:relative; padding-left:26px; }
  .timeline::before{ content:''; position:absolute; left:6px; top:6px; bottom:6px; width:1px; background:var(--border-bright); }
  .t-entry{ position:relative; padding-bottom:30px; }
  .t-entry:last-child{ padding-bottom:0; }
  .t-dot{
    position:absolute; left:-26px; top:4px; width:12px; height:12px; border-radius:50%;
    background:var(--bg); border:2px solid var(--teal); box-shadow:0 0 0 4px rgba(45,217,185,0.12);
  }
  .t-head{ display:flex; flex-wrap:wrap; align-items:baseline; gap:10px; margin-bottom:4px; }
  .t-role{ font-weight:700; font-size:16px; color:#fff; }
  .t-org{ color:var(--amber); font-size:14px; font-weight:600; }
  .t-date{ font-family:var(--mono); font-size:11.5px; color:var(--text-faint); margin-left:auto; }
  .t-list{ list-style:none; margin-top:10px; }
  .t-list li{ font-size:13.5px; color:var(--text-dim); padding-left:18px; position:relative; margin-bottom:6px; }
  .t-list li::before{ content:'›'; position:absolute; left:0; color:var(--teal); font-family:var(--mono); }

  /* ---------- projects ---------- */
  .projects{ display:grid; grid-template-columns:1fr 1fr; gap:16px; }
  .proj-card{
    background:var(--panel); border:1px solid var(--border); border-radius:12px; padding:22px;
    display:flex; flex-direction:column; transition:border-color .2s ease, transform .2s ease;
  }
  .proj-card:hover{ border-color:var(--border-bright); transform:translateY(-3px); }
  .proj-num{ font-family:var(--mono); font-size:11px; color:var(--text-faint); margin-bottom:10px; }
  .proj-title{ font-weight:700; font-size:15.5px; color:#fff; margin-bottom:12px; line-height:1.4; }
  .proj-list{ list-style:none; margin-bottom:16px; flex-grow:1; }
  .proj-list li{ font-size:13px; color:var(--text-dim); padding-left:16px; position:relative; margin-bottom:7px; }
  .proj-list li::before{ content:'—'; position:absolute; left:0; color:var(--violet); }
  .proj-tags{ display:flex; flex-wrap:wrap; gap:6px; padding-top:14px; border-top:1px solid var(--border); }
  .proj-tags span{ font-family:var(--mono); font-size:10.5px; color:var(--teal); background:rgba(45,217,185,0.08); border:1px solid rgba(45,217,185,0.2); padding:3px 8px; border-radius:5px; }

  /* ---------- education / internship ---------- */
  .two-col{ display:grid; grid-template-columns:1.3fr 1fr; gap:16px; }
  .info-card{ background:var(--panel); border:1px solid var(--border); border-radius:12px; padding:22px; }
  .info-card h3{ font-size:14px; color:#fff; margin-bottom:12px; font-weight:700; }
  .info-card .t-list{ margin-top:0; }
  .edu-degree{ font-weight:700; color:#fff; font-size:15px; }
  .edu-school{ color:var(--text-dim); font-size:13px; margin-top:4px; }
  .edu-row{ display:flex; justify-content:space-between; margin-top:14px; font-family:var(--mono); font-size:12px; }
  .edu-row .cgpa{ color:var(--teal); }
  .edu-row .yop{ color:var(--text-faint); }

  /* ---------- footer ---------- */
  .footer{
    margin-top:20px; padding-top:32px; border-top:1px solid var(--border);
    display:flex; flex-wrap:wrap; justify-content:space-between; align-items:center; gap:16px;
  }
  .footer-links{ display:flex; gap:12px; }
  .btn{
    font-family:var(--mono); font-size:12.5px; font-weight:600;
    padding:10px 18px; border-radius:8px; border:1px solid var(--border-bright);
    color:var(--text); transition:all .2s ease;
  }
  .btn.primary{ background:var(--teal); color:#06110D; border-color:var(--teal); }
  .btn:hover{ transform:translateY(-2px); box-shadow:0 6px 20px rgba(0,0,0,0.35); }
  .footer-note{ font-family:var(--mono); font-size:11px; color:var(--text-faint); }

  /* fade-in on load */
  .fade{ opacity:0; transform:translateY(14px); animation:fadeIn .7s ease forwards; }
  @keyframes fadeIn{ to{ opacity:1; transform:translateY(0); } }

  @media (max-width: 760px){
    .stats{ grid-template-columns:1fr 1fr; }
    .skill-groups, .projects, .two-col{ grid-template-columns:1fr; }
    .t-date{ margin-left:0; }
  }

  :focus-visible{ outline:2px solid var(--teal); outline-offset:2px; }
  @media (prefers-reduced-motion: reduce){
    *{ animation:none !important; transition:none !important; }
  }
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-inner">
    <div class="prompt">rohitvarma@devsecops:~$<span class="cursor"></span></div>
    <div class="status-pill"><span class="dot"></span>OPEN TO WORK</div>
  </div>
</div>

<div class="wrap">

  <section class="hero">
    <div class="eyebrow fade" style="animation-delay:.05s">profile / init</div>
    <h1 class="name fade" style="animation-delay:.1s">Muthyam Rohit<span class="amp">Varma</span></h1>
    <div class="role fade" style="animation-delay:.15s">AWS <span>DevSecOps</span> Engineer</div>
    <p class="objective fade" style="animation-delay:.2s">
      Skilled in automating infrastructure with Terraform and deploying applications using Docker, Kubernetes,
      and Ansible — focused on delivering secure, scalable cloud solutions through robust CI/CD and DevSecOps practices.
    </p>
    <div class="contact-row fade" style="animation-delay:.25s">
      <a class="chip" href="tel:+916304908843">📞 <b>+91 63049 08843</b></a>
      <a class="chip" href="mailto:rohitvarmamuthyam123@gmail.com">✉ <b>rohitvarmamuthyam123@gmail.com</b></a>
      <a class="chip" href="https://github.com/Rohitvarma123?tab=repositories" target="_blank" rel="noopener">⌥ github/<b>Rohitvarma123</b></a>
      <a class="chip" href="https://www.linkedin.com/in/rohit-varma-muthyam-26b840286/" target="_blank" rel="noopener">in <b>rohit-varma-muthyam</b></a>
    </div>
  </section>

  <section class="section" id="stats">
    <div class="section-head">
      <span class="section-idx">01</span>
      <span class="section-title">System Overview</span>
      <span class="section-sub">uptime --since=2024-11</span>
    </div>
    <div class="stats">
      <div class="stat-card" style="--bar:var(--teal)"><div class="stat-val" id="stat-exp">0</div><div class="stat-label">Years in DevSecOps</div></div>
      <div class="stat-card" style="--bar:var(--amber)"><div class="stat-val" id="stat-aws">0</div><div class="stat-label">AWS services managed</div></div>
      <div class="stat-card" style="--bar:var(--violet)"><div class="stat-val" id="stat-proj">0</div><div class="stat-label">Production projects</div></div>
      <div class="stat-card" style="--bar:var(--red)"><div class="stat-val" id="stat-cgpa">0.0</div><div class="stat-label">MCA CGPA</div></div>
    </div>
  </section>

  <section class="section" id="skills">
    <div class="section-head">
      <span class="section-idx">02</span>
      <span class="section-title">Skill Capacity</span>
      <span class="section-sub">core / infra</span>
    </div>
    <div class="skill-groups">
      <div class="skill-panel">
        <div class="skill-panel-title"><span>Core Stack</span><span>load</span></div>
        <div class="meter-row"><div class="meter-top"><span>Terraform (IaC)</span><span>92%</span></div><div class="meter-track"><div class="meter-fill" data-w="92" style="background:var(--violet)"></div></div></div>
        <div class="meter-row"><div class="meter-top"><span>Docker & Kubernetes</span><span>90%</span></div><div class="meter-track"><div class="meter-fill" data-w="90" style="background:var(--teal)"></div></div></div>
        <div class="meter-row"><div class="meter-top"><span>AWS (EC2 / S3 / IAM / RDS / Lambda)</span><span>88%</span></div><div class="meter-track"><div class="meter-fill" data-w="88" style="background:var(--amber)"></div></div></div>
        <div class="meter-row"><div class="meter-top"><span>Ansible</span><span>82%</span></div><div class="meter-track"><div class="meter-fill" data-w="82" style="background:var(--violet)"></div></div></div>
        <div class="meter-row"><div class="meter-top"><span>Jenkins CI/CD</span><span>85%</span></div><div class="meter-track"><div class="meter-fill" data-w="85" style="background:var(--teal)"></div></div></div>
        <div class="meter-row"><div class="meter-top"><span>Prometheus & Grafana</span><span>78%</span></div><div class="meter-track"><div class="meter-fill" data-w="78" style="background:var(--amber)"></div></div></div>
      </div>
      <div class="skill-panel">
        <div class="skill-panel-title"><span>Supporting Toolchain</span><span>tags</span></div>
        <div class="tag-cloud">
          <span class="tag">EC2</span><span class="tag">S3</span><span class="tag">VPC</span><span class="tag">IAM</span>
          <span class="tag">EBS / EFS</span><span class="tag">Auto Scaling</span><span class="tag">Load Balancers</span>
          <span class="tag">ECR</span><span class="tag">CloudWatch</span><span class="tag">CloudFront</span>
          <span class="tag">SonarQube</span><span class="tag">Nexus</span><span class="tag">Trivy</span>
          <span class="tag">Maven</span><span class="tag">Docker Hub</span><span class="tag">Git / GitHub</span>
          <span class="tag">Shell Scripting</span><span class="tag">Apache Tomcat</span>
          <span class="tag">Linux</span><span class="tag">MySQL</span>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="experience">
    <div class="section-head">
      <span class="section-idx">03</span>
      <span class="section-title">Experience Log</span>
      <span class="section-sub">git log --oneline</span>
    </div>
    <div class="timeline">
      <div class="t-entry">
        <div class="t-dot"></div>
        <div class="t-head">
          <span class="t-role">AWS DevSecOps Engineer</span>
          <span class="t-org">@ V Cube Software Solutions Pvt. Ltd.</span>
          <span class="t-date">NOV 2024 — PRESENT</span>
        </div>
        <ul class="t-list">
          <li>Managed and maintained AWS cloud services for scalability, security, and reliability</li>
          <li>Built CI/CD pipelines with Jenkins and Git to automate builds and deployments</li>
          <li>Integrated security checks into development and deployment workflows (DevSecOps)</li>
          <li>Containerized and orchestrated applications using Docker and Kubernetes</li>
          <li>Monitored system performance and optimized resources for high availability</li>
        </ul>
      </div>
      <div class="t-entry">
        <div class="t-dot" style="border-color:var(--text-faint); box-shadow:0 0 0 4px rgba(77,85,104,0.12)"></div>
        <div class="t-head">
          <span class="t-role">Cyber Security Virtual Intern</span>
          <span class="t-org">@ Virtual Internship Program</span>
          <span class="t-date">PRIOR</span>
        </div>
        <ul class="t-list">
          <li>Implemented confidentiality controls and access management for authorized users</li>
          <li>Applied authentication techniques to verify identity of users and systems</li>
          <li>Defined and enforced access control policies for resource utilization</li>
        </ul>
      </div>
    </div>
  </section>

  <section class="section" id="projects">
    <div class="section-head">
      <span class="section-idx">04</span>
      <span class="section-title">Deployed Projects</span>
      <span class="section-sub">repos / 2</span>
    </div>
    <div class="projects">
      <div class="proj-card">
        <div class="proj-num">PROJECT 01</div>
        <div class="proj-title">Certificateless Public Integrity Checking of Grouped Shared Data on Cloud Storage</div>
        <ul class="proj-list">
          <li>Decentralized, certificateless integrity checking for cloud storage</li>
          <li>Scalable system to manage group-shared data</li>
          <li>Preserved data privacy & confidentiality during verification</li>
          <li>User-friendly interface for integrity verification</li>
        </ul>
        <div class="proj-tags"><span>Java</span><span>AWS S3</span><span>AWS RDS</span><span>Jenkins</span><span>Docker</span><span>MySQL</span></div>
      </div>
      <div class="proj-card">
        <div class="proj-num">PROJECT 02</div>
        <div class="proj-title">Implementing DevSecOps for a Cloud-Based Web Application</div>
        <ul class="proj-list">
          <li>Integrated security practices into the existing DevOps pipeline</li>
          <li>Automated security testing and compliance checks</li>
          <li>Continuous monitoring and incident response</li>
        </ul>
        <div class="proj-tags"><span>Java</span><span>Maven</span><span>SonarQube</span><span>Nexus</span><span>Trivy</span><span>Docker</span></div>
      </div>
    </div>
  </section>

  <section class="section" id="education">
    <div class="section-head">
      <span class="section-idx">05</span>
      <span class="section-title">Education</span>
      <span class="section-sub">credentials</span>
    </div>
    <div class="two-col">
      <div class="info-card">
        <h3>Master of Computer Applications</h3>
        <div class="edu-school">DVR & Dr. HS MIC College of Technology</div>
        <div class="edu-row"><span class="cgpa">CGPA 8.10</span><span class="yop">YOP 2023</span></div>
      </div>
      <div class="info-card">
        <h3>Certifications & Focus</h3>
        <ul class="t-list">
          <li>DevSecOps pipeline security & compliance</li>
          <li>Cloud infrastructure automation (IaC)</li>
        </ul>
      </div>
    </div>
  </section>

  <div class="footer">
    <div class="footer-links">
      <a class="btn primary" href="mailto:rohitvarmamuthyam123@gmail.com">Send email</a>
      <a class="btn" href="https://github.com/Rohitvarma123?tab=repositories" target="_blank" rel="noopener">View GitHub</a>
      <a class="btn" href="https://www.linkedin.com/in/rohit-varma-muthyam-26b840286/" target="_blank" rel="noopener">View LinkedIn</a>
    </div>
    <div class="footer-note">last deployed · rohit-varma-portfolio · main branch</div>
  </div>

</div>

<script>
  // animate stat counters
  function animateCount(id, target, decimals=0, duration=1200){
    const el = document.getElementById(id);
    const start = performance.now();
    function tick(now){
      const p = Math.min(1, (now-start)/duration);
      const eased = 1 - Math.pow(1-p, 3);
      const val = target * eased;
      el.textContent = decimals ? val.toFixed(decimals) : Math.round(val);
      if(p < 1) requestAnimationFrame(tick);
    }
    requestAnimationFrame(tick);
  }
  window.addEventListener('load', () => {
    animateCount('stat-exp', 1.8, 1);
    animateCount('stat-aws', 16, 0);
    animateCount('stat-proj', 2, 0);
    animateCount('stat-cgpa', 8.1, 1);
    document.querySelectorAll('.meter-fill').forEach(el => {
      setTimeout(() => { el.style.width = el.dataset.w + '%'; }, 300);
    });
  });
</script>

</body>
</html>
