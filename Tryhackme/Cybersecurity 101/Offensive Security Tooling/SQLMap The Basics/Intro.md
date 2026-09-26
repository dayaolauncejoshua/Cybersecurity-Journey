**Where SQL Injection Comes In**

    The important cybersecurity issue is that user input can sometimes become part of an SQL query.

    If the application doesn't properly handle that input, an attacker may be able to manipulate the SQL query instead of simply providing normal data.

**Normal:**

    User Input
        ↓
    Web Application
        ↓
    SQL Query
        ↓
    Database

**SQL Injection:**

    Malicious Input
        ↓
    Web Application
        ↓
    Manipulated SQL Query
        ↓
    Database

    This can potentially allow unauthorized actions such as bypassing authentication, reading data, modifying data, or deleting data, depending on the vulnerability and database permissions.

**Key Takeaway**

    Web applications use SQL queries to communicate with databases. SQL Injection occurs when untrusted user input can alter the intended SQL query.