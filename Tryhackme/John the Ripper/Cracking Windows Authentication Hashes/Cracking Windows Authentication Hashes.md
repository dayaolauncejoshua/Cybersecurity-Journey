**Windows Authentication Hashes — NT Hash / NTLM**
    - NTHash (NT hash) is the password hash used by modern Windows systems to store user and service account passwords.

**Where are hashes stored?**
    - Windows stores local account information in the SAM (Security Account Manager) database, including:
    - Username -> NT hash password
    - In an Active Directory environment, password hashes are stored in the NTDS.dit database on domain controllers.

**How attackers obtain them?**
    - This generally requires privileged access to the Windows system or domain.
    - during testing, an attacker may obtain hashes from:
        - SAM → local Windows accounts
        - NTDS.dit → Active Directory accounts
        - Tools such as Mimikatz can be used to extract credentials/hashes when appropriate privileges are available.
    - However, cracking isn't always necessary.

**Pass-the-Hash**
    - An attacker may sometimes use the NT hash directly to authenticate without knowing the actual password. This is called pass-the-hash attack (PtH attack)
    - Obtaining an NT hash can be dangerous even if the attacker never cracks the password.

**Key takes:**
SAM → Local Windows account hashes 
NTDS.dit → Active Directory account hashes 
NT hash → Can potentially be cracked 
NT hash → Can potentially be abused in Pass-the-Hash attacks

- NT hashes are valuable credentials. Protecting them is important because attackers may either crack them or use them directly in certain authentication attacks.