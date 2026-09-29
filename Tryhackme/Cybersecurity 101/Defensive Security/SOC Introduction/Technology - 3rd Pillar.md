**Technology in a SOC**

    People + Processes + Technology all work together. Security tools reduce the amount of manual work SOC analysts need to do by collecting data, detecting threats, and sometimes automatically responding to them.

    Without security tools, analysts would have to manually check every computer, server, application, and network device.

    Why Technology Is Needed

    Imagine a company has:

    500 computers
    50 servers
    Network devices
    Cloud applications
    Web applications

    Checking each system individually for suspicious activity would be extremely difficult.

    Security solutions centralize information and automate parts of detection and response:
    Computers ─┐    
    Servers   ─┤
    Firewalls ─┤
    Apps      ─┤ → Security Tools → SOC Analysts
    Network   ─┘

**SIEM (Security Information and Event Management)**

    A SIEM collects and analyzes logs from many different sources.

    Examples of log sources:
    Windows computers
    Linux servers
    Firewalls
    Applications
    Authentication systems
    Network devices

    The SIEM can apply detection rules to this data.

    For example:

    Failed login
        ↓
    Failed login
        ↓
    Failed login
        ↓
    Successful login
        ↓
    🚨 Suspicious activity

    The SIEM can correlate events from multiple sources and generate an alert for the SOC.

    Modern SIEMs can also use:
    User/entity behavior analytics
    Threat intelligence
    Machine learning

    Key idea: SIEM mainly provides centralized log collection, analysis, and detection.
    Important: In the simplified SOC model used here, SIEM is primarily associated with Detection, while tools such as EDR and SOAR can provide response capabilities.

**EDR (Endpoint Detection and Response)**

    EDR focuses specifically on endpoints, such as:
    PCs
    Laptops
    Servers
    Workstations

    It provides detailed visibility into what is happening on those machines.

    For example, an EDR might show:
    User opens suspicious file
            ↓
    PowerShell starts
            ↓
    Unknown process created
            ↓
    Process connects to suspicious IP
            ↓
    🚨 EDR Alert

    Unlike a basic log collection system, EDR can often take action automatically or with a few clicks, such as isolating a compromised endpoint.

    Key idea: EDR = detailed endpoint visibility + detection + response.

**Firewall**

    A firewall controls network traffic between networks or systems.
    For example:
    Internet
    ↓
    [ Firewall ]
    ↓
    Internal Network

    It examines incoming and outgoing traffic and can allow or block traffic according to configured rules.
    Example:
    Internet → Server : TCP 443 → ✅ Allow
    Internet → Server : TCP 23  → ❌ Block

    Firewalls can also have security detection capabilities that identify and block suspicious traffic.

    Key idea: Firewall = controls and filters network traffic. 

**Other SOC Technologies**

    Antivirus - Detects and removes malicious software
    EPP	- Prevents threats on endpoints
    IDS/IPS	- Detects and/or blocks suspicious network activity
    XDR	- Correlates security data across multiple security layers
    SOAR - Automates security investigation and response workflows
    SIEM - Centralizes logs and performs security detection/analysis
    EDR	- Detects and responds to endpoint threats
    Firewall - Controls network traffic

    Important Point:

    There is no single security tool that does everything.

    An organization chooses its technology based on factors such as:

    Its threat surface
    Size of the organization
    Security requirements
    Available budget/resources
    Existing infrastructure

**SOC Technology Mental Model**

                SOC TECHNOLOGY

       ┌────────────┬────────────┐
       │            │            │
     SIEM          EDR        Firewall
    Logs/Detect   Endpoint      Network
       │          Detect/       Traffic
       │          Respond       Control
       └────────────┬───────────┘
                    ↓
               SOC Analysts
                    ↓
            Investigate & Respond

    Key takeaway: Technology gives the SOC the visibility and automation needed to detect and respond to threats at scale. People make the decisions, processes provide the workflow, and technology provides the capabilities.