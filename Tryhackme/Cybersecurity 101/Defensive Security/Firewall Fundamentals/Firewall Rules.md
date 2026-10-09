**Firewall Rules**

    A firewall controls network traffic by applying rules that determine what traffic should be allowed, blocked, or forwarded.

    Rules can be customized based on the network's security requirements.

    Example

    A company may normally block SSH (TCP/22) from the Internet, but allow SSH from a trusted administrator's IP address.

        Allow SSH from trusted IP → Block SSH from everyone else

**Basic Firewall Rule Components**

    Source Address - IP address where the traffic originates.
    Destination Address - IP address receiving the traffic.
    Port - Port used by the traffic, e.g. 22, 80, 443
    Protocol - Communication protocol, eg. TCP, UDP, ICMP.
    Action - What the firewall should do with the traffic.
    Direction - Whether the rule applies to incoming or outgoing traffic.

    Example Rule:
    Action - Allow
    Source - 192.168.1.0/24
    Destination - Any
    Protocol - TCP
    Port - 80
    Direction - Outbound

    Allow devices in 192.168.1.0/24 to make outgoing TCP connections on port 80.

**Firewall Actions**

    1. Allow - Permits traffic that matches the rule.
    
    Example:
    Allow outbound HTTP traffic (TCP/80) from the internal network.

    Purpose: Allow legitimate/required communication.

    2. Deny - Blocks traffic that matches the rule.

    Example:
    Block incoming SSH traffic (TCP/22) to the internal network.

    Cybersecurity use: Block unauthorized access and reduce the network's attack surface.

    3. Forward - Redirects traffic to another destination/network segment.

    This is commonly used when a firewall also performs routing/gateway functions.

    Example:
    Forward incoming HTTP traffic (TCP/80) to the internal web server at 192.168.1.8.

    This is commonly associated with port forwarding.

**Direction of Firewall Rules**

    1. Inbound - Controls incoming traffic entering a network or device.

    Example: Allow inbound HTTPS (TCP/443) to a web server. Internet → Network

    2. Outbound - Controls traffic leaving a network or device.

    Example: Block outbound SMTP (TCP/25) from all computers except the organization's mail server.

    Outbound rules are useful for limiting data exfiltration and preventing compromised machines from communicating with unauthorized destinations.

    3. Forward - Controls traffic that enters one interface/network segment and is forwarded to another internal destination.

    Example: Internet → Firewall → Internal Web Server

    The firewall receives the traffic and forwards it to the appropriate server.



