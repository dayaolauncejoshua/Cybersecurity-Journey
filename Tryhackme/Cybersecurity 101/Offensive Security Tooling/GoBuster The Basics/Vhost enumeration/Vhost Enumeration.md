**Gobuster vhost Mode**

    vhost mode is used to discover virtual hosts — different websites hosted on the same server/IP address.

    They can look similar to subdomains, but the way they are discovered is different.

    Sample command
    gobuster vhost -u http://10.10.10.25 -w /usr/share/wordlists/dirb/common.txt --append-domain -t 50
    gobuster vhost -u http://app.example.thm -w /usr/share/wordlists/dirb/common.txt --append-domain -t 30
    gobuster vhost -u "http://10.49.144.34" --domain example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain --exclude-length 250-320

**Virtual Host vs Subdomain** 

    Imagine one server, IP: 10.10.10.5
    It might host:
     example.com    
     admin.example.com
     dev.example.com
    
    These names could represent different websites/applications on the same server.

    The important distinction is:

    Subdomain → discovered through DNS
    Virtual host → discovered by sending requests to the server with different Host headers/names

    Simple Analogy

    Think of the server as an apartment building:

    DNS mode: Ask the directory, “Does admin.example.com have an address?”
    VHost mode: Go to the building and say, “I'm requesting the website for admin.example.com.”

    The server may respond with a different website depending on the requested hostname.