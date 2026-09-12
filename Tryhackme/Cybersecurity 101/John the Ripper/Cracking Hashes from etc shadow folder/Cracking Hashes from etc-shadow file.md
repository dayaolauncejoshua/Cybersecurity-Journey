**Cracking Hashes from /etc/shadow**
    - On Linux, /etc/shadow is the place where it stores users' password hashes and password information such as password-change date, and expiration data. eg. **user:$6$...$hash...**
    - Only root or privileged user can read the /etc/shadow.

**Unshadowing**
    - John expects the Linux password information in a specific format. Therefore, when cracking /etc/shadow hashes, we combine it with /etc/passwd in order for John to understand the data. This is called **"unshadow"**
    - Basic syntax for unshadow:
        unshadow [path to passwd] [path to shadow]
        - Example:
            - **unshadow local_passwd local_shadow > unshadowed.txt**
            - This creates unshadowed.txt, which contains the combined information John can process.
    - You can use the entire files or just the relevant user entries. eg.:
        FILE 1 - local_passwd
            - Contains the /etc/passwd line for the root user: root:x:0:0::/root:/bin/bash
        FILE 2 - local_shadow
            - Contains the /etc/shadow line for the root user: root:$6$2nwjN454g.dv4HN/$m9Z/r2xVfweYVkrr.v5Ft8Ws3/YYksfNwq96UL1FX0OJjY1L6l.DS3KEVsZ9rOVLB/ldTeEL/OIhJZ4GMFMGA0:18576::::::

**Cracking with John**
    - After creating the combined file, give it to John:
        - **john --wordlist=/usr/share/wordlists/rockyou.txt unshadowed.txt**
    - If John needs the hash format specified:
        - **john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt**
        - sha512crypt is commonly identified by the $6$ prefix in /etc/shadow.

**Key take:**
    - /etc/shadow → contains Linux password hashes → unshadow combines it with
    - /etc/passwd → John uses the resulting file to attempt cracking.
    - /etc/shadow + /etc/passwd → unshadow → John → password