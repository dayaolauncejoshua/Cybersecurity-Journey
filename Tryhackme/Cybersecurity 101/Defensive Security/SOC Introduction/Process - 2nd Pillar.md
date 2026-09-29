**SOC Processes**

    A SOC does not just receive alerts. It follows a set of processes to determine what happened, how serious it is, and what action should be taken.

    The main processes here are:
    Alert Triage → Reporting → Incident Response & Forensics

**Alert Triage**

    Alert triage is the first analysis performed when a security alert is received.

    The goal is to:
    Understand what happened
    Determine whether the alert is actually malicious
    Determine its severity
    Prioritize the alert
    Decide whether it needs escalation

    A useful way to remember triage is the 5 Ws:
    What?	What happened?
    When?	When did it happen?
    Where?	Where did it happen?
    Who?	Who or what was involved?
    Why?	Why did it happen / what caused it?

    Example:
    Alert: Malware detected on Host: GEORGE PC

    What?  → Malicious file detected
    When?  → June 5, 2024 at 13:20
    Where? → GEORGE PC
    Who?   → User George
    Why?   → File was downloaded from a pirated software website

    The Why may require additional investigation. The alert itself might only say malware detected; the analyst gathers additional information to understand the circumstances.

    L1 SOC analysts commonly perform this initial triage.

**Reporting**

    If an alert is determined to be harmful or requires further investigation, it is escalated to the appropriate analyst/team. This is usually done through a ticket.

    A good security report should contain:
    The 5 Ws
    Investigation findings
    Relevant evidence
    Screenshots/logs when appropriate
    Severity and other relevant details

    The purpose is to give the next analyst enough information to continue the investigation without starting from zero.

    Simple example:
    Alert
    ↓
    L1 investigates
    ↓
    Findings documented
    ↓
    Ticket created
    ↓
    Escalated to L2/L3

**Incident Response and Forensics**

    Some alerts reveal activity serious enough to become a security incident.

    At this point, an incident response process may be initiated.

    Incident response focuses on containing and handling the incident, while forensics focuses on examining evidence to understand what happened.

    Forensics may examine artifacts such as:

    System logs
    Files
    Processes
    Network traffic
    Event logs
    Disk data

    The goal is to determine the root cause and understand what happened during the incident.

**Simple Difference**

    Alert Triage
        ↓
    "Is this suspicious? How serious is it?"

    Reporting
        ↓
    "Document and escalate the findings."

    Incident Response
        ↓
    "How do we contain and resolve the incident?"

    Forensics
        ↓
    "What exactly happened, and what evidence proves it?"

**Key Take:** 

    SOC processes turn raw security alerts into actionable investigations: triage the alert → document and escalate it → respond to serious incidents → use forensics when deeper evidence and root-cause analysis are required.
