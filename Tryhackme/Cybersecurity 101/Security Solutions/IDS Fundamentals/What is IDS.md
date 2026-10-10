**Intrusion Detection System (IDS)**

    An Intrusion Detection System (IDS) monitors network traffic or system activity to identify suspicious behavior, potential attacks, and security violations.

    When it detects suspicious activity, it generates an alert for security admins or SOC analysts. It generally detects and reports threats but does not automatically block them.

**How It Works**

    1. Monitor network traffic or system activity.
    2. Analyzes activity using detection methods.
    3. Identifies suspiacious patterns or anomalies.
    4. Generate an alert for investigation.

    Example: An attacker bypasses the firewall and begins scanning internal computers. The IDS detects the unusual scanning activity and alerts the SOC analyst.

**Detection Methods**

    1. Signature-based detection: Matches activity agains known attack patterns or signatures. Effective for known threats.

    2. Anomaly-based detection: Identifies activity that deviates from established normal behavior. Can detect previously unknown threats, but may generate false positives.

**Firewall vs IDS**

    Firewall controls which traffic is allowed or blocked, applies rules to network traffic and prevent unwanted connections.

    IDS monitors activity for suspicious behavior, analyzes traffic or system activity and detects potential attacks and generates alerts.

**Cybersecurity Relevance**

    An attacker may use a legitimate-looking connection to get past a firewall. An IDS provides another layer of security by detecting suspicious behavior that occurs afterward.

    A firewall helps control access; an IDS helps detect suspicious activity. An IDS typically alerts rather than blocks—automatic prevention is the role of an Intrusion Prevention System (IPS).