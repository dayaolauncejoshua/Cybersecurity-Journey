**Web Application Components**

    A web application is divided into two parts:
        1. Frontend -> What users see and interacts with
        2. Backend -> What works behind it

    Frontend
        - Frontend is what the users see when they are interacting with a web application running on a web browser. It is the visible part of the web application.
        - It mainly uses HTML, CSS, and JavaScript.

            HTML: Defines the structure and content of a web page.
            CSS: Controls the appearance and layout. Design/Style
            Javascript: Adds logic and interactivity

    Backend
        - Backend is what users normally can't see but it is what makes the application functions.

        Database
            - a place where information are being stored and managed by the application
            - It can create, delete, modify data in the database
        Infrastructure
            - Infrastructure is the underlying technology that supports the application.
            - This includes:
                Web servers — Receive and respond to HTTP/HTTPS requests.
                Application servers — Run the application's backend logic.
                Storage — Stores files and other data.
                Networking devices — Connect the different components.
                Other software/services — Support the application.
    
    WAF — Web Application Firewall
        - A WAF is an optional security component placed in front of a web application.
        - It analyzes incoming web requests and blocks malicious or suspicious requests before they reach the web server
        - eg. Internet -> WAF -> Web server -> Application -> Database
        - This helps prevents web attacks such as SQL Injection and some forms of malicious input
