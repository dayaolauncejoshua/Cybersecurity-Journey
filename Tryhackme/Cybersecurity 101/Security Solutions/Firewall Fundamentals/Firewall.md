**Firewall Fundamentals**

    A firewall is a security device or software that controls network traffic based on predefined rules.

    A security tool, hardware or software that is used to filter network traffic by stopping unauthorized incoming and outgoing traffic.

**What does it check?**

    Depending on the firewall, rules can examine things like:

    Source IP — where traffic comes from
    Destination IP — where traffic is going
    Port — e.g., 22 SSH, 80 HTTP, 443 HTTPS
    Protocol — TCP, UDP, ICMP
    Direction — inbound or outbound traffic
    Sometimes application/user information

    Example:

    A company might create a rule that allows employees to access the web using HTTPS (TCP/443)

    But:
    Block inbound SSH (TCP/22) from the public Internet

    The firewall checks the traffic against its rules before allowing or blocking it.

**Why it matters in cybersecurity:**

    Firewalls help:
    Prevent unauthorized network access
    Restrict unnecessary services/ports
    Control inbound and outbound traffic
    Reduce attack surface
    Detect and log suspicious connections
