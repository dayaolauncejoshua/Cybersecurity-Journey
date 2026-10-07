**Web Server Access Logs**

    Whenever someone interacts with a website, the web server receives HTTP requests.

    Examples:
    Viewing a page
    Logging in
    Uploading a file
    Requesting an image
    Accessing an API

    The web server records these requests in an access log.
    Example location — Apache
    /var/log/apache2/access.log

    An access log can help investigators understand who accessed the website, when, what they requested, and how the server responded.

**Important Access Log Fields**

    Example:
    172.16.0.1 - - [06/Jun/2024:13:58:44] "GET /products HTTP/1.1" 404 "-" "Mozilla/5.0 ..."

    IP ADDRESS
    172.16.0.1
    The IP address associated with the client making the request.

    Example:
    An analyst notices hundreds of requests coming from the same IP. This could be suspicious and may indicate scanning or automated attacks.


    TIMESTAMP
    [06/Jun/2024:13:58:44]
    Shows when the request occurred.

    This is important for building a timeline during an investigation.


    HTTP METHOD
    GET
    Describes the type of HTTP request.

    Common methods include:
    GET → retrieve a resource
    POST → send data to the server
    PUT → update a resource
    DELETE → delete a resource


    URL / RESOURCE
    /products

    Shows the resource that was requested.
    An analyst can use this to determine what part of the website was accessed.


    STATUS CODE
    404 - Resource not found
    Shows how the server responded to the request.

    Important: A 404 or 500 is not automatically an attack. Context is needed.


    USER-AGENT
    Example:
    Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...
    Provides information about the client software, commonly including the browser and operating system.
    It can help analysts identify what type of client made the request.

    Important: User-Agent information can be spoofed, so it should not be treated as definitive proof of the user's actual device.

**Why These Fields Matter in Security**

    An access log gives investigators several useful pieces of information:

        Who → When → What → How the server responded

    For example:
    192.168.1.50
    10:15
    POST /login
    401

    This could mean:

        IP 192.168.1.50 attempted to access /login, but authentication failed.

    If the same IP generates hundreds of failed login requests, it could indicate credential guessing or brute-force activity.


**cat — Display a Log**

    cat displays the contents of a text file.
    cat access.log

    Useful when the log is small enough to read directly.

    Example
    cat access.log
    Output:
    172.16.0.1 ... "GET /products HTTP/1.1" 404 ...
    10.0.0.1 ... "GET / HTTP/1.1" 404 ...
    192.168.1.1 ... "GET /about HTTP/1.1" 500 ...

**Combining Log Files with cat**

    Logs are commonly rotated, meaning older logs are moved into separate files based on time.
    For example:
    access.log
    access1.log
    access2.log

    Sometimes an investigation requires multiple files.

    They can be combined:
    cat access1.log access2.log > combined_access.log

    Meaning
    access1.log + access2.log 
        ↓ 
    combined_access.log

    > sends the output into the specified file.

**grep — Search Logs**

    grep is extremely useful during log analysis. It searches a file for a specific string or pattern.

    Example
    grep "192.168.1.1" access.log

    This displays every line containing:
    192.168.1.1
    Instead of reading the entire log, the analyst immediately sees all activity associated with that IP.

    Security example
    grep "192.168.1.1" access.log

    Could reveal:
    192.168.1.1 ... GET /login ... 401
    192.168.1.1 ... GET /admin ... 403
    192.168.1.1 ... GET /products ... 200

    This gives the analyst a quick view of that IP's activity.

**less — Read Large Logs Page by Page**

    Large log files can contain thousands or millions of lines.

    Using:
    cat access.log
    may produce too much output.

    Instead:
    less access.log
    less allows the log to be viewed one page at a time.

    Useful controls
    
    Space - Next page
    b - Previous page
    /pattern - Search for a pattern
    n - Next search result
    N - Previous search result
    q - Quit

    Example
    less access.log
    Then search for:
    /192.168.1.1
    Press Enter, and less jumps to matching entries.
    Press:
    n
    to find the next occurrence.
    
**Practical SOC Investigation Example**

    Imagine a web server was attacked.

    An analyst suspects:
        10.0.0.50

    The analyst could start with:
        grep "10.0.0.50" access.log

    Then examine the requests:
        10.0.0.50 ... GET /admin ... 403
        10.0.0.50 ... GET /backup ... 404
        10.0.0.50 ... GET /login ... 200
        10.0.0.50 ... POST /login ... 401
        10.0.0.50 ... POST /login ... 401

    This provides clues about what the IP was attempting to access.

    The analyst can then investigate further by looking at:
    Time of requests
    Requested URLs
    HTTP methods
    Status codes
    Number of requests
    User-Agent
    Other related IP addresses/events

    This is how raw logs become evidence for an investigation.

**Easy Mental Model**

    Reading logs

    cat → Show everything

    grep → Find what I want

    less → Browse large logs

    cat file1 file2 > combined → Combine logs

    Investigation flow
    Web activity
        ↓
    HTTP request
        ↓
    Access log
        ↓
    Search/filter with grep or less
        ↓
    Find suspicious patterns
        ↓
    Investigate further

**Cybersecurity Relevance**

    Web access logs are valuable during investigations involving:
    Brute-force attacks
    Web scanning
    Unauthorized access
    Exploitation attempts
    Suspicious file access
    Web application attacks
    Data access/exfiltration