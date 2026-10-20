# Trust but Verify and Zero Trust

    Trust is necessary in business and technology, but trusting users or systems without checking their behavior can create security risks.

### Trust but Verify

    Even when we trust a user or system, we should verify that its behavior is legitimate and normal. 

    Verification may involve reviewing logs, monitoring activity, and using automated security tools.

    Example: An employee is authorized to access company files. The security team still monitors their activity to detect unusual downloads or suspicious access.

    Common security tools:

    1. Logs: Record system and user activities
    2. IDS/IPS: Detect or block suspicious network activity.
    3. Proxy: Can monitor and filter web traffic according to security policies.

### Zero Trust

    Never automatically trust a user, device, or simply because it is inside the company network or belongs to the organization. Verify access requests before granting access.

    Zero Trust follows the principle "Never trust always verify."

    Access decisions consider factors such as identity, permissions, device security, and the resource being requested.

    Example: An employee using a company laptop must still authenticate and be authorized before accessing a sensitive database, even when connected to the office network.

    
    Main Principles of Zero Trust

    1. Verify explicitly: Authenticate users and evaluate relevant security conditions before granting access.
    2. Least privilege: Grant only the permissions required for the task.
    3. Assume breach: Design security controls with the expectation that an attacker may already have gained access somewhere.

### Microsegmentation

    Divides a network into small, isolated security segments. In some designs, a segment can contain just one host.

    Communication between segments is restricted according to security policies

    Example: If an attacker compromises an employee's computer, network controls may prevent that computer from directly accessing the finance server.

    This helps limit an attacker's ability to move laterally across the network.

### Key Takeaways

    Trust but Verify: Don't rely on trust alone; check activity for signs of problems.

    Zero Trust: Don't automatically trust users or devices based on location or ownership.

    Microsegmentation: Limits communication between network segments to help contain breaches.

    Practical implementation: Zero Trust should be applied according to business needs and risk. Controls should improve security without unnecessarily preventing legitimate work.