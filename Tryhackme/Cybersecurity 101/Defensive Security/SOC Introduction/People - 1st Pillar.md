**People in a SOC**

    Even with highly automated security tools, people are still essential because security tools can generate a huge number of alerts, including false positives.

    Think of a SOC like a fire department:

    Security tools = fire alarms
    SOC analysts = firefighters
    Alerts = reported fires
    False positives = smoke from cooking, not an actual fire

    The tools can detect suspicious activity, but humans determine what actually matters and what action should be taken.

**SOC Roles**

    SOC Analyst L1 
        - First person to handle alerts. Performs basic alert triage and determines whether an alert is potentially harmful.

    SOC Analyst L2
        - Performs deeper investigation when L1 cannot resolve an alert. Correlates information from multiple sources.

    SOC Analyst L3
        - Experienced analyst who performs advanced investigation, threat hunting, and incident response. Helps with containment, eradication, and recovery.
    
    Security Engineer
        - Deploys, configures, and maintains security tools such as SIEM, EDR, IDS/IPS, etc.

    Detection Engineer
        - Creates and improves detection rules/logic that security tools use to identify suspicious activity.

    SOC Manager
        - Manages the SOC's people, processes, and operations and communicates the SOC's security posture to leadership/CISO.

**How the levels work (Simplified):**

    Security Tool
        ↓
    Alert
        ↓
    L1 Analyst
    Basic triage
        ↓
    Needs deeper investigation?
        ↓
    L2 Analyst
    Deep investigation
        ↓
    Serious/complex incident?
        ↓
    L3 Analyst
    Threat hunting + Incident Response

    Not every alert reaches L3. L1 handles the initial volume, L2 investigates more complex cases, and L3 handles advanced threats and serious incidents.

**Important point:**

    SOC roles can vary between organizations. A small company might have one person handling several responsibilities, while a large organization may have dedicated teams for each role.

    Key takeaway: Security tools detect and generate alerts, but people provide the analysis, judgment, investigation, and response needed to determine what actually matters.
