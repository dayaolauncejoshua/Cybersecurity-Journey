**Snort**

    Snort is an open-source network security tool originally released in 1998. It monitors network traffic and can detect suspicious or malicious activity by matching packets against rules.

    Snort is commonly used as a Network Intrusion Detection System (NIDS).

**How Snort Detects Threats**
    
    Built-in rules: Detect traffic patterns associated with known threats.
    Custom rules: Allow administrators to detect specific traffic based on their network's needs.
    Rule management: Administrators can enable or disable rules depending on their environment.

    Example: A Snort rule detects traffic matching a known attack pattern and generates an alert for the security team.

**Three Snort Modes**

    1. Packet Sniffer Mode

        Captures and displays network packets.
        Does not perform IDS rule-based detection in this mode.
        Useful for troubleshooting and observing network traffic.

        Example: A network administrator inspects packets to investigate slow network performance.

    
    2. Packet Logging Mode

        Captures network traffic and saves it for later analysis, commonly in PCAP format.
        Useful for incident investigation and digital forensics.
        Captured traffic can be reviewed using packet analysis tools such as Wireshark.

        Example: After a suspected attack, investigators examine saved packets to understand how the communication occurred.

    
    3. Network Intrusion Detection System (NIDS) Mode

        Monitors network traffic in real time.
        Applies Snort rules to identify suspicious patterns.
        Generates alerts when traffic matches configured rules.

        Example: Snort detects traffic matching a known exploit signature and alerts the SOC analyst.

        This is Snort's primary mode for IDS monitoring and detection.

**Quick Comparison**

    Packet Sniffer - Observe traffic, Packets displayed
    Packet Logging - Save traffic (PCAP) for later, PCAP/log files
    NIDS - Detect suspicious traffic, Alerts

**Cybersecurity Relevance**

    SOC analysts and network defenders can use Snort to detect suspicious network traffic, investigate alerts, and support incident response.

    Snort can observe, record, or detect network traffic depending on the mode used. NIDS mode is the key mode for detecting threats and generating alerts.