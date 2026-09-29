**SOC: Detection, Response, and the 3 Pillars**

    Detection and Response are the main purpose of SOC to maintain.
    The SOC continuously monitors the organization's environment so threats can be detected and handled quickly.

**Detection**

    1. Detect Vulnerabilities - Find weaknesses that attackers could exploit.

    Example:
    Windows computers
        ↓
    Missing security patch
        ↓
    Known vulnerability
        ↓
    SOC/security team identifies the risk

    Vulnerability management may belong to another team, but unpatched vulnerabilities still affect the organization's overall security.


    2. Detect Unauthorized Activity - Identify activity from someone who shouldn't have access.

    Example:
    Employee account
        ↓
    Login from unusual location
        ↓
    SOC investigates
        ↓
    Possible compromised account

    Other clues can include unusual login times, devices, IP addresses, or behavior.


    3. Detect Policy Violations

    Identify activity that violates the organization's security rules.

    Examples:
        Downloading prohibited/pirated files
        Sending confidential information through an insecure method
        Using unauthorized software

    What counts as a violation depends on the organization's policies.

    
    4. Detect Intrusions

    Detect when an attacker gained unauthorized access.
    
    Examples:
    Web application exploited -> Unauthorized Access

    Employee visits malicious website -> Malware infects computer -> SOC detects suspicious activity

**Response**

    When a security incident is detected, the SOC helps with incident response.

    The goal is to:
    1. Contain/minimize the damage.
    2. Investigate what happened.
    3. Find the root cause
    4. Help restore security

    Example:

    Alert
    ↓
    Investigate
    ↓
    Confirm incident
    ↓
    Contain threat
    ↓
    Find root cause
    ↓
    Recover

**The 3 Pillars of a SOC**

    A mature SOC depends on three things:

    1. People - The security professionals who perform the work.

    SOC Analyst L1
    SOC Analyst L2
    Incident Responder
    Threat Hunter
    SOC Manager
        
    2. Process - The procedures that tell the team what to do and when to do it.

    Incident response procedures
    Alert triage procedures
    Escalation procedures
    Documentation

    3. Technology - The security tools used to monitor and protect the environment.

    SIEM → collects and analyzes logs
    EDR → monitors endpoints/computers
    IDS/IPS → detects or blocks suspicious network activity
    Firewalls → control network traffic
    Threat Intelligence → provides information about known threats
    SOAR → automates security response tasks

    People use Technology according to established Processes to achieve effective Detection and Response.