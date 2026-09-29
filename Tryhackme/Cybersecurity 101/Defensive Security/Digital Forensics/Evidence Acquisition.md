**Evidence Acquisition in Digital Forensics**

    Evidence acquisition is the process of collecting digital evidence while preserving the original data.

    Collect the evidence without changing, damaging, or contaminating it.

**Three Important Practices**

    1. Proper Authorization
    
    Before collecting digital evidence, investigators need proper legal authorization from the appropriate authority.

    This is important because digital devices can contain private and sensitive information.

    For example, investigators shouldn't simply take and examine someone's laptop without the appropriate legal authority.

    Key: Collect evidence within the limits of the law.


    2. Chain of Custody

    Chain of custody is a documented record showing who handled the evidence, when they handled it, and where it was stored.

    Evidence collected
        ↓
    Investigator A
        ↓
    Forensic Lab
        ↓
    Investigator B
        ↓
    Evidence Storage

    The documentation can include:

    Description of the evidence
    Who collected it
    Date and time collected
    Where it is stored
    Who accessed it
    When it was accessed

    This creates a traceable history of the evidence.

    Why is this important?
    
    If someone asks "How do we know this evidence wasn't changed or mishandled?"

    The chain of custody provides documentation showing how the evidence was handled from collection onward.


    3. Write Blockers
    A write blocker is a hardware or software mechanism that prevents data from being written to the original evidence device while allowing investigators to read the data.

    Example:
    Suspect Hard Drive
        ↓
    Write Blocker
        ↓
    Forensic Workstation
    
    Without a write blocker:
    Hard Drive ← Forensic Workstation
              ↓
       Possible changes

    The forensic computer could potentially write data to the drive, such as modifying metadata or timestamps.

    With a write blocker:
    Hard Drive ──→ Forensic Workstation
        ↑
        │
    Writes blocked 
    Reads allowed 

    The original drive remains unchanged, which helps preserve its forensic integrity.

    Authorization → Are we legally allowed to collect it?

    Chain of Custody → Who handled it and when?

    Write Blocker → Prevent changes to the original evidence.