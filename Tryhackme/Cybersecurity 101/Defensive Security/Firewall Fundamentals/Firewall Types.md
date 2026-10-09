**Firewall Types**

    Firewalls can operate at different OSI layers, depending on what they inspect and how they make filtering decisions.

**1.Stateless Firewall**

    OSI: Layer 3 (Network) + Layer 4 (Transport)

    A stateless firewall checks each packet independently against predefined rules. 
    It does not remember previous connections.

    Example:
    Rule: Block traffic from 10.0.0.5

    If a packet from 10.0.0.5 arrives → blocked.

    The next packet from the same source is treated as a new packet and checked again. The firewall does not remember what happened before.

    
    ADVANTAGES:
    Simple
    Fast
    Efficient for high-volume traffic


    LIMITATION:
    Cannot make decisions based on the history/state of a connection.

**2.Stateful Firewall**

    OSI: Layer 3 + Layer 4

    A stateful firewall remembers active connections using a state table.
    Instead of looking at every packet independently, it can determine whether a packet belongs to an existing legitimate connection.

    Example:

    A user starts an HTTPS connection: PC → Firewall → Web Server

    The firewall records this connection in its state table.
    When subsequent packets belonging to that connection arrive, the firewall knows they are part of an established connection and can allow them according to the connection state.


    ADVANTAGES:
    Tracks connections
    More intelligent than stateless filtering
    Can apply rules based on connection state
    Better security for many network environments


**3.Proxy Firewall**

    OSI: Layer 7 (Application)

    A proxy firewall acts as an intermediary between the internal network and the Internet.

    Instead of the client communicating directly with the destination:

    it becomes: Client → Proxy Firewall → Internet

    The proxy can inspect application-level content and apply content-based rules.

    Example:

    An organization can configure the proxy to: Block access to malicious or restricted websites.

    The proxy can inspect the web request and decide whether to allow or deny it.

    It can also hide internal IP addresses because external systems see the proxy's IP address rather than the client's internal address.


    CAPABILITIES:
    Content filtering
    Application-level control
    Inspect application traffic
    Can inspect decrypted SSL/TLS traffic when configured for it

**4.Next-Generation Firewall (NGFW)**

    OSI: Layer 3 → Layer 7

    An NGFW combines traditional firewall capabilities with more advanced security features.

    It can perform deep packet inspection and use additional security technologies such as:

    IPS (Intrusion Prevention System) — detects and blocks malicious activity
    Threat intelligence — compares activity against known threat information
    Heuristic/behavior analysis — identifies suspicious patterns
    SSL/TLS inspection — decrypts traffic for inspection when configured

    Example:
    An attacker sends malicious traffic toward a company server.

    The NGFW can: Receive traffic → Inspect → Detect malicious pattern → Block
    rather than simply checking the source IP and port.

**Quick Comparison**

    Stateless (L3–L4) - Checks each packet independently
    Stateful (L3–L4) - Tracks connection state
    Proxy (L7) - Acts as intermediary and inspects application traffic
    NGFW (L3–L7) - Advanced inspection + threat prevention