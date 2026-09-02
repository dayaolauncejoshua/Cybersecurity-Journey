**What is Cryptography?**
    - Is the study or practice of protecting information from adversaries/third parties by transforming it so that only authorized people can access and use it. 
    - It is used to protect confidentiality, integrity, and authenticity.

**Common Examples**
    - Logging in to social media account - Credentials are encrypted while being sent to the server
    - Using SSH - SSH client and the server creates a secure/encrypted connection.
    - Online banking - Checks bank's digital certificate to make sure you are communicating with the legitimate bank server and not an attacker's
    - Downloading files - Cryptographic hash functions verify that the downloaded file are original and not modified.

**Cryptography and Security Standards**
    - It is also required by many security laws and standards.

    1. PCI DSS (Payment Card Industry Data Security Standard) - requires organizations to protect payment-card data including:
            * Data at rest - stored on computers, servers, or databases
            * Data in transit - data being sent on network
    2. Medical Data - protects medical records. Specific requirements depends on the country
        - HIPAA (Health Insurance Portability and Accountability Act) in the USA - Primary law that governs the privacy of healthcare information
        - HITECH (Health Information Technology for Economic and Clinical Health) in the USA 
        - GDPR (General Data Protection Regulation) in the EU - Regulation on information privacy in the Europenian Union
        - DPA (Data Protection Act) in the UK

**Confidentiality** - prevents unauthorized access to data
**Integrity** - helps detects whether data has been changed
**Authenticity** - helps verify who you are communicating with
**Data Verification** - hashes can confirm that files are not altered