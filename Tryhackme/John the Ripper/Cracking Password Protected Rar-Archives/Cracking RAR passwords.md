**John — Cracking RAR Passwords**
    - A RAR archive is a compressed container, similar to a ZIP file. It can contain multiple files/folders and can be protected with a password.

1. **Convert the RAR File**
    - John cannot directly use the .rar file, so we first use rar2john to extract the password-related information into a format John understands.
    - Syntax: rar2john [rar file] > [output file]
    - Example: /opt/john/rar2john rarfile.rar > rar_hash.txt
    - The process is: rarfile.rar -> rar2john -> rar_hash.txt
2. **Crack with John**
    - Now give the generated file to John:
        john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt

**Key Take:**
    The process is almost identical with Cracking Zip files
    rar2john prepares a password-protected RAR archive for John to crack.