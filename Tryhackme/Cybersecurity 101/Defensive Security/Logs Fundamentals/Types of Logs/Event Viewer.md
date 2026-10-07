**Windows Event Logs**

    Windows records many activities that happen on the operating system. These records are stored in different event logs, organized by category.

    The three major Windows logs are:

    Application Log - Records events related to applications.

    System Log - Records events related to the Windows operating system itself.

    Security Log - The Security log is especially important for cybersecurity.
    It records security-related activities such as:
    User authentication
    Successful/failed logins
    User account changes
    Security policy changes
    Other security events

**Event Viewer**

    Windows provides a built-in tool called Event Viewer.
    Event Viewer = Graphical interface for viewing, filtering, and searching Windows event logs.

    Instead of opening raw log files manually, an analyst can use Event Viewer to:
    View events
    Filter events
    Search for specific Event IDs
    Check timestamps
    Examine event details
    Investigate suspicious activity

    Event Viewer → Windows Logs → Security

**Windows Event IDs**

    Windows assigns an Event ID to different types of events. 

    Think of an Event ID as a number that identifies what happened.
    For example:
    Event ID 4624 = Successful login

    Instead of manually searching thousands of Security events, an analyst can filter for: 4624

    This makes investigation much faster.

**Important Event IDs**

    4624 - Successful login
    4625 - Failed login
    4634 - User logged off
    4720 - User account created
    4722 - User account enabled
    4724 - Attempt to reset an account's password
    4725 - User account disabled
    4726 - User account deleted

**Example Investigation**

    Suppose a SOC analyst suspects someone accessed a Windows computer using a stolen account.

    The analyst could search the Security log for:
    4624 → Successful logins

    Then examine details such as:
    Which account logged in?
    When did it happen?
    Where did the login originate?
    What type of login was used?
    Was the login normal for that user?

    The analyst could also check 4625 events to see whether there were many failed attempts before the successful login.

    For example:
    10:01 — 4625 — Failed login
    10:02 — 4625 — Failed login
    10:03 — 4625 — Failed login
    10:04 — 4624 — Successful login

    This pattern could indicate a brute-force/password-guessing attempt followed by a successful compromise.

    The Event ID alone does not prove an attack. The analyst needs to examine the event details and surrounding activity.

**Important note:**

    Windows Security logs are extremely valuable to SOC analysts, incident responders, and digital forensics investigators.

    They can help investigate:
    Account compromise
    Brute-force attacks
    Unauthorized logins
    Suspicious account creation
    Privilege/account changes
    Attacker activity on Windows systems

    Windows records activities as events. Event Viewer allows analysts to investigate those events, and Event IDs make it easier to identify specific activities. For security investigations, the Windows Security log is particularly important.