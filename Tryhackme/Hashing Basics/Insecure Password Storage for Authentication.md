**Hashing for Password Storage**
    - Hashing has many cybersecurity uses, but two important ones are:
        1. Password storage for authentication
        2. Data integrity

    - For normal authentication, websites doesn't need to know your actual password. It only verify that you know the correct password.
    - When you log in, your password is hashed and compared with the stored hash.

**Insecure Password Storage**
    - Incorrect storing of passwords can cause serious security problems if database is breached.
    - Common insecurity practices:
        1. Plaintext passwords - passwords are stored as exactly as entered
        2. Deprecated encryption - passwords are encrypted using outdated/weak encryption
        3. Insecure hashing - passwords are hashed using weak algorithms such as MD5 and SHA-1
    - Example:
        * **RockYou Breach**
            - RockYou stored user passwords in plaintext. When its database was breached, millions of actual passwords were exposed.
            - The leaked passwords became the famous rockyou.txt wordlist, containing over 14 million passwords.
            - Attackers can use password lists like this in brute-force and password-cracking attacks.

Cybersecurity take: 
    - For authentication, do not store passwords in plaintext.
    - Use a secured updated hashing algorithm combining with protection such as **salt**.
    - Even if attackers breached or steals a database, they will not be able to easily recover user's original passwords.