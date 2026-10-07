**Why Are Logs Categorized?**

    A system can generate thousands or millions of log events. Looking through everything manually would be inefficient.
    Logs are therefore organized into different categories/types, based on the kind of information they contain.

    Example

    If investigating:
    “Who successfully logged into a Windows computer yesterday?”

    There is no need to examine every available log.

    The Security Logs are the most relevant because they contain authentication and other security-related events.

**Common Log Types**

    1. System Logs - Record activities related to the operating system

    Example:
    Computer started
    Computer shut down
    Driver loaded
    Hardware error occurred

    Useful for: OS troubleshooting and understanding system behavior.


    2. Security Logs - Record security-related activities.

    Example:
    Successful/failed login
    Account changes
    Authorization events
    Security policy changes

    Useful for: Detecting and investigating security incidents.

    For a SOC analyst, these are especially important when investigating account compromise or unauthorized access.


    3. Application Logs - Records events occurring inside an application.

    Example:
    User logged into a web application
    Application configuration changed
    Application update occurred
    Application generated an error

    Useful for: Investigating application problems and suspicious application activity.


    4. Audit Logs - Record important user and system activities, particularly actions that need to be tracked.

    Example:
        John accessed Customer_Database at 14:32

    Useful for:
    Security monitoring
    Investigations
    Compliance
    Tracking who performed an action


    5. Network Logs - Record network-related activity.

    Example:
    Incoming connection
    Outgoing connection
    Network session
    Firewall activity

    Useful for:
    Network troubleshooting
    Detecting suspicious connections
    Investigating attacks and data exfiltration


    6. Access Logs - Record when someone or something accesses a particular resource.

    Common examples:

    Web server access logs
    Database access logs
    Application access logs
    API access logs

    Example web server log:

        192.168.1.50 → GET /login → 200 OK

    This tells us that an IP address requested the /login resource and the server responded successfully.

**Log Analysis**

    Having logs is not enough. Security teams need to analyze them to find useful information.

    Log Analysis = Examining logs to extract useful information and identify suspicious or unusual activity.

    Analysts may look for:
    Unusual login times
    Multiple failed logins
    Suspicious IP addresses
    Unexpected network connections
    Unauthorized file access
    Malware activity
    Unusual user behavior
    Errors or system failures

    Example

    Suppose the logs show:
    09:01 - Failed login - admin
    09:02 - Failed login - admin
    09:03 - Failed login - admin
    09:04 - Failed login - admin
    09:05 - Successful login - admin
    09:06 - Large file download

    An analyst may recognize a possible sequence:
    Repeated failed logins → Successful login → Suspicious data access

    This could indicate a brute-force attack followed by account compromise.

**Manual vs Automated Log Analysis**

    Looking through logs with the naked eye becomes difficult when there are huge numbers of events.

    Organizations use both Manual Analysis and Automated Analysis


    MANUAL ANALYSIS - An analyst directly examines logs and searches for relevant events.

    Useful for:
    Small datasets
    Specific investigations
    Learning how logs work
    Detailed investigation of particular events


    AUTOMATED ANALYSIS:
    Tools automatically search, filter, correlate, and alert on suspicious events.

    Examples:
    SIEM
    EDR
    Log management platforms

    For example:
    500 failed logins from one IP → SIEM detects the pattern → generates an alert.
    
    The analyst then investigates the alert.

**Important SOC Mental Model**

    Log Source → Log Events → Analysis → Suspicious Activity → Alert/Investigation

    For example:
    Windows Security Log
    ↓
    Failed login events
    ↓
    Many failures from same IP
    ↓
    Possible brute-force attack
    ↓
    SOC investigates

**Important notes**

    Logs are categorized because different logs contain different types of information.

    Security Logs are particularly useful for authentication and security investigations.
    Network Logs help investigate network activity.

    Access Logs show access to resources such as websites and databases.

    Log Analysis means examining logs to find useful information or abnormal activity.
    
    Manual analysis works for smaller investigations, but large environments require automated tools such as SIEM.