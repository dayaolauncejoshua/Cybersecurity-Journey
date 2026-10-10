## Snort Usage: Rules, Testing & PCAP Analysis

### 1.Snort Rule Format

    A Snort rule defines which network traffic to detect and what action to take when traffic matches the rule.

    Example:

    alert icmp any any -> $HOME_NET any (msg:"Ping Detected"; sid:10001; rev:1;)

    This rule detects ICMP traffic (commonly used by ping) going toward the configured home network and generates an alert.


    Rule Components
        alert - Generate an alert when the rule matches
        icmp - Protocol to detect
        First any - Any source IP address
        Second any - Any source port
        -> - Traffic direction: source to destination
        $HOME_NET - Variable representing the protected network
        Final any - Any destination port
        msg - Message displayed in the alert
        sid - Unique Snort rule identifier
        rev - Rule revision number

    
    Important: ICMP does not use TCP/UDP ports. The any fields are part of Snort's general rule format; they do not mean ICMP has actual port numbers.

### Understanding the Rule

    alert icmp any any -> $HOME_NET any

    This means, Alert when ICMP traffic from any source is directed toward the configured home network.

    The rule's options provide the alert message and rule identification.

    SID: Identifies the rule.
    REV: Tracks rule revisions; increase it when modifying the rule.
    MSG: Explains what activity triggered the alert.

### 2.Creating a Custom Rule

    Snort allows administrators to create custom rules for traffic that built-in rules might not cover.

    Open the local rules file:
    sudo nano /etc/snort/rules/local.rules

    Add the following example:
    alert icmp any any -> 127.0.0.1 any (msg:"Loopback Ping Detected"; sid:10003; rev:1;)

    This rule detects ICMP traffic directed to 127.0.0.1, the loopback address used by a computer to communicate with itself.

    Save the file in Nano using Ctrl+X, then Y, then Enter.

### 3.Testing the Rule

    Start Snort:

    sudo snort -q -l /var/log/snort -i lo -A alert_fast -c /etc/snort/snort.lua

    Key options:
        -q - Quiet mode; reduces normal console output
        -l - Specifies the log directory
        -i lo - Monitors the loopback interface
        -A alert_fast - Displays alerts in a concise format
        -c - Specifies the configuration file

    Then, in another terminal, run:
        ping 127.0.0.1

        If the rule is loaded correctly and the traffic is visible to Snort, matching ICMP packets should generate an alert such as:

        "Loopback Ping Detected" {ICMP} 127.0.0.1 -> 127.0.0.1

        Why this matters: It demonstrates how a custom detection rule can identify specific network activity and produce an alert.


### 4.Running Snort on PCAP Files

    A PCAP file stores captured network packets. Instead of monitoring live traffic, Snort can analyze a saved capture for evidence of suspicious activity.

    Command: sudo snort -q -l /var/log/snort -r Task.pcap -A alert_fast -c /etc/snort/snort.lua

    The important option is:
    -r Task.pcap — reads packets from the saved capture file instead of a live network interface.

    Example Use Case

    After a suspected network attack, an investigator receives a PCAP file.

    They run Snort against it to check whether any packets match the configured detection rules. The resulting alerts can help identify suspicious traffic during the incident.

### Cybersecurity Key Takeaways

    Rules define what traffic Snort should detect.
    Custom rules let defenders monitor activity specific to their environment.
    SID identifies a rule; REV tracks its version.
    Live detection monitors traffic on a network interface.
    PCAP analysis checks previously captured traffic.
    Snort alerts indicate a rule match, not automatic proof that an attack succeeded. Analysts must investigate the surrounding evidence.