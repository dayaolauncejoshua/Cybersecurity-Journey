**Cracking Password Hashes**
    - Hashes cannot be decrypted because hashes are one-way. Instead, attackers try to crack hash by guessing possible passwords.
    - If the calculated hash matches the stolen hash, the attacker has found the original password.

**What about Salt?**
    - A salt doesn't prevent password cracking. Instead, it makes password cracking more difficult. 
    - It ensures that each password has different hash.
    - Attackers can still obtain the salt used and include it when testing passwords.

**Common Cracking Tools**
    1. Hashcat - powerful password/hash cracking tool
    2. John the Ripper - password-cracking tool

**Cracking Passwords with GPUs**
    - GPUs (Graphics Processing Units) have thousands of small processing cores designed to perform many mathematical calculations in parallel.
    - This makes GPUs very effective for password/hash cracking, because attackers can test many password guesses at the same time.
    - Tools like Hashcat can use GPUs to greatly speed up cracking for many hash types.

    - Why Bcrypt Is Different
        - bcrypt, are designed to be computationally expensive and resistant to GPU acceleration.
        - Make each password guess expensive, so attackers cannot test huge numbers of guesses quickly—even with powerful GPUs.
    - Key take:
        - GPUs make many hash-cracking attacks much faster, so secure password hashing algorithms like bcrypt, scrypt, and Argon2 are designed to make large-scale cracking expensive.

**Cracking Passwords on VMs**
    - Virtual Machines (VMs) usually don't have direct access to the host computer's GPU. GPU passthrough is possible, but it can be complicated to configure.
    - VMs can also have some performance overhead, meaning CPU/GPU operations may be slower than running directly on the host.

1. Hashcat
    - Hashcat benefits heavily from GPUs because it can perform many hash calculations in parallel.
    - For best performance, run hashcat directly on the Host OS, especially if you have a powerful GPU.
        - It can also run inside a VM using OpenCL, but performance will usually be worse.
    - Best on host
2. John the Ripper
    - John the Ripper uses the CPU by default, so it works easily inside a VM.
    - However, running it directly on the host can still provide better performance because it avoids virtualization overhead and gives it better access to CPU cores/threads.
    - Works well in VMs

**CRACKING SOME HASHES**

**Hashcat Basic Syntax**
    - Hashcat follows this basic structure:
        - hashcat -m <hash_type> -a <attack_mode> hashfile wordlist
        - What hash? → How should I attack it? → Where is the hash? → What passwords should I try?
            1. -m <hash_type> - Specifies what type of hash you are trying to crack. eg. -m 1000 == NTLM
            2. -a <attack_mode> - Specifies how Hashcat should generate/test password guesses. eg. -a 0. 0 = Straight attack
            3. hashfile - The file containing the target hash you want to crack.
            4. wordlist - The file containing possible passwords to try. eg. rockyou.txt
        - hashcat -m 1000 -a 0 hashes.txt rockyou.txt