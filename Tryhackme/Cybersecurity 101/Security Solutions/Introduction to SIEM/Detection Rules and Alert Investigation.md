**Behind Triggered Alerts**

    A SIEM detects threats using detection rules.

**Detection Rule**

    A detection rule is a logical condition that tells the SIEM: “If these conditions happen, generate an alert.”

    The SIEM continuously checks incoming logs against these rules.

    Examples:
    5 failed logins within 10 seconds → Alert: Multiple Failed Login Attempts
    Successful login after multiple failures → Alert: Successful Login After Multiple Attempts
    USB device connected → Alert if USB devices are restricted by company policy
    Outbound traffic > 25 MB → Alert for possible data exfiltration

    The exact thresholds depend on the organization's security policies and normal activity.

**How Detection Rules Work**

    Rules examine specific field-value pairs in normalized logs.

    Use Case 1: Event Log Cleared

        Attackers may clear Windows event logs to hide their activity.
        Windows generates Event ID 104 when event logs are cleared.

    Rule:
    Log Source = WinEventLog AND Event ID = 104

    → Alert: Event Log Cleared

    Why it matters:
    Clearing security logs can be a sign that an attacker is trying to remove evidence.


    Use Case 2: whoami Command Execution

        Attackers may run whoami after gaining access to determine which user/account they are currently using.
        Windows Event ID 4688 records process creation.

    Important fields:
    Log Source → Where the event came from
    Event ID = 4688 → Process creation
    NewProcessName → Name/path of the process being executed

    Rule:
    Log Source = WinEventLog
    AND Event ID = 4688
    AND NewProcessName contains "whoami"

    → Alert: WHOAMI Command Execution Detected

**Why Normalized Logs Matter**

    Detection rules depend on specific fields and values.

    For example:
    EventID = 4688
    NewProcessName = whoami.exe

    If logs from different sources use inconsistent field names/formats, detection rules become harder to create and maintain.
    Therefore: Parsing + normalization → consistent fields → more reliable detection rules

**Alert Investigation**

    When a detection rule triggers, the SOC analyst investigates the alert rather than immediately assuming it is an attack.

    Basic Investigation Flow
    1. Alert triggered
    ↓
    2. Examine related events/logs
    ↓
    3. Check which rule conditions were matched
    ↓
    4. Investigate the surrounding activity/context
    ↓
    5. Determine True Positive or False Positive

    False Positive
    The alert triggered, but the activity was legitimate.
    Example:
    An employee repeatedly fails a password because they forgot it.

    Action: The analyst may tune the detection rule to reduce unnecessary alerts.

    True Positive
    The alert represents genuine suspicious or malicious activity.

    Example:
    Multiple failed logins → successful login → unusual PowerShell execution → suspicious outbound connection.

    Action:
    Perform further investigation and incident response.

**Possible Actions:** 

    Depending on the investigation, the analyst may:

    Contact the asset/user owner to verify the activity.
    Investigate further if the activity is suspicious.
    Isolate the affected host to prevent further compromise.
    Block a malicious/suspicious IP address when appropriate.
    Escalate the incident to higher-level analysts or the incident response team.