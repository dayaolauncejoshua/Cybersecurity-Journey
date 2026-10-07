**Incident Response Frameworks**

    Handling different security incidents can become confusing without a structured process.

    An Incident Response Framework provides a standard approach for responding to incidents in an organized way.

**Two commonly referenced frameworks are:**

    SANS Incident Response Framework
    NIST Incident Response Framework

    They have similar concepts and help organizations build their own incident response procedures.


**SANS Framework**

    The SANS framework has 6 phases - PICERL :
      Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned

    
    1. PREPARATION - Get Ready
    Prepare the organization before an incident happens.

    This includes:
    Creating incident response team
    Creating incident response plan
    Deploy security tools
    Training employees

    Example:
    Employees recieve phishing-awareness training program so they wil be less likely to fall for malicious emails.


    2. IDENTIFICATION
    Determin wether a suspicious activity is actually a security incident.

    SOC tools and analysts may detect:

    Unusual network traffic 
    Suspicious logins
    Malware
    Unusual file activity

    Example:
    Large amount of data leaving a computer
                ↓
        SOC investigates
                ↓
    Phishing attachment caused malware infection

    Goal: Identify what happened and determine whether an incident exists.


    3. CONTAINMENT
    Once an incident is confirmed, limit its impact.

    Examples:
    Isolate affected computer
    Disable compromised account
    Block malicious IP Address
    Disconnect affected systems

    Example:
    Compromised PC
        ↓
    Network isolation
        ↓
    Attacker cannot easily reach other systems

    Goal: Prevent the incident from spreading or causing additional damage.


    4. ERADICATION - Remove the threat
    After containing the incident, remove the cause of compromise.

    Examples:
    Remove malware
    Delete malicious files
    Remove persistence mechanisms
    Patch the exploited vulnerabilities
    Reset compromised credentials

    Example:
    A malware scan finds and removes the malicious software from the infected computer.

    Goal: Make sure the threat is removed.


    5. RECOVERY - Restore Normal Operations
    Return affected systems to safe, working state. 

    This can involve:
    Restoring Backups
    Rebuilding Systems
    Reconfiguring Systems
    Testing systems before putting them back to production
    Monitoring for additional suspicious activity

    Goal: Safely return the organization to normal operations.


    6. LESSONS LEARNED — Improve
    After the incident, the organization reviews what happened.

    Questions include:

    What caused the incident?
    What worked?
    What failed?
    Why wasn't it detected earlier?
    How can it be prevented or detected faster next time?

    Example:
    After a phishing incident, the organization improves email filtering and provides additional employee training.

    Goal: Learn from the incident and improve security.


**NIST Incident Response Framework**

    The traditional NIST incident response lifecycle has 4 main phases:

    1. Preparation
    Prepare people, tools, policies, and procedures before an incident.
    Example: Configure SIEM alerts, create an IR plan, train SOC analysts.


    2. Detection & Analysis
    Detect suspicious activity and determine whether it is actually an incident.
    Analyze logs, alerts, endpoint data, network traffic, etc.
    Example: SIEM detects unusual login → SOC investigates → confirms compromised account.


    3. Containment, Eradication & Recovery
    Containment: Limit the damage/spread.
    Eradication: Remove the threat and its cause.
    Recovery: Restore affected systems to normal operation.
    Example: Isolate infected PC → remove malware → patch vulnerability → restore system.


    4. Post-Incident Activity
    Review what happened and improve defenses.
    Document findings, identify weaknesses, and update procedures.
    Example: Determine why phishing succeeded and improve email filtering/training.


    Key point: The frameworks use different phase groupings, but the overall goal is similar


**Incident Response Plan**

    An Incident Response Plan (IRP) is the organization's formal document describing how it will respond to security incidents. It provides specific procedures to follow before, during, and after an incident.

    Typical contents include:
    Roles & Responsibilities

    Who does what?

    Example:
    L1 investigates the alert → L2 performs deeper investigation → Incident Response team handles major incidents.


    Incident Response Methodology
    What process should the organization follow?

    For example:
    Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned

    
    Communication Plan
    Who needs to be informed?

    This can include:
    Security team
    Management
    IT teams
    Legal
    Relevant stakeholders
    Law enforcement, when appropriate
    Escalation Path

    Defines when and to whom an incident should be escalated.

    Example:
    L1 Analyst
        ↓
    L2 Analyst
        ↓
    L3 / Incident Response
        ↓
    Management / CISO


**Cybersecurity Relevance**

    As a SOC analyst, an important distinction is:
    Alert triage answers:
    "Is this alert actually a threat?"

    Incident response answers:
    "Now that we have a real incident, how do we contain, remove, and recover from it?"

    Key Takeaway
    Incident Response Framework = structured method for handling security incidents.