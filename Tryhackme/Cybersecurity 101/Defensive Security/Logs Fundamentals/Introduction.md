**Logs Fundamentals Introduction**

    1. What are Logs? 

    Attackers often try to avoid leaving traces so they are harder to detect. However, their activities can still leave evidence across different parts of a system.

    These digital traces are commonly found in logs. 

    Log is a record of an activity or event.

    Logs record activities happening on a:

    Computer
    Server
    Network
    Application
    Security device
    Cloud service
    etc.

    The activity can be legitimate or malicious.

    Example:
    A user logs in:
        User: John — Login successful — 09:15

    This is a normal activity.

    An attacker attempts multiple logins:

        Failed login — admin — 09:16
        Failed login — admin — 09:16
        Failed login — admin — 09:17
        Successful login — admin — 09:17

    These logs could provide evidence of a brute-force attack.


    2. Logs as Digital Footprints

    Logs are like footprints at a crime scene.

    In cybersecurity:
    Login logs + network logs + endpoint logs + application logs -> reconstruct what happened

    No single log may tell the entire story. Security analysts often correlate multiple logs to understand the complete attack.

    Example:

    An attacker compromises an employee account:

    Authentication log: Successful login from an unusual location.
    Endpoint log: PowerShell starts.
    Network log: Large connection to an external IP.
    File log: Sensitive files are accessed.
    Firewall log: Connection to a suspicious external server.

    Individually, these events may not prove much.

    Account compromise → malicious activity → data access → possible data exfiltration

    This is why logs are extremely important in SOC and incident response.


    3. Main Uses of Logs

    3.1. Security Event Monitoring

    Logs help security teams detect suspicious or abnormal behavior, especially when monitoring occurs in real time.

    Example:

    Hundreds of failed login attempts within a few minutes could indicate a brute-force attack.

    3.2. Incident Investigation & Digital Forensics

    Logs provide evidence about what happened during an incident.

    They can help answer:
    What happened?
    When did it happen?
    Which system was affected?
    Which account was involved?
    What actions were performed?
    Where did the activity come from?

    Logs can also help determine the root cause of an incident.

    Example:

    Logs may show that an attacker entered through a vulnerable web application and then accessed sensitive files.


    3.3. Troubleshooting

    Logs are not only for cybersecurity.
    Applications and operating systems also record errors and failures.

    Example:

    A server keeps crashing. Its logs may show:
    Database connection failed

    This helps the administrator identify and fix the problem.


    3.4 Performance Monitoring

    Logs can provide information about how well systems and applications are performing.

    Example:
    Application logs show that response times increased from 200 ms to 5 seconds.

    This could indicate a performance problem that needs investigation.


    3.5 Auditing & Compliance

    Logs create a record of activities, which can help organizations demonstrate that systems and users are following required policies or regulations.

    Example:

    An organization may need to know:
    Who accessed a sensitive database, when they accessed it, and what they did.

    Logs can provide an activity trail for this purpose.


**Simple Mental Model**

    Logs = Digital Footprints

    They can be used for:
    Detect → Investigate → Troubleshoot → Monitor → Audit

**Cybersecurity Relevance**

    For a SOC analyst, logs are one of the most important sources of evidence.

    A security alert tells the analyst:
    "Something suspicious may have happened."

    Logs help answer:
    "What actually happened?"

    This is why SOC analysts need to understand different types of logs and how to investigate them.


**Key:**

    Logs are records of system, user, application, and network activities. They act as digital footprints that help security teams detect attacks, investigate incidents, determine root causes, troubleshoot problems, monitor performance, and maintain audit trails.