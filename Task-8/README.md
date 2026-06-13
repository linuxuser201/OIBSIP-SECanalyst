Task 8: Capture Network Traffic with Wireshark

Objective

To capture and analyze HTTP network traffic using Wireshark and understand the HTTP request-response process through packet inspection.

---

Tools Used

- Tool: Wireshark
- Purpose: Network protocol analysis and packet inspection
- Platform: Kali Linux

---

Procedure

1. Installed and launched Wireshark.
2. Selected the active network interface.
3. Started packet capture.
4. Visited a website to generate HTTP traffic.
5. Applied the following display filter:

http

6. Stopped the capture after sufficient traffic had been collected.
7. Saved the captured packets as "wireshark_capture.pcap".
8. Examined the HTTP packets to identify requests, responses, and redirects.

---

Packet Analysis Summary

No.| Source| Destination| Description
1207| 192.168.1.4| 34.223.124.45| GET request for the root page
1212| 34.223.124.45| 192.168.1.4| HTTP 200 OK response containing HTML content
1359| 2401:4900:8fe...| 2600:1f13:37c...| GET request to "/online" over IPv6
1369| 2600:1f13:37c...| 2401:4900:8fe...| HTTP 301 redirect response
1374| 2401:4900:8fe...| 2600:1f13:37c...| Follow-up GET request to "/online/"
1391| 2600:1f13:37c...| 2401:4900:8fe...| HTTP 200 OK response
1396| 2401:4900:8fe...| 2600:1f13:37c...| Request for "favicon.ico"
1422| 2600:1f13:37c...| 2401:4900:8fe...| HTTP 200 OK response serving the favicon

---

Observations

- The client initiated a standard HTTP GET request to retrieve a webpage.
- The server returned a successful HTTP 200 OK response.
- One of the requests resulted in an HTTP 301 redirect.
- The browser automatically followed the redirect and requested the updated resource.
- Additional requests were generated to retrieve website assets such as the favicon.
- Both IPv4 and IPv6 traffic were observed during the capture session.

---

Deliverables

- "wireshark_capture.pcap" – Network capture containing HTTP traffic.
- "README.md" – Documentation and analysis of the captured packets.

---

Demonstration Video

Google Drive Video:
https://drive.google.com/file/d/1znDolRdaYUGGGSFJdkVbIgNCTbQTXY-7/view?usp=drivesdk

---

Conclusion

This exercise demonstrated how Wireshark can be used to inspect network communications and analyze the HTTP request-response cycle. The packet capture provided insight into web browsing behavior, server responses, redirection mechanisms, and the exchange of additional resources required to load a webpage. Such analysis is valuable for network troubleshooting, incident response, and cybersecurity investigations.
