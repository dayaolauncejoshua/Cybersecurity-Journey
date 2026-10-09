**Windows Defender Firewall**

    Windows Defender Firewall is the built-in firewall in Windows. It controls incoming and outgoing network traffic based on configured rules.

    Simple example
    Suppose an application on your PC wants to receive connections:

    Internet → Your PC → Application

    Windows Defender Firewall checks its rules:

    Allowed → traffic can reach the application
    Blocked → traffic is stopped

**What it can control**

    Firewall rules can be based on things like:
    Program/application
    Port — e.g., TCP 22, 80, 443
    Protocol — TCP/UDP
    IP address
    Inbound vs outbound traffic

**Firewall Profiles**

    Windows has different profiles depending on the network:
    Domain — organization/domain network
    Private — trusted networks, such as home
    Public — untrusted networks, such as public Wi-Fi

**Cybersecurity relevance**

    Windows Defender Firewall helps reduce the attack surface of a Windows machine by preventing unauthorized network connections.