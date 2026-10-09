**IDS Types: Deployment & Detection Modes**

    An IDS is categorized based on where it monitors and how it detect threats.

**1.Deployment Modes - Where does it monitor?**

    Host-Based IDS (HIDS)

        Installed on an individual computer or server.
        Monitors activity on that specific host, such as file changes, system logs, and suspicious processes.
        Provides detailed visibility into the host's activity.
        Limitation: Managing and maintaining it across many computers can be resource-intensive.

        Example: HIDS detects an unexpected change to a critical system file on a Windows server.
    

    Network-Based IDS (NIDS)

        Monitors network traffic across a network segment.
        Can detect suspicious communication involving multiple devices.
        Provides centralized visibility into network activity.

        Example: NIDS detects one computer repeatedly scanning the ports of other computers.

    HIDS = Happening on a device
    NIDS = Happening across the network

**2.Detection Modes - How does it detect threats**

    Signature-Based IDS

        Compares activity against a database of known attack patterns (signatures).
        Quickly detects threats with matching signatures.
        Requires updated signatures to recognize new threats.
        Usually cannot detect a genuinely new attack if no matching signature exists.

        Example: Detects network traffic matching a known malware communication pattern.

        Limitation: May miss zero-day attacks that lack known signatures.


    Anomaly-Based IDS

        Learns or uses a defined baseline of normal system or network behavior.
        Alerts when activity significantly deviates from that baseline.
        Can detect previously unknown attacks, including some zero-day attacks.
        May generate more false positives when legitimate activity looks unusual.

        Example: A computer that normally sends small amounts of data suddenly transfers several gigabytes to an unfamiliar external server.

        Reducing false positives: Tune detection thresholds and baselines to reflect legitimate network activity.

    
    Hybrid IDS

        Combines signature-based and anomaly-based detection.
        Detects known threats using signatures and can identify unusual behavior that signatures may miss.
        Offers broader detection coverage, but can require more processing and tuning.

        Example: A hybrid IDS detects known malware through its signature and flags unusual outbound traffic through anomaly detection.

    