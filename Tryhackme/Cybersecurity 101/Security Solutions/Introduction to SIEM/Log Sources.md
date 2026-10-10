**Log Sources**

**Windows Machine**

    Windows records many activities as events.
    Each event is assigned an Event ID, which helps analysts identify what happened. eg. 4624 → Successful login, 4625 → Failed login, 4720 → User account created

    Event Viewer
    Event Viewer is the built-in Windows tool used to view and investigate these events. 

**Linux Logs**

    Linux records events, errors, warnings, authentication activity, and system activity in log files. These logs can be forwarded/ingested into a SIEM for centralized and continuous security monitoring.

    Common Linux Log Locations
    /var/log/httpd - HTTP request, response, and error logs
    /var/log/cron - Cron job events and scheduled-task activity
    /var/log/auth.log - Authentication-related logs, commonly Debian/Ubuntu
    /var/log/secure - Authentication/security logs, commonly RHEL/CentOS
    /var/log/kern - Kernel-related events

**Web Server**

    It is important to monitor all requests/responses coming in and out of the web server for any potential web attack attempt. In Linux, common locations to write all apache-related logs are /var/log/apache or /var/log/httpd.

    Example:
    192.168.21.200 - - [21/March/2022:10:17:10 -0300] "GET /cgi-bin/try/ HTTP/1.0" 200 3395 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36"
    127.0.0.1 - - [21/March/2022:10:22:04 -0300] "GET / HTTP/1.0" 200 2216 "-" "curl/7.68.0"

**Log Ingestion**

    Log ingestion is the process of collecting and sending logs from different systems into a SIEM for centralized monitoring and analysis.

    Common Log Ingestion Methods

    1. Agent / Forwarder

    A lightweight program is installed on an endpoint/server.
    It collects important logs and sends them to the SIEM.
    Example: Splunk Forwarder sends Windows/Linux logs to Splunk.

    Flow: Endpoint → Agent/Forwarder → SIEM

    
    2. Syslog

    Syslog is a common protocol for sending log messages from devices and systems to a centralized server.
    Common sources: Linux servers, firewalls, routers, web servers, etc.
    Useful for real-time log collection.

    Flow: Device/Server → Syslog → SIEM


    3. Manual Upload

    Existing/offline log files can be manually uploaded into a SIEM.
    Useful when investigating previously collected logs or historical data.
    The SIEM processes/normalizes the data so it can be analyzed.

    Example: A security team receives a log file from a compromised server and uploads it to the SIEM for investigation.

    
    4. Port Forwarding

    The SIEM is configured to listen on a specific network port.
    Endpoints send their logs to that IP address and port.

    Flow: Endpoint → Network → SIEM listening on port

**Real-World Analogy**

    Think of the SIEM as a security control center:
        Agent/Forwarder = employee delivering reports
        Syslog = standardized communication channel
        Manual Upload = bringing an old report to the control center
        Port Forwarding = sending reports to a specific mailbox/door

**Cybersecurity Relevance**

    Log ingestion is important because a SIEM cannot analyze logs it does not receive. Proper ingestion gives SOC analysts centralized visibility across endpoints, servers, network devices, and applications.

    Log Sources → Ingestion Method → SIEM → Normalize/Parse → Analyze/Correlate → Alert