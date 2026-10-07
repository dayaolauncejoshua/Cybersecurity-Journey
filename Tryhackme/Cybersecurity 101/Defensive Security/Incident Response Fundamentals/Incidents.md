**Incident Response - Alerts & Incidents**

    1. Events

    An event is any activity that happens on a device or system and can be recorded.

    Examples:

    User logs in
    File is created
    Program starts
    USB is connected
    Network connection is made

    Both interactive and background processes generate events.

    Because devices generate large numbers of events, manually checking them is impractical.


    2. Logs

    Security solutions collect these events as logs.
    A log is a record of an activity.

    Example:
    13:20 - User: George
    13:20 - Login successful
    13:21 - powershell.exe started
    13:21 - Connection to 185.x.x.x

    Security tools such as SIEM and EDR analyze these logs to find suspicious patterns.


    3. Alert

    When a security solution detects something potentially dangerous, it creates an alert.
    Events → Logs → Security Tool → Suspicious Activity → Alert

    An alert means:
    "This activity may be dangerous. Investigate it."

    It does not automatically mean an attack occurred.


    4. False Positive

    A false positive is an alert that looks suspicious but is actually legitimate activity.

    Example
    A SIEM detects:
        "Large amount of data transferred to an external IP."

    The analyst investigates and discovers it was the company's scheduled cloud backup.

    Alert
    ↓
    Investigation
    ↓
    Legitimate backup
    ↓
    False Positive

    Why it matters?

    Too many false positives create alert fatigue. Analysts may waste time investigating harmless activity and potentially miss real threats.


    5. True Positive

    is an alert that correctly identifies genuinely malicious or harmful activity.

    Example

    A security tool detects a suspicious email containing a phishing link.

    The SOC investigates and confirms:
    The email is malicious
    The link leads to a credential-stealing website
    The attack targeted an employee


    6. False Positive vs True Positive

    False Positive - Alert triggered, but activity is legitimate. eg. Cloud backup
    True Positive - Alert triggered and activity is actually malicious. eg. Phishing attack


    Important SOC Concept

    An alert is not automatically an incident.
    The analyst must investigate first.

    Alert
    ↓
    Triage / Investigation
    ↓
    False Positive → Close
            OR
    True Positive → May become an Incident


    7. Security Incident
    A confirmed malicious event that requires a security response can be classified as a security incident.

    Examples:

    Malware infection
    Successful phishing attack
    Compromised account
    Unauthorized access
    Data theft
    Ransomware infection

    Once an incident is identified, the team determines its severity.


    8. Incident Severity
    Severity describes how serious an incident is and helps determine response priority.

    Levels are: Low → Medium → High → Critical

    Example

    Low:
    Suspicious activity on a test computer with no evidence of compromise.

    Medium:
    A normal employee account is compromised.

    High:
    Several company computers are infected with malware.

    Critical:
    Ransomware affects critical business servers and stops important operations.

    Severity is based on factors such as impact, affected systems, sensitivity of data, and urgency.


SOC Example

    Imagine an employee receives a phishing email.

    1. Event
    Employee receives email
            ↓
    2. Log
    Email security system records the message
            ↓
    3. Detection
    Security tool detects suspicious URL
            ↓
    4. Alert
    SOC receives phishing alert
            ↓
    5. Triage
    L1 analyst investigates
            ↓
    6. True Positive
    Email confirmed as phishing
            ↓
    7. Incident
    Employee clicked the malicious link
            ↓
    8. Severity
    Account credentials may have been compromised
            ↓
    9. Incident Response
    Account disabled/reset
    Malicious URL blocked
    Other users checked