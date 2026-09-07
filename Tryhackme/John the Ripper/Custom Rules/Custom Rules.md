**John — Custom Rules**
    - Custom rules allows you to command John how to modify words from a wordlist to generate more of a realistic password guesses.
    - This is useful when you know the target's password pattern

**Why it matters?**
    - Many systems, organizations now requires a complex password that contains:
        * Uppercase Letter
        * Lowercase Letter
        * Symbol
        * Number
    - Users often satisfy these requirements using predictable patterns. Eg. polopassword -> Polopassword1!
        - Instead of randomly creating a complex password, the user simply Capital letter + word + number + symbol
        - Attackers can exploit this predictability with custom rules.

**Creating a Custom Rule**
    - John's rules are defined in its john.conf file.
    - Common locations include:
        /opt/john/john.conf 
        /etc/john/john.conf
    - A rule starts with a name:
        [List.Rules:PoloPassword]
        - This creates a rule called PoloPassword.
    
   **Common Modifiers**
        1. c - Capitalize the first character
        2. Az - Append characters to the end
        3. A0 - Append characters to the beginning
    **Character sets use [ ]:**
        [0-9] → numbers 0–9 
        [A-Z] → uppercase letters 
        [a-z] → lowercase letters 
        [!£$%@] → specified symbols
    **Example Rule**
        To turn: polopassword into possible passwords such as: Polopassword1!, Polopassword2$, Polopassword7@
        The rule should be: 
            [List.Rules:PoloPassword] 
            cAz"[0-9][!£$%@]"
        - John then generates different combinations based on the rule.

**Using the Custom Rule**
    - You tell John to use your rule with:
        **john --wordlist=[wordlist] --rule=PoloPassword [hashfile]**
        eg. **john --wordlist=/usr/share/wordlists/rockyou.txt --rule=PoloPassword hashes.txt**

**Key Takeaway**
    - Custom rules let John transform normal dictionary words into password patterns that users commonly create.