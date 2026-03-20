---

## **Full-Spectrum Penetration Testing Report: Metasploitable 2**

**Target Host:** `192.168.56.101`  
**Security Analyst:** Shaik Abdul Bakhtiar  
**Date:** March 21, 2026  
**Status:** **Critical Risk (Full System Compromise)**

---

### **1. Executive Summary**
The objective of this assessment was to identify and exploit vulnerabilities within the target environment. The assessment was a complete success, resulting in **Root-level access**. The attack path began with an unauthenticated service exploit, followed by credential harvesting, database exfiltration, and the successful implementation of persistence mechanisms.

---

### **2. Technical Findings & Exploitation Path**

#### **Phase 1: Initial Access (CVE-2011-2523)**
* **Vulnerability:** The target was running `vsFTPd 2.3.4`, a version known to contain a malicious backdoor.
* **Exploitation:** By triggering the backdoor (using a specific string ending in `:)`), a listener was opened on port 6200.
* **Impact:** Immediate, unauthenticated **Root** shell access.

#### **Phase 2: Password Cracking & Credential Harvesting**
* **Shadow File Analysis:** I exfiltrated `/etc/passwd` and `/etc/shadow`.
* **Tooling:** Used **John the Ripper** with the `rockyou.txt` wordlist.
* **Results:** Successfully cracked passwords for system users:
    * `service`: `service`
    * `msfadmin`: `msfadmin`
    * `klog`: `identity`

#### **Phase 3: Database Compromise (Post-Exploitation)**
* **Sensitive File Discovery:** Identified a web configuration file at `/var/www/dvwa/config/config.inc.php`.
* **Observation:** The file revealed that the MySQL `root` user had **no password**.
* **Database Dump:** Logged into **MySQL** and dumped the `users` table from the `dvwa` database.
* **MD5 Cracking:** Used John the Ripper (`--format=Raw-MD5`) to crack web user hashes:
    * `admin`: `password`
    * `gordonb`: `abc123`
    * `1337`: `charley`

#### **Phase 4: Lateral Movement & Persistence**
* **SSH Access:** Verified that the system accepted legacy host keys (`ssh-rsa`).
* **Persistence Mechanism:** Created a new system user `sys_update` with a custom password.
* **Privilege Escalation:** Modified the `/etc/sudoers` file to grant `sys_update` passwordless sudo privileges (`NOPASSWD:ALL`).
* **Verification:** Confirmed that `sys_update` can log in via SSH and instantly switch to `root` using `sudo -i`.

---

### **3. Vulnerability Summary Table**

| Vulnerability | Severity | Description |
| :--- | :--- | :--- |
| **vsFTPd Backdoor** | **CRITICAL** | Allows remote attackers to execute arbitrary code as root. |
| **Weak Password Policy** | **HIGH** | System passwords were easily crackable via dictionary attacks. |
| **Insecure DB Config** | **HIGH** | MySQL root user had no password and credentials were in plaintext. |
| **Sudo Misconfiguration** | **MEDIUM** | Presence of NOPASSWD entries allows for trivial privilege escalation. |

---

### **4. Remediation Plan**
To secure the environment, the following actions are recommended:
1.  **Update Services:** Replace `vsFTPd 2.3.4` with a secure, modern FTP server or use SFTP.
2.  **Password Hardening:** Enforce a minimum password length and complexity. Rotate all compromised credentials.
3.  **Database Security:** Set a strong password for the MySQL `root` user and restrict file permissions on `config.inc.php`.
4.  **Audit Sudoers:** Regularly audit `/etc/sudoers` to ensure no unauthorized users have administrative rights.

---

### **Technical Skills Demonstrated**
* **Tools:** Nmap, Metasploit, John the Ripper, MySQL, SSH.
* **Skills:** Hash Cracking, Linux Administration, Privilege Escalation, Persistence, SQL Injection/DB Enumeration.

---
