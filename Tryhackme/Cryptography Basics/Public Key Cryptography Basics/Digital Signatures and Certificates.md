**Digital Signature**
    - is a cryptgraphic way to prove authenticity and integrity of a file or a document.
    - Authenticity - Who signed/created the file?
    - Integrity - The file has not been altered after it was signed.
    - It uses asymmetric cryptography:
        - Private key → Creates the digital signature
        - Public key → Verifies the signature
        - Only the owner should have the private key, so a valid signature provides evidence that the owner signed the data.
    - Digital signature = proves authenticity + protects integrity.

    Example:
        - The simplest form of digital signature is encrypting the document with your private key. If someone wants to verify this signature, they would decrypt it with your public key and check if the files match.

**Digital Signature vs. Electronic Signature**
    - An electronic signature can simply be an image of someone's handwritten signature pasted onto a document.
    - This does not prove integrity, because anyone could copy that image and paste it onto another document.
    - **Cryptographic Digital Signature**
        - A true digital signature uses cryptography, specifically a private key.
        Simplified process:

            Bob's document
                ↓
                Hash
                ↓
            Hash is signed using Bob's private key
                ↓
            Digital Signature

            Bob sends the original document + digital signature to Alice.

            Alice then:

            Uses Bob's public key to verify the signature.
            Calculates the hash of the document she received.
            Compares the two hashes.

            If they match:
            The document has not been changed.
            The signature was created using Bob's private key.

            If someone modifies the document:
            The hashes won't match → signature verification fails.

**Certificates**
    - A digital certificate helps your browser verify that a website is really the website it claims to be.
    - Example:
        - when you visit tryhackme.com using HTTPS, your browser needs to make sure it is communicating with the real TryHackMe server and not an attacker's server.
        - The website provides a TLS certificate containing information about its identity and public key.
Chain of Trust
    - Your browser doesn't simply trust every certificate. It uses a chain of trust:
        Website Certificate → Certificate Authority (CA) → Root CA → Browser/OS
    - Root CA 
        - is an organization that your operating system or browser already trusts. If the certificate can be traced back to a trusted Root CA, the browser can trust the website's certificate.
    - **TLS Certificates**
        - A website using HTTPS needs a TLS certificate. Certificates can be obtained from Certificate Authorities (CAs).

    - Certificate = proof of a website's identity.
    - HTTPS + TLS certificate + Certificate Authority → helps establish a secure and trusted connection.