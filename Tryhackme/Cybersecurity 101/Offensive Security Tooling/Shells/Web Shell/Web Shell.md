**Web Shell**

    A web shell is a script placed on a web server that allows commands to be executed through the web application.

    Unlike a normal reverse shell, the attacker doesn't necessarily need a direct network connection to a shell. Instead, HTTP requests are used to send commands to the web shell.

    Attacker
    │
    │ HTTP request
    ▼
    Web Server
    │
    ▼
    Web Shell
    │
    ▼
    Operating System
    │
    ▼
    Command executed

    Example: PHP Web Shell

    <?php
    if (isset($_GET['cmd'])) {
        system($_GET['cmd']);
    }
    ?>

    Basically means:
    If the HTTP request contains a cmd parameter, execute its value as an operating-system command.

    shell.php?cmd=whoami

    The result is then returned through the web response.

**How Does the Web Shell Get There?**

    An attacker first needs a way to place the malicious script on the web server.

    Possible causes include vulnerabilities such as:

    Unrestricted file upload → upload a malicious .php file
    File inclusion → cause attacker-controlled code/file to be loaded
    Command injection → execute commands through a vulnerable application
    Stolen/unauthorized access → directly place the file on the server

    Web vulnerability / unauthorized access
              ↓
       Web shell uploaded
              ↓
      Attacker sends HTTP request
              ↓
          Web shell
              ↓
       OS command executed
              ↓
         Result returned

**Why Web Shells Matter in Cybersecurity**

    Web shells are important in web application security and incident response because an attacker may hide a malicious script inside a legitimate web application's files.

**Key Takeaway**

    A web shell is a malicious script hosted on a web server that allows commands to be executed through HTTP requests.