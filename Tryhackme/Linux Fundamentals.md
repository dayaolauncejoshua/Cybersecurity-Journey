What is Linux?
    - Linux is an open-source kernel that manages the core resources of a computer and serves as the foundation for many Linux-based operating systems.

Examples:
    Ubuntu - General-purpose Linux distribution
    Debian - Stable/general-purpose distribution
    Kali Linux - Security and penetration-testing distribution

Cybersecurity importance:
    - Linux is widely used in servers, cloud infrastructure, cybersecurity tools, and security appliances, so understanding Linux is essential for cybersecurity professionals.

What is SSH? 
    - Secure Shell or SSH simply is a protocol between devices in an encrypted form. Using cryptography, any input we send in a human-readable format is encrypted for travelling over a network where it is then unencrypted once it reaches the remote machine. eg. ssh username@IP

Linux Common directories:
    1. /etc - contains system and application configuration files.
    2. /tmp - used for temporary files created by applications and users.
    3. /var - stores data that changes frequently while the system is running.
    4. /root - is the home directory of the root (administrator) account.

Nano - Linux Terminal Text Editor:
    - is a simple text editor that runs directly inside the Linux terminal. It allows you to create and edit text files without using a graphical interface.

Why is Nano useful?
    - In Linux, especially on servers, you often don't have a graphical desktop. You work entirely through the terminal.
Nano lets you edit things such as:
    - Configuration files
    - Scripts
    - Text files
    - Web server configurations
    - System settings

Transferring Files From Your Host - SCP (SSH)
    - Secure copy or SCP is a means of securely copying or transferring files between two computers using SSH.
Working on a model of SOURCE and DESTINATION, SCP allows you to:
    - Copy files & directories from your current system to a remote system
    - Copy files & directories from a remote system to your current system
Command:
    - scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
    - "important.txt" is the file we transferred
    - "ubuntu@192.168.1.30" is the remote system 
    - "/home/ubuntu/transferred.txt" is the directory where we want to transfer the file