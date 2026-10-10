**SIEM - Core Features**

    SIEM (Security Information and Event Management) is a security solution that:
    Collects → Normalizes → Correlates → Analyzes → Detects → Alerts

    It gathers logs from many sources and turns them into useful security information.

**Core SIEM Features**

    1. Centralized Log Collection - SIEM collects logs from different sources into one central location.
    
    Sources can include Windows/Linux, Servers, Firewalls, EDR, Applications, Network devices

    Logs can be collected through agents or APIs.

    This makes investigations much faster.


    2. Log Parsing & Normalization 

    Different systems produce logs in different formats.
    Parsing = breaking a raw log into individual fields.

    For example:
    192.168.1.10 GET /login 401

    can be broken into:
    IP       = 192.168.1.10
    Method   = GET
    URL      = /login
    Status   = 401

    Normalization = converting information from different log sources into a consistent structure/format. Make different logs follow a consistent format.

    This allows the SIEM to analyze different sources together.


    3. Log Correlation

    Correlation = Connecting events from different logs to identify a meaningful pattern.
    One event may look completely normal.

    Example:
    VPN login
    File access
    PowerShell execution
    Outbound network connection

    Individually, these may not be suspicious.

    But suppose they happen within 5 minutes:
    Unusual VPN login
        ↓
    Sensitive files accessed
        ↓
    PowerShell executed
        ↓
    Outbound connection
        ↓
    Possible data exfiltration

    The SIEM can correlate these events and identify a potentially suspicious sequence.
    This is one of the most important concepts in SIEM.


    4. Real-Time Alerting

    SIEM uses detection rules to identify suspicious activity.

    Example rule: If there are 20 failed logins from the same IP within 5 minutes → generate an alert.

    When the rule's conditions are met:
    Events → Detection Rule → Alert → SOC Analyst

    SIEMs often have predefined rules, but security analysts can also create/customize rules based on the organization's environment.


    5. Dashboards & Reporting

    SIEMs provide dashboards that summarize security activity.

    Examples:
    Number of alerts
    Failed login attempts
    Triggered detection rules
    Events ingested
    System health
    Frequently visited domains
    Security notifications

    Instead of reading thousands of raw logs, analysts can get a visual overview of what's happening.

**Simple SIEM Mental Model**

    Log Sources -> Centralized Collection -> Parsing -> Normalization -> Correlation -> Detection Rules -> Alert -> SOC Analyst Investigation

    Example
    Windows Login + VPN Login + PowerShell + Outbound Connection -> SIEM -> Correlation -> Suspicious Pattern -> ALERT -> SOC investigates

**Cybersecurity Note**

    For a SOC L1 analyst, SIEM is one of the primary places where alerts are received and investigated.
    
    The analyst needs to understand:
    Where the event came from
    What happened
    When it happened
    Which user/device was involved
    Whether multiple events are connected
    Whether it is a true or false positive

    SIEM turns huge amounts of raw logs into useful security information by collecting, parsing, normalizing, correlating, and analyzing them, then generating alerts when suspicious patterns are detected.
    