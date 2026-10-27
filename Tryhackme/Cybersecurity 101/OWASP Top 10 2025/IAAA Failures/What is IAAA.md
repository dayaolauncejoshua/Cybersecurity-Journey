# OWASP Top 10 (2025) - IAAA

    IAAA stands for Identity, Authentication, Authorisation, and Accountability. It describes four important stages for managing user access and tracking activity in an application.

### 1.Identity

    Identifies which user or service is requesting access.

    Example: You enter email address or username on a website

### 2.Authentication

    Verifies that the claimed identity is genuine.

    Example: You enter your password, use a one-time password (OTP), or authenticate with a passkey.

### 3.Authorisation

    Determines which resources and actions an authenticated identity is permitted to access.

    Example: A regular user can view their own orders but cannot access another customer's orders or the administrator dashboard.

### 4.Accountability

    Records and monitors actions so activity can be traced and investigated. 

    Example: Application logs record that a user logged in, changed an account setting, or attempted to access a restricted page.

### What Happens When IAAA Fails?

    Identity failure: The application incorrectly identifies or associates a request with an account.

    Authentication failure: An attacker gains access using stolen credentials or exploits weak login protections.

    Authorisation failure: A user accesses another user's data or performs an action beyond their permissions.

    Accountability failure: Important activity is not logged or monitored, making suspicious actions harder to investigate.

    These failures can result in account takeover, data exposure, privilege escalation, and difficulty investigating security incidents.

### Connection to OWASP Top 10 (2025)

#### IAAA helps explain three relevant OWASP categories:

    Broken Access Control: Failures in enforcing what users are allowed to do.
    Authentication Failures: Failures in verifying users' identities.
    Security Logging and Alerting Failures: Failures in recording and detecting important security events.


