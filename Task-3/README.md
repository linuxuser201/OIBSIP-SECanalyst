DVWA SQL Injection Demonstration

Overview

This project demonstrates a basic SQL Injection attack on Damn Vulnerable Web Application (DVWA) with the security level configured to LOW.

---

Objective

To demonstrate how improper input validation can allow an attacker to manipulate SQL queries and retrieve unintended information from the database.

---

Environment

- Application: Damn Vulnerable Web Application (DVWA)
- Security Level: LOW
- Platform: Kali Linux
- Tool Used: Bash Script with "curl"

---

Demonstration Video

Google Drive Video:
https://drive.google.com/file/d/1vXWLCflgswdb1USkcTd5UHriOSh9DwCg/view?usp=drivesdk

---

Injection Payload Used

1' OR '1'='1

---

Script Used

./sql_injection_demo.sh

---

Expected Outcome

The injected payload alters the SQL query logic, causing the application to return multiple user records instead of information associated with a single user ID. This demonstrates the impact of insecure database query construction.

---

Conclusion

This exercise highlights the risks associated with unsanitized user input and emphasizes the importance of secure coding practices such as parameterized queries and prepared statements to mitigate SQL Injection vulnerabilities.
