---
# the default layout is 'page'
title: About
description: About Salmon Kumar, Security Engineer & Penetration Tester
permalink: /about/
icon: fas fa-info-circle
order: 4
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Syne:wght@400;600;700;800&display=swap');

:root {
  --red: #ff2d2d;
  --dim-red: #cc1a1a;
  --green: #00ff9d;
  --dim-green: #00cc7a;
  --bg: #0a0a0a;
  --surface: #111111;
  --surface2: #171717;
  --border: #222222;
  --text: #e8e8e8;
  --muted: #666666;
  --mono: 'Share Tech Mono', monospace;
  --sans: 'Syne', sans-serif;
}

.about-wrapper {
  font-family: var(--sans);
  color: var(--text);
  max-width: 900px;
  margin: 0 auto;
  padding: 0 0 4rem;
}

/* ── HERO ── */
.hero {
  position: relative;
  padding: 3.5rem 0 3rem;
  border-bottom: 1px solid var(--border);
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 60% 120% at 80% 50%, rgba(255,45,45,0.06) 0%, transparent 70%);
  pointer-events: none;
}

.hero-eyebrow {
  font-family: var(--mono);
  font-size: 0.9rem;
  color: var(--red);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.6rem;
}

.hero-eyebrow::before {
  content: '//';
  opacity: 0.4;
}

.hero-name {
  font-size: clamp(2.4rem, 6vw, 4rem);
  font-weight: 800;
  line-height: 1.05;
  letter-spacing: -0.03em;
  margin: 0 0 0.5rem;
  color: #fff;
}

.hero-name span {
  color: var(--red);
}

.hero-title {
  font-family: var(--mono);
  font-size: 1rem;
  color: var(--muted);
  letter-spacing: 0.08em;
  margin-bottom: 1.6rem;
}

.hero-title em {
  color: var(--green);
  font-style: normal;
}

.hero-summary {
  font-size: 1.05rem;
  line-height: 1.75;
  color: #aaaaaa;
  max-width: 640px;
  margin-bottom: 2rem;
}

.hero-summary strong {
  color: var(--text);
  font-weight: 600;
}

.status-pill {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(0,255,157,0.06);
  border: 1px solid rgba(0,255,157,0.2);
  padding: 0.35rem 0.9rem;
  border-radius: 100px;
  font-family: var(--mono);
  font-size: 0.72rem;
  color: var(--green);
  letter-spacing: 0.05em;
}

.status-dot {
  width: 6px;
  height: 6px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0,255,157,0.4); }
  50% { opacity: 0.7; box-shadow: 0 0 0 5px rgba(0,255,157,0); }
}

/* ── IMPACT NUMBERS ── */
.impact-bar {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  border: 1px solid var(--border);
  border-radius: 4px;
  margin: 2.5rem 0;
  overflow: hidden;
}

.impact-item {
  padding: 1.4rem 1.2rem;
  border-right: 1px solid var(--border);
  position: relative;
}

.impact-item:last-child { border-right: none; }

.impact-item::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: var(--red);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s ease;
}

.impact-item:hover::after { transform: scaleX(1); }

.impact-number {
  font-family: var(--mono);
  font-size: 1.8rem;
  color: #fff;
  font-weight: 700;
  line-height: 1;
  margin-bottom: 0.3rem;
}

.impact-number span {
  color: var(--red);
}

.impact-label {
  font-size: 0.8rem;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  font-family: var(--mono);
}

/* ── SECTION HEADINGS ── */
.section {
  margin-top: 3rem;
}

.section-heading {
  font-family: var(--mono);
  font-size: 1.2rem;
  letter-spacing: 0.20em;
  text-transform: uppercase;
  color: var(--red);
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
}

.section-heading::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border);
}

/* ── EXPERTISE CARDS ── */
.expertise-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
}

.expertise-card {
  background: var(--surface);
  padding: 1.4rem 1.6rem;
  transition: background 0.2s;
}

.expertise-card:hover { background: var(--surface2); }

.expertise-card-icon {
  font-size: 1.2rem;
  margin-bottom: 0.6rem;
}

.expertise-card-title {
  font-weight: 700;
  font-size: 1.2rem;
  color: #fff;
  margin-bottom: 0.4rem;
  letter-spacing: -0.01em;
}

