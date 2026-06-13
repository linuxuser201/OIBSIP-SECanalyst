Task 10: Network Security Assessment Report

Objective

To assess the security posture of a local test network by identifying exposed services using Nmap and analyzing network traffic using Wireshark.

---

Tools Used

- Nmap 7.95 – Port scanning and service enumeration
- Wireshark – Packet capture and traffic analysis
- Platform: Kali Linux

---

Part 1: Nmap Network Scan

Command Executed

nmap -sS -sV -O -oN nmap_results.txt 192.168.1.19

Scan Results Summary

Parameter| Result
Target IP Address| 192.168.1.19
Host Status| Up
Open Port| 80/tcp
Service Detected| Apache httpd 2.4.63 (Debian)
Operating System| Linux 2.6.32 / 5.X / 6.X
Network Distance| 0 hops

Observations

- Only one open port, "80/tcp", was identified.
- The exposed service was an Apache HTTP server.
- Nmap identified the target as a Linux-based system with multiple possible kernel versions.
- The limited number of open ports suggests a reduced attack surface.

---

Part 2: Wireshark Traffic Analysis

Procedure

1. Started packet capture on the active network interface.
2. Generated HTTP traffic by visiting websites.
3. Applied the display filter:

http

4. Stopped the capture.
5. Saved the capture as "wireshark_capture.pcapng".
6. Analyzed the captured packets.

Packet Analysis Summary

No.| Source| Destination| Description
1207| 192.168.1.4| 34.223.124.45| HTTP GET request
1212| 34.223.124.45| 192.168.1.4| HTTP 200 OK response
1359| IPv6 Client| IPv6 Server| GET request to "/online"
1369| IPv6 Server| IPv6 Client| HTTP 301 redirect
1374| IPv6 Client| IPv6 Server| Follow-up GET request
1391| IPv6 Server| IPv6 Client| HTTP 200 OK response
1422| IPv6 Server| IPv6 Client| Favicon delivered successfully

Observations

- Standard HTTP requests and responses were captured successfully.
- Redirect behavior was observed through HTTP 301 responses.
- Browsers automatically followed redirects.
- Additional requests were generated for page assets such as favicons.
- Both IPv4 and IPv6 traffic were present.
- The observed traffic was unencrypted HTTP traffic.

---

Security Assessment Summary

Assessment Area| Observation| Recommendation
Web Server Exposure| Apache service accessible on Port 80| Keep services updated and properly hardened
Unencrypted Traffic| HTTP traffic observed without encryption| Implement HTTPS using TLS
Operating System Fingerprinting| Linux versions inferred through scanning| Minimize unnecessary service exposure
Attack Surface| Only one open port detected| Continue maintaining minimal exposure

---

Deliverables

- "nmap_results.txt" – Nmap scan output.
- "wireshark_capture.pcapng" – Network traffic capture.
- "README.md" – Documentation and assessment findings.

---

Demonstration Videos

Nmap Demonstration

Google Drive Video:
https://drive.google.com/file/d/1U7m_qdG_KwCry4gsGgagsAyxWhR1JhJy/view?usp=drivesdk

Wireshark Demonstration

Google Drive Video:
https://drive.google.com/file/d/1yV0pzsC-31E4jM_CMEnDrdJ33KygSdMC/view?usp=drivesdk

---

Conclusion

The assessment identified a relatively small attack surface, with only an HTTP service exposed on the target host. Traffic analysis revealed the use of unencrypted HTTP communications, highlighting the importance of adopting HTTPS to ensure confidentiality and integrity. Regular vulnerability assessments, service hardening, and secure communication practices remain essential components of maintaining a strong security posture.

---

