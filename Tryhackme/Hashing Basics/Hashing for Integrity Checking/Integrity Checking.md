**Integrity Checking**
    - Hashing can verify whether a file has been changed.
    - A hash function produces the same hash for the exact same data. Even a tiny change to the file will produce a significantly different hash.
    - Real-World Example
        - When you download a Fedora ISO, the official website provides its expected SHA-256 hash.
        - You can calculate the hash of your downloaded file
        - Then compare it with the official hash.
        - If they match, you can be confident that your file is identical to the official file.
    Key take:
        - Hashing provides a way to verify file integrity. If the hashes match, the files have the same contents; if they differ, the contents differ.

**HMACs**
    - **HMAC (Hash-based Message Authentication Code)** combines a cryptographic hash function + secret key to verify both:
        1. Integrity → The message was not modified.
        2. Authenticity → The message came from someone who knows the secret key.
    - How it works:
        - The sender generates an HMAC using the message and secret key and sends it with the message.
        The receiver, who also knows the secret key, calculates the HMAC again. If the values match: Sender HMAC = Receiver HMAC
        - If attackers changes the message, HMAC will no longer match
    - HMAC uses a standardized process involving:
        1. Preparing the secret key to match the hash function's block size.
        2. Combining the key with an internal constant using XOR.
        3. Hashing the message with this modified key.
        4. Hashing the result again with another key-derived value.
        5. Producing the final fixed-size HMAC value.
    - HMAC = Hashing + Secret Key → verifies integrity AND authenticity.