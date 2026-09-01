**Nmap**
    - Nmap (Network Mapper) is an open-source network scanning tool used to efficiently discover hosts and services on a network.

    - Instead of manually checking every IP address and port, Nmap can automate the process.
        - Nmap can be used to:
            - Discover live hosts
            - Scan open ports
            - Identify running services
            - Detect service versions
            - Perform different types of port scans
            - Control scan timing
            - Format and save scan results

**Nmap TCP Port Scanning**
    - A network service is a process listening for incoming connections on a TCP or UDP port.
    - Common examples:
        - Web servers → TCP 80 (HTTP), 443 (HTTPS)
        - DNS → Port 53 (UDP/TCP)
    - TCP and UDP each have 65,535 ports.
    - Nmap can scan ports to determine which ones are open and have services listening.

**TCP Connect Scan (-sT)**
    -Attempts to complete the full TCP three-way handshake.
    - Open port response:
        SYN → SYN-ACK → ACK
        Connection is established.
        Nmap then terminates the connection.
    - Closed port response:
        SYN → RST/RST-ACK
        Command:
        nmap -sT <target>

**SYN Scan (-sS)**
    - Sends only the initial SYN packet.
    - Does not complete the TCP three-way handshake.
    - Open port response:
        SYN → SYN-ACK
        Nmap sends RST instead of the final ACK.
    - Closed port response:
        SYN → RST/RST-ACK
        Often called a stealth scan because a full TCP connection is not established.
    - Command:
    - nmap -sS <target>

**Key Difference**
Connect Scan (-sT) → Completes the TCP three-way handshake.
SYN Scan (-sS) → Checks the response without completing the handshake.

**Nmap UDP Port Scanning**
    - UDP is connectionless, meaning it does not use a TCP-style three-way handshake. It is also useful for real-time communication where speed is important.
**UDP Scan with Nmap**
    - To scan UDP ports, use:
        nmap -sU <target>
**How Nmap identifies closed UDP ports**
    - When Nmap sends a UDP packet to a closed UDP port, the target commonly responds with:
        1. ICMP Destination Unreachable
        2. Port Unreachable

**UDP scanning is different from TCP scanning because UDP does not establish a connection. Nmap often identifies closed UDP ports through ICMP "Port Unreachable" responses.**

**Limiting Target Ports in Nmap**
    - By default, Nmap scans the 1,000 most common ports. You can change this depending on your needs.
    - **Fast Scan: -F**
        - Scan only 100 most common ports. eg. nmap -F <target>
        - for quicker scan
    - **Specify Ports: -p**
        - choose specific ports or ranges. eg. Scan ports 10 to 1024:
            - nmap -p10-1024 <target>
    - **Well-Known Ports**
        - Ports 1–1023 are commonly called well-known ports because many standard services use them. eg. nmap -p1-1023 <target>
        - well known ports used for DNS, HTTP, HTTPS, SSH, etc
    - Additionals 
        - OS detection: -O
        - Service version: -sV
        - Forcing scan: -Pn
            - Normally, Nmap first performs host discovery to check whether a target is online before scanning its ports.
            - However, a host might be online but not respond to discovery probes, such as ICMP ping requests. In this case, Nmap may assume the host is down and skip the port scan.
            - -Pn skips host discovery and forces Nmap to attempt a port scan even if the target does not respond to ping or other discovery probes.