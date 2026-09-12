**John the Ripper — Basic Syntax**
    - **john [options] [file]**
        - john → starts John the Ripper
        - [options] → tells John how to perform the attack
        - [file] → file containing the hash(es) you want to crack
    - Wordlist Attack
        - The most common approach is using a wordlist:
        - john **--wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt**
            - This means use rockyou.txt to try password guesses against the hashes in hash_to_crack.txt.

**Automatic Hash Detection**
    - John can sometimes automatically identify the hash type and choose an appropriate format.
    - It is convenient when you dont know what type of hash you have, however automatic detection isn't always reliable.
**Identifying Hashes Manually**
    - use a tool like hash-identifier or online tool https://hashes.com/en/tools/hash_identifier. It will suggest possible hash types

**Format-Specific Cracking**
    - If you know the hash type, you can tell John exactly which format to use:
        - **john --format=[format] --wordlist=[wordlist] [hashfile]**
        - eg. john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt   
**How to find the format**
    - List all formats John supports:
        - **john --list=formats** or **john --list=formats | grep -iF "md5"** for specific types