**John the Ripper**
    - is a well-known password cracking tool use to recover passwords from password hashes.
    - It works by taking a hash and trying possible passwords until one produces a matching hash.

Learning Objectives:
    1. Cracking Windows authentication hashes
    2. Crack /etc/shadow hashes
    3. Cracking password-protected Zip files
    4. Cracking password-protected RAR files
    5. Cracking SSH keys

**What makes Hashes Secure?**
    - Hashing is designed to be one-way function. Input -> Hash
    - It is easy and fast to calculate a hash from an input, but very difficult to mathematically reverse the hash back into the original input. eg. password123 -> SHA-256 ef92b778...
        - You can easily calculate the hash, but you can't simply run SHA-256 backward to get password123.

**P vs NP**
    - P and NP are mathematical/computer-science concepts related to how efficiently problems can be solved.
        - P → Problems that can be solved efficiently by a computer.
        - NP → Problems where a solution can be verified quickly, but finding that solution may be very difficult.
    - What's important is that hashing is easy to perform, but reversing a secure hash is computationally impractical.

**Where John the Ripper Comes In**
    - How does John crack passwords? It doesnt reverse hashes.
    - It guesses possible passwords, hashes each guess, and compares the results to the target hash.
    - If the hash matches the target hash. It has found the original password
    - This is called **dictionary attack**.
    - John doesn't "unhash" passwords. It cracks hashes by repeatedly hashing password guesses and looking for a matching hash.
    - The security of password hashing therefore depends heavily on password strength and the hashing algorithm used.