Nmap Scan Report - Task 1

Objective

Perform a network scan using Nmap to identify open ports, running services, and operating system information on the target machine.

---

Tools Used

- Tool: Nmap 7.95
- Platform: Kali Linux

---

Target Information

- Target IP Address: "192.168.1.27"

---

Demonstration Video

Google Drive Link: https://drive.google.com/file/d/1Op5xc9Pi9_mj_C0I4TbUtSGpq1VpDZnH/view?usp=drivesdk

---

Command Executed

nmap -sS -sV -O -oN nmap_results.txt 192.168.1.27

---

Scan Results

- Host Status: Up
- Open Ports: 80/tcp
- Service Detected: Apache httpd 2.4.63 (Debian)
- Device Type: General Purpose
- Operating System: Linux 2.6.32, Linux 5.0 - 6.2
- Network Distance: 0 hops

---

Output File

The scan results were saved to the following file:

scan_results.txt

---

Conclusion

The Nmap scan successfully identified the active host, detected the open HTTP service running on port 80, and provided operating system fingerprinting information. This exercise demonstrates the use of Nmap for basic network reconnaissance and service enumeration.
