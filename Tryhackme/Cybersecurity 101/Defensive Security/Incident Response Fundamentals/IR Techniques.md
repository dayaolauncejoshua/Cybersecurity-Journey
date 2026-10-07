**IR Techniques**

**1.Detection and Identification**

    The second phase is:
    
    SANS: Identification
    NIST: Detection & Analysis

    Manually searching for abnormal activity is difficult because organizations generate huge amounts of security data. Security tools help automate detection and analysis.

Common Security Solutions

    SIEM — Security Information and Event Management

    Collects important logs from many systems into one central location.
    Correlates events from different sources to identify suspicious activity or possible incidents.
    Example: SIEM sees multiple failed logins followed by a successful login and unusual data access.


    AV — Antivirus

    Detects and removes/blocks known malicious software.
    Regularly scans systems for malware.
    Example: AV detects a known ransomware file and blocks it.


    EDR — Endpoint Detection and Response

    Installed/active on endpoints such as computers and servers.
    Provides more detailed monitoring than traditional antivirus.
    Helps detect advanced or suspicious activity.
    Can also perform response actions such as isolating a machine or helping remove the threat.
    Example: EDR detects suspicious PowerShell activity and isolates the affected computer from the network.


    SIEM - Collects/correlates logs → detects incidents
    AV - Detects known malware
    EDR - Monitors endpoints → detects and responds to threats


**2.Playbooks**

    Once an incident is identified, the SOC needs to know what actions to take.

    Different incidents require different responses, so organizations create predefined procedures called playbooks.

    Playbook = Overall response guidelines

    A playbook describes what should generally be done when dealing with a particular type of incident.


    Example: PHISHING EMAIL PLAYBOOK

    1. Notify relevant stakeholders.
    2. Analyze the email header and body to 3. determine whether it is malicious.
    3. Analyze any attachments.
    4. Determine whether anyone opened the attachment.
    5. Isolate infected systems from the network.
    6. Block the sender.

    The playbook provides the overall response process so analysts don't have to figure everything out from scratch during an incident.


**3.Runbooks**

    A runbook is more detailed than a playbook.

    Playbook: What actions should be taken?
    Runbook: Exactly how should a specific action be performed?

    For example:

    Playbook:
    Isolate the infected computer.

    Runbook:
    1. Open the EDR console.
    2. Search for the affected hostname.
    3. Select the endpoint.
    4. Click Isolate Host.
    5. Confirm isolation.
    6. Verify that network communication has stopped.

    The exact runbook can vary depending on the organization's tools, infrastructure, and available resources.

    Simple Mental Model
    Security Tools → Detect Incident → Playbook → Runbook → Execute Response

    SIEM/EDR/AV = Detect the problem
    Playbook = The response plan
    Runbook = The detailed instructions for carrying out the plan
    SOC Analyst = Uses these resources to investigate and respond


**Cybersecurity Relevance**

    For a SOC L1 analyst, this is important because analysts commonly work from predefined playbooks and runbooks. They provide consistency, speed, and fewer mistakes during stressful incidents.

    Key takeaway: Playbooks define the response approach; runbooks provide the detailed execution steps.