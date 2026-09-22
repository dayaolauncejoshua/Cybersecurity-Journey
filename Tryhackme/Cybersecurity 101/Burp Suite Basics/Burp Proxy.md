**Burp Proxy**

    is one of the most important tools in Burp Suite. It sits between the browser and the web server, allowing HTTP/HTTPS traffic to be captured, viewed, modified, and forwarded.

**Basic Flow**

    Browser → Burp Proxy → Web Server 
    Browser ← Burp Proxy ← Web Server

    🔹 Intercepting Requests
    When Intercept is ON, Burp pauses outgoing requests before they reach the server.    
    
    The request can then be:

     Forward → send it to the server
     Drop → discard it
     Edit → modify it before sending
     Send to another Burp tool → such as Repeater

     When Intercept is OFF, requests pass through normally.

        Important: Turning interception off does not stop Burp from recording traffic.
    
    🔹 Capture & HTTP History
    Burp records requests and responses passing through the Proxy.

    The HTTP history lets testers review previous traffic even after the request has already been sent.

    This is useful for finding:
     URLs and endpoints
     Parameters
     Cookies
     Authentication information
     Request/response behavior

    🔹 WebSocket History
     Burp can also capture and log WebSocket communication.

    This is useful for applications that require real-time communication, such as:
     Chat applications
     Live notifications
     Online games
     Real-time dashboards

     🔹 Proxy Settings
     The Proxy settings provide additional control over how Burp handles traffic.

     Response Interception
     By default, Burp mainly intercepts requests, not server responses.
     Rules can be configured to tell Burp when to intercept responses.
     For example, a rule could intercept responses from a specific URL so the response can be inspected or modified.

     Match and Replace
     Match and Replace uses regular expressions (regex) to automatically modify traffic.

     For example, Burp could automatically:

     User-Agent: Chrome → User-Agent: Test-Agent

     It can also modify things such as cookies, headers, or other request/response content.
     This is useful when the same modification needs to be applied repeatedly.