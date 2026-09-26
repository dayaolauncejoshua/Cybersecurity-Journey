**Gobuster dns Mode**

    dns mode is used to discover subdomains of a target domain.

    Main domains supposed to have subdomains
        eg. example.com could have a subdomain of admin.example.com

    If the subdomain exists, Gobuster can identify it.

    Example Command

    gobuster dns -d example.thm -w /path/to/wordlist
    gobuster dns -d example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt

    This is important because the main domain or website and its subdomain smay have different applications, configurations, or security weakness.