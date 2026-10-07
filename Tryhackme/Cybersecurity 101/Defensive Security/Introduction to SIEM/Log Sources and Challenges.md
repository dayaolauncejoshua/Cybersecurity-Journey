**Log Sources and Challenges**

**1.Log Sources**

    A log source is a device or system that generates logs.

    Two main categories:

    Host-Centric Log Sources - Logs about activity inside a device/host.
    
    Examples:
    Windows/Linux systems
    Servers
    Workstations

    Events include:
    User accessing a file
    Login/authentication attempt
    Process execution
    Registry changes
    PowerShell execution

    It is like what's happening on a computer.


    Network-Centric Log Sources - Logs about network communication between systems or with the Internet.

    Examples:
    Firewalls
    IDS/IPS
    Routers

    Events include:
    SSH connections
    FTP file access
    Web traffic
    VPN connections
    Network file sharing

    It is like what's happening between computers/networks.

**2.Why Logs Alone Are Difficult**

    A network can have many log sources, each generating huge amounts of logs.

    2.1. Numerous Log Sources 

        A company may have: 100 computers + servers + firewalls + routers + applications
        Each can generate hundreds or thousands of events.
        Manually checking every device is extremely inefficient.

    
    2.2. No Centralization

        Logs normally remain on the device that generated them.
        An analyst might need to connect to:
        Windows machines
        Linux servers
        Network devices
        Firewalls

        This wastes time during an incident.
        SIEM solves this by bringing logs into one central location.

    
    2.3 Limited Context 

        One log by itself may look completely normal.
        Example: User accessed confidential.docx
        That isn't necessarily suspicious.

        But correlate it with: Compromised PC → attacker moves laterally → user account accessed → confidential file accessed
        Now the activity becomes much more suspicious.

        Correlation gives context

    
    2.4. Limited Analysis

        Humans cannot realistically examine every log generated every second. Important events can easily be missed.

        SIEM helps by automatically:
        Filtering
        Searching
        Correlating
        Detecting patterns
        Generating alerts

    
    2.5. Different Log Formats

        Different devices produce logs in different formats.
        
        For example:

        Windows:
        Windows Event IDs

        Web server:
        Apache access logs

        Firewall:
        Firewall-specific format

        Analyzing all these formats manually is difficult.

        SIEM normalizes/structures the data so information from different sources can be analyzed together.


**Important / Key**

    Without SIEM, Analysts check everything separately. 
    Windows → Logs 
    Linux → Logs 
    Firewall → Logs 
    Router → Logs 
    Web Server → Logs

    With SIEM, It centralize and correlates these logs, set alerts, and be investigated by analysts/SOC. 