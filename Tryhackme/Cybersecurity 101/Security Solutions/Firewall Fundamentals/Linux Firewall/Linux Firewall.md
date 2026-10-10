**Linux Firewall — Netfilter & UFW**

Netfilter

    Netfilter is the firewall framework built into the Linux kernel.

    It provides core networking security functions such as:
    Packet filtering — allow/block network traffic
    NAT — translate IP addresses
    Connection tracking — track network connections

    Netfilter as the engine, while tools such as iptables, nftables, firewalld, and ufw are ways to configure/control that engine.

Common Netfilter Utilities

    iptables - Traditional and widely used interface for configuring Netfilter
    nftables - Modern successor to iptables with improved filtering/NAT capabilities
    firewalld - Firewall management tool with predefined network zones
    ufw - Beginner-friendly interface that simplifies firewall configuration

**UFW — Uncomplicated Firewall**

    UFW provides a simpler command-line interface for configuring Linux firewall rules.

    Instead of writing complex iptables rules, administrators can use simpler commands.

    Check Firewall Status:
    sudo ufw status

    Example:
    Status: inactive

    Enable Firewall:
    sudo ufw enable

    To disable it:
    sudo ufw disable


    Default Traffic Policy

    For example: sudo ufw default allow outgoing
    Allow outgoing traffic by default, unless another rule specifically restricts it.

    Similarly, incoming can be used to configure the default incoming policy.


    Block Incoming SSH

    SSH normally uses TCP port 22.
    sudo ufw deny 22/tcp

    Deny incoming TCP traffic on port 22.

    Remote Computer → TCP/22 → Linux Machine = Blocked


    View Firewall Rules
    sudo ufw status numbered

    Example:
    [1] 22/tcp    DENY IN    Anywhere

    This shows the rule number, port, action, and direction.


    Delete a Rule

    If the rule is number 2:
    sudo ufw delete 2

    UFW will ask for confirmation before removing it.

**Cybersecurity Relevance**

    Linux firewalls are important for controlling network access to servers and endpoints.

    For example, if a Linux server does not need SSH access from the Internet, blocking TCP/22 can reduce its attack surface.

Key Takeaways

    Netfilter = Linux kernel's underlying network filtering framework.
    iptables/nftables/firewalld/UFW = tools used to manage firewall behavior.
    UFW = simpler, beginner-friendly way to configure Linux firewall rules.
    22/tcp = SSH.
    allow = permit traffic.
    deny = block traffic.
    incoming = traffic coming into the machine.
    outgoing = traffic leaving the machine.