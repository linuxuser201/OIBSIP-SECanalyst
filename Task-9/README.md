Task 9: SQL Injection Demonstration in DVWA

Objective

Demonstrate the impact of SQL Injection vulnerabilities using the Damn Vulnerable Web Application (DVWA) and discuss methods to mitigate such security flaws.

---

Environment Setup

- Application: Damn Vulnerable Web Application (DVWA)
- Security Level: Low
- Target Module: SQL Injection
- Access URL: "http://localhost/DVWA/vulnerabilities/sqli/"
- Platform: Kali Linux

---

Demonstration Video

Google Drive Video:
https://drive.google.com/file/d/1YAQADu8Aag7SO2mr6TQJUecexXW9EZWZ/view?usp=drivesdk

---

Vulnerability Description

The SQL Injection module in DVWA demonstrates how insufficient input validation can allow malicious input to alter the behavior of database queries.

The vulnerable parameter is the User ID field, which accepts user-supplied input without adequate sanitization.

---

Demonstration Details

During the exercise, the application accepted specially crafted input that modified the intended SQL query logic, resulting in the disclosure of additional database records beyond those requested by the user.

This illustrates how SQL Injection vulnerabilities can compromise the confidentiality of sensitive information stored within a database.

---

Impact

Potential consequences of SQL Injection vulnerabilities include:

- Unauthorized access to database records
- Disclosure of sensitive information
- Authentication bypass
- Modification or deletion of stored data
- Compromise of application integrity

---

Mitigation Strategies

To protect applications against SQL Injection attacks:

- Use prepared statements and parameterized queries.
- Validate and sanitize user input.
- Apply the principle of least privilege to database accounts.
- Implement secure error handling practices.
- Conduct regular security testing and code reviews.
- Utilize web application firewalls where appropriate.

---

Deliverables

- "README.md" – Documentation of the demonstration and mitigation techniques.
- Supporting screenshots or recordings of the exercise.
- Demo video link provided above.

---

Conclusion

This exercise demonstrated the risks associated with insecure database query construction and emphasized the importance of secure development practices. Understanding how SQL Injection vulnerabilities occur enables developers and security professionals to implement effective defensive measures and build more resilient applications.

---

Legal Notice

This demonstration was conducted exclusively within a controlled DVWA laboratory environment for educational purposes. Security testing should only be performed on systems that you own or for which you have explicit authorization.
