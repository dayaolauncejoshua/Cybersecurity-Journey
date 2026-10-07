**Types of Security Incidents**

    In cybersecurity, incidents are categorized based on what happened and what was affected.
    An incident can involve multiple types at the same time.


**1.Malware Infection**

    Malware = malicious software designed to damage, disrupt, spy on, or gain unauthorized access to a system.

    Malware can arrive through:

     Email attachments
     Malicious downloads
     Compromised websites
     USB devices
     Exploited vulnerabilities


    Examples of malware include:

     Ransomware
     Trojan
     Spyware
     Worm
     Virus

    Employee receives email
            ↓
    Downloads malicious document
            ↓
    Malware executes
            ↓
    Computer becomes infected

    Malware infections are common SOC incidents. Analysts investigate how the malware entered, what it executed, and whether other systems were affected.


**2.Security Breach**

    A security breach occurs when an unauthorized person gains access to protected or confidential information.


    Attacker obtains employee credentials
            ↓
    Logs into company system
            ↓
    Accesses confidential customer records
            ↓
    Security Breach

    The focus is unauthorized access to protected information or systems.


**3.Data Leaks**

    A data leak occurs when a confidential or sensitive information becomes exposed to unauthorized people. Data leak does not necessarily need an attacker.

    It can happen because of:

    Human Error
    Misconfigured cloud storage
    Incorrect Permissions
    Accidental Email
    Malicious Activity
    Poor Security Practices


    Example:
    An employee with high position accidentally send a confidential email to a lower employee. 
    An employee accidentally uploads a company file in a public accessible cloud storage/folder.

    Confidential data
        ↓
    Incorrect permissions
        ↓
    Publicly accessible
        ↓
    Data Leak


    Security Breach vs Data Leak
    A useful distinction:

    Security breach → unauthorized access
    Data leak → unauthorized exposure

    They can overlap. For example, an attacker could breach an account and then leak the stolen data.


**4.Insider Attack**

    An insider attack occurs when someone in an organization abuses its legitimate access to perform malicious activity.

    The insider could be:

    Employee
    Contractor
    Administrator
    Other trusted user


    Example:
    Employee has legitimate network access
            ↓
    Employee intentionally connects infected USB
            ↓
    Malware spreads through network
            ↓
    Insider Attack

    Insider attacks can be particularly concerning because insiders may already have legitimate access and knowledge of internal systems.


**5.Denial of Service (DOS)**

    A DOS attack attempts to make a system, application, or network unavailable to legitimate users.

    The attacker sends excessive malicious request until the target's resources hits it limit of becomes exhausted.


    Normal:
    Users → Website → Website responds

    DoS:
    Attacker →→→→→ Website
            huge number of requests
                    ↓
            Resources exhausted
                    ↓
            Legitimate users ❌


    An online store normally handles 1,000 requests per minute. An attacker sends a huge number of requests, consuming the server's resources and preventing normal customers from accessing the website.

    Cybersecurity relevance: DoS primarily affects the Availability part of the CIA Triad.