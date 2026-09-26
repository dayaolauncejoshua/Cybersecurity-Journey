**Hydra Commands**

    Hydra's command syntax depends on the service being tested. The basic idea is:
    Hydra → Username + Password List → Authentication Service

    1. FTP

    Example:
     hydra -l user -P passlist.txt ftp://MACHINE_IP

    -l user → username to test
    -P passlist.txt → password wordlist
    ftp://MACHINE_IP → target FTP service

    2. SSH

    hydra -l root -P passwords.txt MACHINE_IP -t 4 ssh

    -l - specifies a single username
    -P - specifies a password list
    -t - 4 Use 4 parallel threads
    ssh - Service being tested

    The command means: 
    Try the passwords in passwords.txt against the SSH service using the root username, with 4 parallel attempts.

    Threads
    -t controls how many attempts Hydra processes in parallel.

    -t 1 → 1 thread
    -t 4 → 4 threads
    -t 8 → 8 threads
    More threads can make testing faster, but aggressive attempts may trigger rate limiting, account lockouts, or detection.

    3. Web Forms - POST

    Hydra can also test web login forms.
    First, determine whether the form uses GET or POST. Browser Developer Tools → Network can help identify this.
    A POST form command looks like:

    hydra -l username -P wordlist MACHINE_IP \ http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V

    Important parts
    -l = Username
    -P = Password wordlist
    http-post-form = The web form uses HTTP POST
    / = login page path
    username=^USER^ = Hydra inserts the username here
    password=^PASS^ = Hydra inserts each password here
    F=incorrect = Text indicating a failed login
    -V = Show each attempt 

**Understanding ^USER^ and ^PASS^**

    These are placeholders Hydra replaces automatically.
    For example:

    username=^USER^
    password=^PASS^

    could become:

    username=admin
    password=password123

    Then Hydra tries the next password from the wordlist.

**Understanding F=incorrect**

    Hydra needs a way to recognize a failed login.
    If the server responds with:

    Login failed: incorrect password

    Hydra can use:

    F=incorrect

    The F= tells Hydra:
     If this text appears in the response, consider the login attempt a failure.

    
    4. Non-Default Port

    If the service isn't using its standard port, use:
    -s <port>

    Example:
    hydra -l username -P wordlist MACHINE_IP \ http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" \ -s 8080 -V

    Here:   
    -s 8080
    means the web service is listening on port 8080.

**Key Takeaway**

    The most important Hydra options to remember:

    -l       → username
    -P       → password wordlist
    -t       → number of threads
    -V       → verbose output
    -s       → specify port
    ^USER^   → username placeholder
    ^PASS^   → password placeholder
    F=       → identify failed login

    The service module at the end tells Hydra what kind of authentication it is testing:

    ssh
    ftp://
    http-post-form

    Choose the service → provide username(s) → provide password wordlist → tell Hydra how to recognize success/failure → run the authorized test.