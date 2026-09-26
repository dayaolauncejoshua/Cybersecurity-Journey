**Gobuster**

    Gobuster is an open-source offensive security tool written in Go (Golang). It is mainly used for enumeration during penetration testing and security assessments.

    It can discover:

    Web directories and files
    DNS subdomains
    Virtual hosts (vhosts)
    Amazon S3 buckets
    Google Cloud Storage

    Gobuster commonly uses wordlists to automate the discovery process.

**Enumeration**

    Enumeration means systematically identifying available resources on a target.

    For example, a website may have:
    example.com/
    example.com/admin/
    example.com/backup/
    example.com/uploads/

    Gobuster can help discover these locations even if they aren't linked from the main page.

**Brute Force**

    Brute force means trying many possible values until a match is found.

    Simple analogy:
    There are 10 keys → try each key until one opens the lock.

    Gobuster applies this idea using a wordlist:

    admin
    login
    backup
    uploads
    dashboard

    It tests each word against the target and analyzes the responses.

**Where Gobuster Fits**

    In a typical ethical hacking process:

    Reconnaissance → Enumeration/Scanning → Exploitation 
                         ↑ Gobuster

    Gobuster is commonly used during the reconnaissance and enumeration/scanning stages to discover additional attack surface.

**Example**

    gobuster dir -u http://TARGET -w wordlist.txt

    This tells Gobuster to use a wordlist to look for directories on the target web server.

**Key Take**

    Gobster doesn't primarily exploit vulnerabilities. Its main purpose is to discover what exists on a target so that further security testing can be performed.