.expertise-card-desc {
  font-size: 0.9rem;
  color: var(--muted);
  line-height: 1.5;
}

/* ── SKILLS ── */
.skills-block {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.skill-row {
  display: flex;
  align-items: baseline;
  gap: 1rem;
}

.skill-cat {
  font-family: var(--mono);
  font-size: 0.9rem;
  color: var(--muted);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  min-width: 130px;
  flex-shrink: 0;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.tag {
  font-family: var(--mono);
  font-size: 0.72rem;
  padding: 0.2rem 0.6rem;
  border-radius: 2px;
  letter-spacing: 0.03em;
  transition: all 0.2s;
}

.tag-red {
  background: rgba(255,45,45,0.08);
  border: 1px solid rgba(255,45,45,0.2);
  color: #ff8080;
}

.tag-red:hover {
  background: rgba(255,45,45,0.15);
  border-color: rgba(255,45,45,0.4);
  color: #ffaaaa;
}

.tag-green {
  background: rgba(0,255,157,0.05);
  border: 1px solid rgba(0,255,157,0.15);
  color: #80ffcc;
}

.tag-green:hover {
  background: rgba(0,255,157,0.1);
  border-color: rgba(0,255,157,0.3);
}

.tag-neutral {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  color: #888;
}

.tag-neutral:hover {
  background: rgba(255,255,255,0.07);
  color: var(--text);
}

/* ── APPSEC FOCUS ── */
.appsec-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
}

.appsec-item {
  background: var(--surface);
  padding: 1rem 1.2rem;
}

.appsec-label {
  font-family: var(--mono);
  font-size: 0.82rem;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: 0.35rem;
}

.appsec-value {
  font-size: 0.85rem;
  color: var(--text);
  font-weight: 600;
}

/* ── TIMELINE ── */
.timeline {
  position: relative;
  padding-left: 1.5rem;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 0; top: 8px; bottom: 8px;
  width: 1px;
  background: var(--border);
}

.timeline-item {
  position: relative;
  padding-bottom: 2rem;
}

.timeline-item:last-child { padding-bottom: 0; }

.timeline-item::before {
  content: '';
  position: absolute;
  left: -1.5rem;
  top: 8px;
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--red);
  border: 1px solid var(--dim-red);
  transform: translateX(-3px);
}

.timeline-meta {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 0.4rem;
  flex-wrap: wrap;
}

.timeline-role {
  font-weight: 700;
  font-size: 1.2rem;
  color: #fff;
}

.timeline-company {
  font-family: var(--mono);
  font-size: 0.9rem;
  color: var(--green);
}

.timeline-period {
  font-family: var(--mono);
  font-size: 0.9rem;
  color: var(--muted);
  margin-left: auto;
}

.timeline-bullets {
  list-style: none;
  padding: 0;
  margin: 0.5rem 0 0;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}

.timeline-bullets li {
  font-size: 1rem;
  color: #888;
  line-height: 1.5;
  padding-left: 1rem;
  position: relative;
}

.timeline-bullets li::before {
  content: '›';
  position: absolute;
  left: 0;
  color: var(--red);
  font-weight: 700;
}

.timeline-bullets li strong {
  color: #bbb;
  font-weight: 600;
}

/* ── CTF PLATFORMS ── */
.ctf-section {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.ctf-card {
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 1.2rem 1.4rem;
  background: var(--surface);
}

.ctf-card-label {
  font-family: var(--mono);
  font-size: 1rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--muted);
  margin-bottom: 0.8rem;
}

/* ── CONNECT ── */

.connect-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.5rem;
}

.connect-link {
  display: flex;
  align-items: center;
  gap: 0.7rem;
  padding: 0.75rem 1rem;
  border: 1px solid var(--border);
  border-radius: 3px;
  text-decoration: none;
  color: var(--muted);
  font-family: var(--mono);
  font-size: 0.9rem;
  transition: all 0.2s;
  background: var(--surface);
}

.connect-link:hover {
  border-color: var(--red);
  color: var(--text);
  background: rgba(255,45,45,0.04);
  text-decoration: none;
}

.connect-link-icon { font-size: 0.9rem; }

