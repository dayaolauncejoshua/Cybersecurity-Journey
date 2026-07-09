Topic: TCP/IP and OSI Model

TCP/IP MODEL
What I learned:
- TCP/IP model defines four categories/layers that must occur in order for communications to be successful.
- It is a framework that defines how data travels from one device to another over a network or the Internet.
- IP (Internet Protocol) defines where data should go by using IP addressing(routing).
- TCP (Transmission Control Protocol) makes sure data arrives at its destination completely, correctly, and in the right order
- It divides into 4 Layers
    - Application = Provide network services to application (HTTP, HTTPS, FTP, DNS, SMTP, SSH)
    - Transport = Ensures data is delivered correctly (TCP) or quickly (UDP).
    - Internet = Finds the best path and delivers packets using IP addresses (IP, ICMP).
    - Network Access = Sends data over physical networks (Cables/Wi-Fi, Ethernet, ARP) 


Why it matters in Cybersecurity:
- This is used to understand/identify which layer attacks happen and how to defend against them.
- Examples:
    - Application Layer = Web attacks (SQL Injection, XSS, phishing websites).
    - Transport Layer = Port scanning, TCP SYN floods.
    - Internet Layer = IP spoofing, ICMP attacks.
    - Network Access Layer = ARP spoofing, MAC flooding.

-------------------------------------------------------------------------------------------------------------

OSI MODEL
What I learned:
- OSI model is a conceptual framework divided into 7 layers which explains how data travels from one device to another ocer a network.  
- It is mainly used for learning, troubleshooting, and analysis as each layer explains or it has specific responsibility. Unlike TCP/IP model which is used in real networks.
- The 7 Layers
    - Application = Provides network services to applications.
    - Presentation = Formats, encrypts, and compresses data. (SSL/TLS encryption, JPEG, MP4)
    - Session = Starts, manages, and ends communication sessions. (Login sessions, video calls)
    - Transport = Ensures reliable or fast data delivery. (TCP, UDP)
    - Network = Routes data between networks. 
    - Data Link = Delivers data within the same local network. (Ethernet, Wi-Fi, ARP, MAC addresses)
    - Physical = Transmits raw bits over cables or wireless signals. (Fiber optic cables, Ethernet cables, Wi-Fi radio signals)

Why it matters in Cybersecurity:
- This helps to identify where an attack occurs and which security controls should be used (Same answer as with TCP/IP but mainly OSI is more usable for analysis).
- Examples:
    - Layer 7 (Application): SQL Injection, Cross-Site Scripting (XSS), phishing websites.
    - Layer 4 (Transport): TCP SYN Flood (a type of DoS attack).
    - Layer 3 (Network): IP spoofing, ICMP abuse.
    - Layer 2 (Data Link): ARP spoofing, MAC flooding.
    - Layer 1 (Physical): Someone physically disconnecting or tapping a network cable.

