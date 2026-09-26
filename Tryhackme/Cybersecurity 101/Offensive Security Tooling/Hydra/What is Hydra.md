**What is Hydra?**

    Hydra is a brute force online password-cracking tool used to automate login attempts against authentication services.
    Instead of manually trying passwords one by one, Hydra can use a wordlist and test many passwords automatically.

    How it works:
    Username + Password Wordlist
            ↓
          Hydra
            ↓
     Login Service
            ↓
     Failed / Successful

**Services Hydra Supports**

    Hydra supports many authentication protocols and services, including:
    SSH
    FTP
    HTTP/HTTPS login forms
    SMB
    RDP
    Telnet
    SNMP
    MySQL / PostgreSQL
    LDAP
    VNC
    And many others

    The exact options and syntax depend on the protocol being tested.

**Why Wordlists Matter**

    Hydra commonly uses a password wordlist containing possible passwords
    A large wordlist can contain millions of commonly used or previously exposed passwords. eg. rockyou.txt
    Hydra checks these against the target's authentication system.

    Modern password security also relies on more than just password complexity:
     Long, unique passwords
     MFA
     Account lockout/rate limiting
     Removing default credentials
     Monitoring failed login attempts