.connect-link-type {
  font-size: 0.9rem;
  color: var(--muted);
  opacity: 0.5;
  margin-left: auto;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

/* ── QUOTE ── */
.quote-block {
  margin-top: 3rem;
  padding: 1.5rem 1.8rem;
  border-left: 2px solid var(--red);
  background: rgba(255,45,45,0.03);
}

.quote-block p {
  font-family: var(--mono);
  font-size: 1rem;
  color: #666;
  line-height: 1.7;
  margin: 0 0 0.3rem;
}

.quote-block cite {
  font-size: 0.8rem;
  color: var(--muted);
  opacity: 0.6;
}

/* ── RESUME CTA ── */
.resume-cta {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  background: var(--dim-red);
  color: #ffffff !important;
  padding: 0.65rem 1.4rem;
  border-radius: 3px;
  text-decoration: none;
  font-family: var(--mono);
  font-size: 0.9rem;
  letter-spacing: 0.05em;
  font-weight: 800;
  transition: background 0.2s;
  margin-top: 1rem;
}

.resume-cta:hover {
  text-decoration: none;
  color: #000000;
  background: #000000;
}

/* ── RESPONSIVE ── */
@media (max-width: 640px) {
  .impact-bar { grid-template-columns: repeat(2, 1fr); }
  .expertise-grid { grid-template-columns: 1fr; }
  .appsec-grid { grid-template-columns: repeat(2, 1fr); }
  .ctf-section { grid-template-columns: 1fr; }
  .connect-grid { grid-template-columns: 1fr; }
  .skill-row { flex-direction: column; gap: 0.3rem; }
  .skill-cat { min-width: unset; }
  .timeline-period { margin-left: 0; width: 100%; }
}
</style>

<div class="about-wrapper">

<!-- ── HERO ── -->
<div class="hero">
  <div class="hero-eyebrow">Security Researcher & AppSec Engineer</div>
  <h1 class="hero-name">Salmon<span>.</span><br>Kumar</h1>
  <div class="hero-title">
    <em>@0xSalm0n</em> &nbsp;·&nbsp; Security Engineer &nbsp;·&nbsp; Penetration Tester &nbsp;·&nbsp; AppSec
  </div>
  <p class="hero-summary">
    I break applications for a living — then help teams build them <strong>right</strong>. Specializing in <strong>web application, API, network, and mobile (Android) penetration testing</strong>, I combine a developer's understanding of codebases with an attacker's mindset to find what automated scanners miss.
  </p>
  <div class="status-pill">
    <span class="status-dot"></span>
    Available for Security Collaborations & CTF Teams
  </div>
</div>

<!-- ── IMPACT NUMBERS ── -->
<div class="impact-bar">
  <div class="impact-item">
    <div class="impact-number">1<span>yr+</span></div>
    <div class="impact-label">AppSec Experience</div>
  </div>
  <div class="impact-item">
    <div class="impact-number">OWASP<span>+</span></div>
    <div class="impact-label">Standards Applied</div>
  </div>
  <div class="impact-item">
    <div class="impact-number">4<span>x</span></div>
    <div class="impact-label">Attack Surfaces</div>
  </div>
  <div class="impact-item">
    <div class="impact-number">Dev <span>→</span> Sec</div>
    <div class="impact-label">Full-Stack Background</div>
  </div>
</div>

<!-- ── APPSEC FOCUS ── -->
<div class="section">
  <div class="section-heading">AppSec Focus Areas</div>
  <div class="appsec-grid">
    <div class="appsec-item">
      <div class="appsec-label">Primary Domain</div>
      <div class="appsec-value">Web Application Pentesting</div>
    </div>
    <div class="appsec-item">
      <div class="appsec-label">API Security</div>
      <div class="appsec-value">REST · GraphQL · Auth Flows</div>
    </div>
    <div class="appsec-item">
      <div class="appsec-label">Mobile</div>
      <div class="appsec-value">Android (APK Analysis)</div>
    </div>
    <div class="appsec-item">
      <div class="appsec-label">Methodology</div>
      <div class="appsec-value">OWASP Top 10 · PTES</div>
    </div>
    <div class="appsec-item">
      <div class="appsec-label">Secure Dev</div>
      <div class="appsec-value">SAST · Code Review · Hardening</div>
    </div>
    <div class="appsec-item">
      <div class="appsec-label">Goal</div>
      <div class="appsec-value">Red Team Operations</div>
    </div>
  </div>
</div>

<!-- ── EXPERTISE ── -->
<div class="section">
  <div class="section-heading">Core Competencies</div>
  <div class="expertise-grid">
    <div class="expertise-card">
      <div class="expertise-card-icon">🔍</div>
      <div class="expertise-card-title">Vulnerability Research</div>
      <div class="expertise-card-desc">Identifying logic flaws, injection points, and authentication bypasses in web apps and APIs beyond what automated scanners surface.</div>
    </div>
    <div class="expertise-card">
      <div class="expertise-card-icon">📋</div>
      <div class="expertise-card-title">Pentest Reporting</div>
      <div class="expertise-card-desc">Delivering developer-friendly reports with clear risk ratings, PoC evidence, and actionable remediation mapped to OWASP and CVSS.</div>
    </div>
    <div class="expertise-card">
      <div class="expertise-card-icon">🛡️</div>
      <div class="expertise-card-title">Secure Code Review</div>
      <div class="expertise-card-desc">Reviewing source code and collaborating with dev/DevOps teams to enforce secure coding standards before code ships to production.</div>
    </div>
    <div class="expertise-card">
      <div class="expertise-card-icon">⚙️</div>
      <div class="expertise-card-title">Attack Surface Reduction</div>
      <div class="expertise-card-desc">Endpoint hardening, infrastructure security, and threat modeling to shrink the attack surface and reduce organizational risk.</div>
    </div>
  </div>
</div>

<!-- ── TECHNICAL SKILLS ── -->
<div class="section">
  <div class="section-heading">Technical Skills</div>
  <div class="skills-block">
    <div class="skill-row">
      <div class="skill-cat">Security Tools</div>
      <div class="skill-tags">
        <span class="tag tag-red">Burp Suite</span>
        <span class="tag tag-red">Metasploit</span>
        <span class="tag tag-red">Nmap</span>
        <span class="tag tag-red">SQLMap</span>
        <span class="tag tag-red">Nessus</span>
        <span class="tag tag-red">Wireshark</span>
        <span class="tag tag-red">OWASP ZAP</span>
        <span class="tag tag-red">Postman</span>
      </div>
    </div>
    <div class="skill-row">
      <div class="skill-cat">Languages</div>
      <div class="skill-tags">
        <span class="tag tag-green">Python</span>
        <span class="tag tag-green">Bash</span>
        <span class="tag tag-green">JavaScript</span>
        <span class="tag tag-green">SQL</span>
        <span class="tag tag-green">C</span>
      </div>
    </div>
    <div class="skill-row">
      <div class="skill-cat">Platforms</div>
      <div class="skill-tags">
        <span class="tag tag-neutral">Linux</span>
        <span class="tag tag-neutral">Docker</span>
        <span class="tag tag-neutral">Git</span>
        <span class="tag tag-neutral">Android</span>
      </div>
    </div>
    <div class="skill-row">
      <div class="skill-cat">Practices</div>
      <div class="skill-tags">
        <span class="tag tag-neutral">Threat Modeling</span>
        <span class="tag tag-neutral">VAPT</span>
        <span class="tag tag-neutral">Exploit Development</span>
        <span class="tag tag-neutral">SAST</span>
        <span class="tag tag-neutral">Secure SDLC</span>
      </div>
    </div>
  </div>
</div>

<!-- ── EXPERIENCE ── -->
<div class="section">
  <div class="section-heading">Experience</div>
  <div class="timeline">

    <div class="timeline-item">
      <div class="timeline-meta">
        <span class="timeline-role">Cybersecurity Engineer</span>
        <span class="timeline-company">@ Talrop</span>
        <span class="timeline-period">Jan 2025 – Present</span>
      </div>
      <ul class="timeline-bullets">
        <li>Conducting <strong>VAPT on web apps, networks, and APIs</strong> — identifying critical vulnerabilities before attackers do.</li>
        <li>Collaborating directly with developers and DevOps to <strong>remediate findings against OWASP standards</strong> within sprint cycles.</li>
        <li>Performing <strong>endpoint hardening and simulating real-world attack scenarios</strong> to validate detection and response capabilities.</li>
        <li>Researching emerging threats and producing <strong>detailed security reports</strong> with severity ratings and remediation roadmaps.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-meta">
        <span class="timeline-role">Full-Stack Developer Intern</span>
        <span class="timeline-company">@ Talrop</span>
        <span class="timeline-period">May 2024 – Dec 2024</span>
      </div>
      <ul class="timeline-bullets">
        <li>Built and maintained web applications with a <strong>security-first development approach</strong> — giving me the developer context attackers exploit.</li>
        <li>Worked across <strong>backend APIs, database management, and CI/CD pipelines</strong>, understanding the full attack surface from the inside.</li>
        <li>Developed the <strong>attacker-developer perspective</strong> that now drives more accurate vulnerability discovery and remediation guidance.</li>
      </ul>
    </div>

  </div>
</div>

<!-- ── CTF PLATFORMS ── -->
<div class="section">
  <div class="section-heading">CTF Platforms</div>
  <div class="ctf-section">
    <div class="ctf-card">
      <div class="ctf-card-label">TryHackMe</div>
      <iframe
        src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=1052718"
        style="border:none; display:block; max-width:100%; background:var(--surface);"
        width="340"
        height="100">
      </iframe>
    </div>
    <div class="ctf-card">
      <div class="ctf-card-label">Hack The Box</div>
      <a href="https://app.hackthebox.com/profile/1120355" target="_blank" rel="noopener">
        <img src="https://www.hackthebox.com/badge/image/1120355"
          style="border:none; display:block; max-width:100%;"
          width="340"
          height="100" alt="HTB Badge">
      </a>
    </div>
  </div>
</div>

<!-- ── EDUCATION ── -->
<div class="section">
  <div class="section-heading">Education</div>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-meta">
        <span class="timeline-role">B.E. Computer Science & Engineering</span>
        <span class="timeline-period">2020 – 2024</span>
      </div>
      <ul class="timeline-bullets">
        <li>SCAD College of Engineering and Technology, Tirunelveli — <strong>CGPA: 7.8/10</strong></li>
      </ul>
    </div>
    <div class="timeline-item">
      <div class="timeline-meta">
        <span class="timeline-role">Higher Secondary Certificate (HSC) – Maths Biology</span>
        <span class="timeline-period">2019 – 2020</span>
      </div>
      <ul class="timeline-bullets">
        <li>Amir Jamal Higher Secondary School, Tirunelveli</li>
      </ul>
    </div>
  </div>
</div>

<!-- ── RESUME ── -->
<div class="section">
  <div class="section-heading">Resume</div>
  <p style="font-size:1rem; color:var(--muted); margin:0 0 0.3rem;">Full work history, certifications, and detailed project context.</p>
  <a class="resume-cta" href="/assets/resume/Salmon_Kumar.pdf" download>
    ↓ &nbsp;Download Resume PDF
  </a>
  <p style="font-size:0.8rem; color:var(--muted); opacity:0.5; margin-top:0.6rem; font-family:var(--mono);">Last updated: December 2025</p>
</div>

<!-- ── CONNECT ── -->
<div class="section">
  <div class="section-heading">Let's Connect</div>
  <p style="font-size:1rem; color:#777; margin-bottom:1rem; line-height:1.6;">
    Open to security research collaborations, red team engagements, CTF partnerships, and AppSec conversations. If you're hiring a pentest engineer or want to swap vulnerability war stories — reach out.
  </p>
  <div class="connect-grid">
    <a class="connect-link" href="mailto:salmonkumar1337@gmail.com">
      <span class="connect-link-icon">✉</span>
      salmonkumar1337@gmail.com
      <span class="connect-link-type">Email</span>
    </a>
    <a class="connect-link" href="https://linkedin.com/in/0xsalmon" target="_blank" rel="noopener">
      <span class="connect-link-icon">in</span>
      linkedin.com/in/0xsalmon
      <span class="connect-link-type">LinkedIn</span>
    </a>
    <a class="connect-link" href="https://github.com/0xSalm0n" target="_blank" rel="noopener">
      <span class="connect-link-icon">⌥</span>
      github.com/0xSalm0n
      <span class="connect-link-type">GitHub</span>
    </a>
    <a class="connect-link" href="https://twitter.com/0xSalm0n" target="_blank" rel="noopener">
      <span class="connect-link-icon">𝕏</span>
      twitter.com/0xSalm0n
      <span class="connect-link-type">X / Twitter</span>
    </a>
  </div>
</div>

<!-- ── QUOTE ── -->
<div class="quote-block">
  <p>"There is no patch for human stupidity."</p>
  <cite>— Kevin Mitnick</cite>
</div>

</div>