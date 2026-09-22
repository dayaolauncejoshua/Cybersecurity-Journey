**Burp Suite**

    Burp Suite is a Java-based framework used for web application penetration testing. 
    It is also commonly used when testing mobile applications and APIs.

**Main Purpose**

    Burp's core function is to act as a proxy between the browser and the web server.
    Browser 
     ↓ HTTP/HTTPS request 
    Burp Suite 
     ↓ 
    Web Server 
     ↓ HTTP/HTTPS response 
    Burp Suite 
     ↓ 
    Browser

    It sits in the middle, it means it can:
        * Capture HTTP/HTTPS traffic
        * View requests and responses
        * Modify requests before they reach the server
        * Modify responses before they reach the browser
        * Send requests to other Burp tools for further testing

**Example**

    A browser sends:
        POST /login HTTP/1.1
        username=admin&password=test

    Burp can intercept the request and allow the tester to examine or modify the data before forwarding it.

    For example:
        username=admin -> Burp Suite -> username=test

    This makes it possible to test how the web application handles different inputs and behaviors.

**Why It Matters in Cybersecurity**

    Burp is especially useful for manual web application security testing because it allows testers to see what is actually being sent between the client and server.

    This helps investigate areas such as:
      Authentication
      Session management
      Cookies
      User input
      Access control
      Injection vulnerabilities
      Application logic
      APIs

----------------------------------------

**Burp Suite Editions**

    Burp Suite has three main editions: Community, Professional, and Enterprise.

    1. Burp Suite Community Edition
        * Free for non-commercial use within legal/authorized boundaries.
        * This is the edition used for learning and labs.
        * Provides the core tools for manually inspecting and modifying web traffic.
        * Some advanced features are limited compared with Professional.

    2. Burp Suite Professional
        A licensed version with more advanced and unrestricted features, including:
            * Automated vulnerability scanner → automatically looks for web vulnerabilities.
            * Fuzzer/Brute-forcer → can test many inputs without the same rate limitations as Community.
            * Project saving & reports → save testing projects and generate reports.
            * API → integrate Burp with other tools.
            * More extensions → greater ability to extend Burp's functionality.
            * Burp Collaborator → helps detect certain vulnerabilities involving interactions between the target and an external server.
    
    3. Burp Suite Enterprise
        Enterprise is designed mainly for continuous automated scanning.
        Instead of a security tester manually using Burp from their computer:
            * Burp Enterprise → Server → Continuously scans web applications

        It can periodically scan applications for vulnerabilities, similar in concept to how Nessus continuously/automatically scans infrastructure.