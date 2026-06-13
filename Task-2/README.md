UFW Configuration - Task 2

Objective

The objective of this task is to configure a basic firewall using UFW (Uncomplicated Firewall) on a Linux system. The firewall rules were configured to:

- Allow incoming SSH connections (Port 22)
- Deny incoming HTTP connections (Port 80)
- Verify that the configured rules are active

---

Tools Used

- Tool: UFW (Uncomplicated Firewall)
- Platform: Kali Linux

---

Configuration Steps

1. Allow SSH Connections

sudo ufw allow ssh

2. Deny HTTP Connections

sudo ufw deny http

3. Enable the Firewall

sudo ufw enable

4. Verify Firewall Status

sudo ufw status

---

Firewall Status

The configured firewall rules were successfully applied.

Port| Protocol| Action
22| TCP| ALLOW
80| TCP| DENY

The same rules were also applied for IPv6 traffic.

---

Demonstration Video

Google Drive Video:
https://drive.google.com/file/d/1KsGGZXmBN-tlXwUY1YxLfWJShC3xkbgn/view?usp=drivesdk

---

Conclusion

UFW was successfully configured to permit SSH access while blocking HTTP traffic. This exercise demonstrates the implementation of basic firewall rules to enhance system security and control incoming network connections.
