**John — Cracking ZIP Passwords**
    - John can crack the password of a password-protected ZIP file.
    - However, It cannot directly use the ZIP file. We first use **zip2john** to extract the password-related information and convert it into a hash format that John can process.

1. **Convert the ZIP file**
    - Syntax: zip2john [zip file] > [output file]
    - Example: zip2john zipfile.zip > zip_hash.txt
        - It will convert the zip into a hash format.
2. **Crack with John**
    - Once the hash file is created, give it to John just like other hashes:
    - john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt

**Cybersecurity Key Takeaway**
    - zip2john converts a password-protected ZIP into a format that John can crack.
    - It is similar to unshadow:
        - unshadow → prepares Linux password hashes for John
        - zip2john → prepares ZIP password data for John
        - john → attempts to crack the resulting data