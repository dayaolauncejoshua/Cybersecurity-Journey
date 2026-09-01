**Controlling Scan Speed and Timing**
    - Nmap provides timing templates to control how fast or slow a scan runs.
    - Scan speed matters because faster scans can generate more network traffic and may be detected by an IDS (Intrusion Detection System) or other security tools.
    - Nmap has six timing templates:
        1. Paranoid: -T0 Extreme slow
        2. Sneaky: -T1 Very Slow
        3. Polite: -T2 Slow
        4. Normal: -T3 Default Speed
        5. Aggressive: -T4 Fast
        6. Insane: -T5 Very Fast
    - Lower timing values (T0–T2) scan more slowly, while higher values (T4–T5) scan faster. Faster scans may be more noticeable and can also be less reliable on slow or unstable networks.

**Verbosity**
    - see more information about what Nmap is doing while the scan is still running
    - nmap -v <target>

**Saving Scan Report**
    - allows you to save scan results in different formats for later analysis.
    - **Output Formats**
        1. -oN <filename> — Normal output - Human readable output
        2. -oX <filename> — XML output - Structured format, useful for automated processing or importing into other tools.
        3. -oG <filename> — Grepable output - Designed to work easily with tools such as grep and awk.
        4. -oA <basename> - All major formats - Saves the scan results in multiple formats at once.
            - eg. nmap -oN scan.txt <target>
            - nmap -oA scan_results <target> - This creates multiple output files with the same basename in different formats