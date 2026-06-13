Nikto Vulnerability Scan Report

Overview

This project demonstrates the use of Nikto to perform a web server vulnerability assessment against a local DVWA (Damn Vulnerable Web Application) instance. The scan identifies potential security weaknesses, insecure configurations, and information disclosure issues.

---

Tool Used

- Tool: Nikto v2.5.0
- Platform: Kali Linux

---

Target Information

- Host: "127.0.0.1" (Local DVWA Server)
- Port: "80"

---

Scan Summary

The Nikto scan identified several potential vulnerabilities and insecure configurations within the test environment.

Key Findings

1. Missing Security Headers

- "X-Frame-Options" header was not present, increasing the risk of clickjacking attacks.
- "X-Content-Type-Options" header was missing, allowing browsers to perform MIME-type sniffing.

2. Server Information Disclosure

- ETag headers may expose file metadata and internal server details.
- Supported HTTP methods included:
  - "HEAD"
  - "GET"
  - "POST"
  - "OPTIONS"

3. Exposed Files and Misconfigurations

- Sensitive files and diagnostic pages were detected, including:
  - "phpinfo.php"
  - Apache "server-status"
- These resources may reveal internal server information that could assist an attacker during reconnaissance.

4. Potentially Dangerous Scripts

- The scan reported the presence of file manager and script paths that may indicate insecure or unintended deployments.
- Such findings should be investigated and removed if not required.

---

Risk Implications

- Exposure of system and software information.
- Increased attack surface due to unnecessary files and services.
- Possibility of unauthorized access to sensitive information.
- Greater susceptibility to client-side attacks because of missing security headers.

---

Recommendations

- Remove or restrict access to test and debugging files such as "phpinfo.php".
- Implement security headers including:
  - "X-Frame-Options"
  - "X-Content-Type-Options"
- Disable unnecessary HTTP methods.
- Restrict access to Apache "server-status".
- Review the web root for unauthorized scripts and remove them.
- Apply the principle of least privilege through proper file permissions.
- Perform regular vulnerability assessments and server hardening.

---

Included Files

- "Nikto_scan_results.txt" – Complete Nikto scan output.
- "README.md" – Findings, analysis, and remediation recommendations.

---

Demonstration Video

Google Drive Video:
https://drive.google.com/file/d/1wnirmwBgGyZLgNbMI5jDqC6oP4IRlXoq/view?usp=drivesdk

---

Legal Notice

This vulnerability assessment was conducted exclusively within a local DVWA test environment for educational purposes. Security testing should only be performed on systems that you own or for which you have obtained explicit authorization.
