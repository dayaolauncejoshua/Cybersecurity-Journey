**What is Hashing**
    - Hashing is the process of converting data into a fixed length of strings called hash or **hash value**
    - This is commonly used for storing passwords, file integrity, etc.
    - A hash value is a fixed-size string or characters that is computed by a hash function.
**Hash Function** 
    - A hash function is an algorithm that takes any data and produces a fixed-size hash value (digital fingerprint).
    - SHA-256, MD5, SHA-3, SHA-1
    - Hash functions differs from encryption. It is a one-way, and it is not reversible.

**Why Hashing is Important?**
    - Hashing is mainly used in cybersecurity for integrity and password protection.

1. Passwords
    - When creating an account, a secure website should not store your actual password in their server/database. Instead, it stores its hash value.
    - When logging in, it verifies your password input's hash value and compares one of the stored hash in the database.
    - This means that attackers won't be able to get your original password if the database was compromised.

**Hash Collisions**
    - this occurs when two different inputs produce the same hash.
    - Input A → Hash function → ABC123, Input B → Hash function → ABC123
    - Collisions are unavoidable in theory because inputs are unlimited and there is a limitation on possible hash outputs. This is what they call "pigeonhole effect", more inputs than possible outputs.
    - That's why a good hash function can avoid this.
**MD5 and SHA-1**
    - these hash functions are considered insecured in today's time. There are records and studies of them that collisions occur with these functions.
    - Therefore, they must not be used anymore for password protection and verifying security sensitive data.
    - Instead, use modern hashing functions or stronger algorithm such as **SHA-256** or dedicated password hashing algorithm such as **Argon2, bcrypt, or scrypt**.

