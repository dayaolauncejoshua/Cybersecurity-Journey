**RSA (Rivest, Shamer, Adleman)** 
    - is an assymetric cryptographic algorithm that uses pair of mathematically related keys. This enables secure data transmission over insecure channels.

**Why RSA is secure?**
    - RSA's security relies on a mathematical problem called integer factorization.
    - Multiplying two very large prime numbers together is easy, but taking the resulting huge number and figuring out which two prime numbers were multiplied together is extremely difficult.
    - RSA uses extremely large numbers, making factorization computationally infeasible with current technology.
    - Easy to multiple, Extremely difficult to factor.

**Numerical Example**
    - RSA uses modular arithmetic (modulo) to create a public key and private key.
        1. Choose two prime numbers
            p = 157, q = 199
            n = p x q
            n = 157 x 199
            n = 31243
            n becomes part of both public and private keys
        2. Calculate ϕ(n)
            ϕ(n) = (p - 1)(q - 1)
            ϕ(n) = 30888
            - This value is used when creating the RSA keys
        3. Choose the public exponent e
            e = 163
            - The important requirement is that e must be relatively prime to ϕ(n).
            - In simple terms, they must not share a common factor other than 1.
        4. Calculate the private exponent d
            chooses d so that:
            e × d ≡ 1 mod ϕ(n)
            163 × 379 = 61,777
            61,777 mod 30,888 = 1
            Therefore:
            d = 379
        5. Create the keys
            Public key: (n, e) (31243, 163)
            Private key: (n, d) (31243, 379)
        6. Encrypts a message
            Suppose Alice wants to send:
            x = 13
            Uses public key:
            y = xᵉ mod n
            y = 16,341, 13 -> 16341 (encrypted data)
        7. Decrypt
            Receives 16,341
            Use private key:
            x = yᵈ mod n
            x = 13
            Recovered original message
    - Real RSA uses vastly larger numbers.