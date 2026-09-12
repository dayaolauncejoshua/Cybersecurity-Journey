**Identifying and Cracking Password Hashes**
    - From an offensive security perspective, if you obtain a password hash, the first step is to figure out what type of hash it is. Once you identify it, you can try to crack it and recover the original password.

**Linux Password Hashes**
    - On Linux, password hashes are normally stored in: /etc/shadow
    - This file is normally readable only by root, making it more secure than the old method of storing password information in /etc/passwd.
    - A /etc/shadow entry contains several fields separated by :. The password field contains information such as:
        - $prefix$options$salt$hash
        - This shows:
            ~ Prefix → identifies the hashing algorithm
            ~ Options → parameters used by the algorithm
            ~ Salt → random value added to the password
            ~ Hash → resulting password hash
        - the prefix is especially useful for identifying which hashing algorithm was used.

**Offensive process:** 
    - Identify the hash → determine the algorithm → attempt to crack it → recover the password.

**Hash Formats in Linux and Windows**

1. Modern Linux
    - Linux stores password hashes in /etc/shadow.
    - Example:
        - user1:$y$j9T$76UzfgEM5PnymhQ7TlJey1$/OOSg64dhfF.TigVPdzqiFang6uZA4QA1pzzegKdVm4
        - The important part is the password field: $prefix$options$salt$hash
            $y$j9T$76UzfgEM5PnymhQ7TlJey1$/OOSg64dhfF.TigVPdzqiFang6uZA4QA1pzzegKdVm4
                * y → yescrypt, the hashing algorithm
                * j9T → algorithm parameters
                * 76Uz... → salt
                * /OOS... → hash

2. Windows Passwords
    - Windows uses NTLM to hash passwords.
    - Windows password hashes are stored in the SAM (Security Accounts Manager) database.
    - NTLM hashes can look similar to MD4 or MD5 hashes, so you cannot always identify the algorithm just by looking at the hash.

Linux /etc/shadow → likely Linux password-hashing format
Windows SAM → likely NTLM

Tools such as Hashcat can help identify and crack different hash types.