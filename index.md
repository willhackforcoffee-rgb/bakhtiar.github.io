---
layout: default
title: BAKHTIAR // CYBER-OPS
---

<script src="https://unpkg.com/typed.js@2.1.0/dist/typed.umd.js"></script>

<style>
  body {
    background-color: #0d1117;
    color: #2ecc71; 
    font-family: 'Courier New', Courier, monospace;
    background-image: linear-gradient(rgba(0,0,0,0.94), rgba(0,0,0,0.94)), url('background1.jpg');
    background-size: cover;
    background-attachment: fixed;
    line-height: 1.6;
    margin: 0 auto;
    max-width: 900px;
    padding: 20px;
  }

  /* Interactive Terminal Header */
  .terminal-header {
    font-size: 1.4em;
    font-weight: bold;
    color: #2ecc71;
    margin-bottom: 20px;
  }
  
  #typed-command {
    color: #ffffff;
    text-shadow: 0 0 5px rgba(255,255,255,0.3);
  }

  /* Profile Image Styling */
  .profile-img {
    border-radius: 8px;
    border: 2px solid #2ecc71;
    margin-bottom: 20px;
    transition: transform 0.3s;
  }
  .profile-img:hover {
    transform: scale(1.02);
  }

  /* Professional Accents */
  .award-text {
    color: #5dade2; /* Professional Sky Blue */
    font-weight: bold;
  }

  .highlight { 
    color: #f1c40f !important; /* Gold for visibility */
    font-weight: bold;
  }

  .link-btn {
    border: 1px solid #2ecc71;
    padding: 6px 14px;
    text-decoration: none;
    color: #2ecc71;
    font-size: 0.85em;
    transition: all 0.3s ease;
    display: inline-block;
    margin-right: 10px;
    border-radius: 3px;
  }

  .link-btn:hover { 
    background: #2ecc71; 
    color: #0d1117; 
    box-shadow: 0 0 15px rgba(46, 204, 113, 0.4);
  }

  .lab-card {
    margin-bottom: 18px;
    border-left: 3px solid #2ecc71;
    padding-left: 20px;
    background: rgba(46, 204, 113, 0.03);
    padding-top: 5px;
    padding-bottom: 5px;
  }

  hr { border: 0; border-top: 1px solid #30363d; margin: 35px 0; }

  /* Blinking Cursor Styling */
  .typed-cursor {
    opacity: 1;
    color: #2ecc71;
  }
</style>

<div class="terminal-header">
  [root@bakhtiar ~]# <span id="typed-command"></span>
</div>

<img src="profile.jpg" width="140" class="profile-img" alt="Professional Profile">

<h2>Automation Engineer | Offensive Security Researcher 🛡️</h2>

<div style="margin-bottom: 25px;">
  <a href="https://www.linkedin.com/in/shaik-abdul-bakhtiar-b04aa3159" class="link-btn" target="_blank">🔗 LINKEDIN</a>
  <a href="https://www.instagram.com/bakhtiar.io" class="link-btn" target="_blank">📸 INSTAGRAM</a>
</div>

<blockquote>
  <strong>Experience:</strong> 3.5 Years in Software Quality Assurance & Automation Frameworks<br>
  <strong>Focus Areas:</strong> Vulnerability Assessment | Pentesting | OSINT Architecture
</blockquote>

<hr>

### 🛠️ Cybersecurity Lab Reports (Proof of Work)

<div class="lab-card">
  **[Vulnerability Assessment]** Network-wide audits utilizing **Nessus Essentials**. Identified, mapped, and prioritized critical vulnerabilities within Metasploitable environments.
</div>

<div class="lab-card">
  **[Penetration Testing]** Successfully exploited `vsftpd 2.3.4` backdoor to demonstrate root-level access and post-exploitation persistence in a controlled lab.
</div>

<div class="lab-card">
  **[OSINT & Recon]** Automated subdomain discovery via **Subfinder** and cross-platform identity mapping using **Sherlock** to build target footprints.
  <br><a href="recon_report.txt" class="link-btn" style="margin-top:12px;">VIEW FULL RECON REPORT</a>
</div>

<div class="lab-card">
  <h3 style="color: #00ff00; margin-bottom: 8px;">◈ Metasploitable 2: Full System Compromise</h3>
  <p style="font-size: 0.9em; line-height: 1.4;">
    Successfully exploited <strong>vsftpd 2.3.4</strong> backdoor to gain root access. 
    Performed credential harvesting via <strong>John the Ripper</strong> and established 
    persistent access via a custom <strong>sudoers</strong> backdoor.
  </p>
  
  <div style="margin-top: 15px; display: flex; gap: 10px;">
    <a href="reports/metasploitable-compromise.html" class="link-btn">VIEW EXPLOITATION REPORT</a>
    
    <a href="reports/recon-report.md" class="link-btn" style="background: transparent; border: 1px solid #00ff00;">RECON DATA</a>
  </div>
</div>

<hr>

### 🏆 Professional Impact & Awards
* <span class="highlight">Rising Star Award</span> – Engineered scalable **Selenium & TestNG frameworks** that reduced regression testing overhead by 40%.
* <span class="highlight">Pat on the Back</span> – Recognized for **Superior Defect Reporting** and identifying high-severity security leaks during UAT.

<hr>

### 🎓 Education & Certifications
* **MBA (Finance) & B.Tech (CS-IT)** – Specialized in bridging technical vulnerabilities with business risk management.
* **Ethical Hacking & Cyber Security** – [Active] Advanced training in offensive tactics and network defense.
* **CPSAT** – Certified Professional Selenium Automation Test Engineer.
* **Oxford Achievers** – High-level Professional Communication & English proficiency.

<hr>

### 📄 [Download My Full Resume (PDF)](./Shaik_Abdul_Bakhtiar_Automation_Security_Resume.pdf)

<p style="text-align: center; font-size: 0.75em; color: #8b949e; margin-top: 50px;">
  &copy; 2026 Bakhtiar. Generated via Secure Terminal Session.
</p>

<script>
  var typed = new Typed('#typed-command', {
    strings: [
      'whoami',
      'cat core_competencies.log',
      'nmap -sV labs.bakhtiar.io',
      'grep "Automation" skills.txt',
      './start_exploit_session.sh'
    ],
    typeSpeed: 50,
    backSpeed: 30,
    backDelay: 2000,
    loop: true,
    cursorChar: '_'
  });
</script>
