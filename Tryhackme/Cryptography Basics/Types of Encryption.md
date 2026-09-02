**Types of Encryption**

1. Symmetric Encryption / Symmetric Cryptography
    - Uses the same key to encrypt and decrypt data.
    - Key must be kept secret. It is all called **private key cryptography**
    - Examples:
        1. Data Encryption Standard (DES)
            - Adopted in 1977. Uses 56-bit key.
            - Considered insecure today as it is vulnerable to brute force attacks
        2. 3DES (Triple DES)
            - Applies DES three times
            - Uses a 168-bit key (effective security ≈ 112 bits)    
            - Improvement of DES but deprecated in 2019
            - Still used on legacy systems
        3. AES (Advanced Encryption Standard)
            - Fast, secure, and the current standard for symmetric encryption supports 128, 192, and 256-bit keys adopted in 2001.

    2. Assymetric Encryption / Assymetric Cryptography
        - Unlike symmetric encryption, assymetric encryption uses a pair of keys. One to encrypt and one to decrypt.
            - Public key - Can be shared with everyone. For encryption
            - Private key - must be kept secret. For decryption
        - It encrypts data using public key. It is also called public key cryptography.
        - Common Examples
            1. RSA
            2. Diffie-Hellman
            3. ECC (Elliptic Curve Cryptography)
        - For example:
            - RSA: 2048, 3072, or 4096-bit keys
            - ECC: A 256-bit key can provide security comparable to roughly a 3072-bit RSA key.
            - ECC can provide stronger securit with smaller keys