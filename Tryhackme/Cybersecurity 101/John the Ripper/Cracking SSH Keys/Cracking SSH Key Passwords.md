**John — Cracking SSH Private Key Passwords**
    - SSH can use key-based authentication instead of a normal login password.
    - The private key is commonly stored as: id_rsa
    - The important distinction is that the private key itself can be protected with a passphrase.
        - SSH private key (id_rsa) -> protected by passphrase
    - If you have the private key but don't know its passphrase, John can be used to attempt to recover the passphrase.

1. **Convert the SSH Key**
    - John cannot directly crack the id_rsa file, so we use ssh2john to convert it into a format John understands.
    - Syntax: ssh2john [id_rsa file] > [output file]
    - Example: /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
    - On some systems: python3 /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
    - The process: id_rsa -> ssh2john -> id_rsa_hash.txt
2. **Crack the Passphrase**
    - Feed the generated file into John:
    - john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt
    - John tries passwords from the wordlist until it finds the correct private-key passphrase.

**Cybersecurity Key Takeaway**
ZIP → zip2john → John 
RAR → rar2john → John 
SSH key → ssh2john → John 
Linux → unshadow → John
    - The conversion tool prepares the authentication/password data, while John performs the cracking.