**Burp Suite Community Key Features**

    Compared to the features of Professional edition, Burp Suite Community still provides important tools for web application security testing.

    1. Proxy - One of the main tools of Community.
        * Intercepts HTTP/HTTPS request and reponses
        * Allows requests/responses to be viewed and modified before reaching their destination.
        * eg. Intercept a login request and modify a parameter before forwarding it.

    2. Repeater - Repeater allows a captured request to be:
        * Capture → Modify → Resend → Modify → Resend
        * Useful for manually testing an endpoint and trying different payloads, such as SQL injection (SQLi).

    3. Intruder - Intruder automates sending many variations of requests.
        * Brute-force testing
        * Fuzzing
        * Testing many possible input values
        Community Edition has rate limitations, so it is more restricted than Professional.

    4. Decoder - Decoder converts data between different formats.
        * Can be used to decode captured data;
        * and Encode payloads before sending them.
        Examples include Base64, URL encoding, hexadecimal, etc.

    5. Comparer - compares two pieces of data
        It can compare:
            * Word level -> differences in text
            * Byte level -> differences at the raw data level
        Useful when analyzing two HTTP responses or other pieces of captured data.

    6. Sequencer - checks how random and unpredictable tokens are.
        For example:
            Session cookie: 8f72a91c...
        If session tokens are predictable, an attacker may potentially guess another user's token and hijack their session.

    7. Extensions & BApp Store - Burp can be extended with additional functionality.
        Burp Extender → loads extensions into Burp.
        BApp Store → marketplace for third-party Burp extensions.
        Extensions can add features that aren't included by default.
        Example:
        Logger++ → provides more advanced HTTP logging capabilities.

