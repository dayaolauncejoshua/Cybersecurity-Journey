**Hashing Passwords**
    - Instead of storing user's actual password, a website can store its hash.
    - When user logs in, the website hashes the password they entered and compares with the stored hashes for verification.
    - This means actual passwords doesn't need to be stored.

**Problem: Same password = Same hash**
    - A hash function always produces the same output for the same input.
    - Attackers will know which users use the same password.

**Rainbow tables**
    - Attackers use this as like a list or collection of computed Password -> Hash
    - Example:
        - password123 → ef92...
        - qwerty123 → 7c4a...
        - letmein → 1a8f...
    - Attackers can look to the table if they obtained the hash instead of cracking the hash from scratch

Cybersecurity take:
    - Simply hashing passwords is not enough.
    - This is solved by adding a salt to it. hash algorithm + salt. This will make attacks harder

**Salting Passwords**
    - is adding random, unique value to each password before hashing it.
    - The salt is stored in database along with the password hash

**Why use salt?**
    - It adds uniqueness to passwords, that even the same password/input would not have the same hash outputs
    - Without salt:
        Alice: Password123 → ABC789 
        Bob: Password123 → ABC789
    - With unique salts:
        Alice: Password123 + SaltA → XYZ123
        Bob:   Password123 + SaltB → QWE456
    - This makes rainbow table much less effective.

**Secure Password Storage**
    - Secure system generally:
        1. Uses a password-hashing algorithm such as Argon2, Scrypt, bcrypt, or PBKDF2.
        2. Generates a unique random salt for each password.
        3. Combine password and salt
        4. Hashes the combination.
        5. Stores the hash and salt in the database.
    - Password + Unique salt = Password hash 
    - Algorithms such as bcrypt and scrypt handle salting as part of their password-hashing process.

**Why not encrypt passwords?**
    - Encryption is reversible if you have the key.
    - If attackers gets both the database and the key, they can decrypt all the passwords. 
    - For authentication, you don't need to recover the original password. You only need to verify that the user knows it.