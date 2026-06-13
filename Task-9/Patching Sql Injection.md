Patching SQL Injection Vulnerabilities in DVWA

Introduction

SQL Injection is one of the most critical web application vulnerabilities. This document outlines secure coding practices that can be used to remediate the SQL Injection vulnerability demonstrated in the DVWA SQL Injection (Low) module.

---

Vulnerability Overview

The vulnerable implementation allows user-supplied input to be directly incorporated into an SQL query without proper validation or parameterization.

Vulnerable Query

SELECT first_name, last_name FROM users WHERE id = '$id';

Because the input is not securely handled, an attacker can manipulate the query logic and retrieve unintended data.

---

Remediation Strategies

1. Use Prepared Statements

Prepared statements separate SQL instructions from user input, preventing malicious data from being interpreted as executable SQL.

PHP (PDO)

$id = $_GET['id'];

$stmt = $pdo->prepare(
    "SELECT first_name, last_name FROM users WHERE id = ?"
    );

    $stmt->execute([$id]);

    $data = $stmt->fetchAll();

    PHP (MySQLi)

    $id = $_GET['id'];

    $stmt = $conn->prepare(
        "SELECT first_name, last_name FROM users WHERE id = ?"
        );

        $stmt->bind_param("i", $id);
        $stmt->execute();

        $result = $stmt->get_result();

        ---

        2. Validate User Input

        Ensure that all inputs conform to the expected format before processing.

        $id = filter_input(INPUT_GET, 'id', FILTER_VALIDATE_INT);

        Input validation reduces the likelihood of unexpected values reaching the database layer.

        ---

        3. Use Stored Procedures

        Encapsulating database operations within stored procedures can help reduce direct exposure of SQL queries.

        CREATE PROCEDURE getUserById(IN userId INT)
        BEGIN
            SELECT first_name, last_name
                FROM users
                    WHERE id = userId;
                    END;

                    ---

                    4. Apply the Principle of Least Privilege

                    Database accounts should only possess the permissions necessary for application functionality.

                    Recommended practices:

                    - Avoid using administrative database accounts.
                    - Grant only required privileges such as "SELECT", "INSERT", or "UPDATE".
                    - Restrict access to sensitive operations whenever possible.

                    ---

                    5. Implement Additional Security Controls

                    A Web Application Firewall (WAF) can provide an additional layer of defense by detecting and blocking known attack patterns.

                    Examples include:

                    - ModSecurity
                    - AWS WAF
                    - Cloudflare WAF

                    ---

                    Summary

                    Vulnerability| Recommended Control
                    Dynamic SQL Queries| Prepared Statements
                    Unvalidated Input| Input Validation
                    Excessive Database Permissions| Least Privilege
                    Direct Query Exposure| Stored Procedures
                    Lack of Layered Security| Web Application Firewall

                    ---

                    Conclusion

                    SQL Injection vulnerabilities can lead to unauthorized access to sensitive data and compromise the integrity of an application. Implementing prepared statements, validating input, enforcing least privilege, and adopting layered security controls significantly reduces the risk of exploitation.

                    This remediation exercise demonstrates the importance of secure coding practices and proactive security measures in the software development lifecycle.

                    ---

                    Legal Notice

                    The vulnerability demonstration and remediation discussed in this document were performed within the DVWA laboratory environment for educational purposes only. Security testing should only be conducted on systems that you own or have explicit authorization to assess.
