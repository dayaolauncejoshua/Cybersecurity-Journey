**SIEM (Security Information and Event Management)**

    SIEM is the core security solution that a SOC analyst uses in the security operations center. 
    It is a security platform that collects, centralize, and analyze logs/events from many systems to help detect and investigate threats.


    Simple flow
    Devices/Servers/Firewalls/Applications
    ↓
    Logs
    ↓
    SIEM
    ↓
    Correlation & Detection Rules
    ↓
    Alert
    ↓
    SOC Analyst investigates


    Example
    A company has:

    Windows login logs
    Firewall logs
    Web server logs
    EDR logs

    Instead of checking each system separately, the SIEM brings the logs together.

    It might detect:
    20 failed logins → successful login → unusual IP → sensitive file access

    The SIEM can generate an alert, and the SOC analyst investigates it.

**Why SIEM matters**

    For a SOC, SIEM is essentially a central place to monitor and investigate security activity.
    SIEM = Collect logs → Correlate/analyze → Detect suspicious activity → Alert SOC