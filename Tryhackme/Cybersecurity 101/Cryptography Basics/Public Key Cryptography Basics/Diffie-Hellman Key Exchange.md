**Diffie-Hellman (DH)**
    - is a key exchange method that allows two parties to create a shared secret key over an insecure network without directly sending the secret key.
    - The shared secret can then be used for symmetric encryption.

**How can both party agree on a secret key if an attacker can see their network traffic?**
    - Diffie-Hellman solves this by allowing both parties to calculate the same secret independently.
    - Important terms:
        * p - Large prime number; public
        * g - Generator; public
        * a - Person 1 private key
        * b - Person 2 private key
        * A - Person 1 public key
        * B - Person 2 public key
        * Shared secret - Secret calculated by both P1 and P2
    - Process:
        1. Agree on public values
            p = 29
            g = 3
            - These is public
        2. Choose private keys
            P1: a = 13
            P2: b = 15
            - These must remain secret
        3. Calculate public keys
            P1:
                A = gᵃ mod p
                A = 3¹³ mod 29
                A = 19
            P2:
                B = gᵃ mod p
                B = 3¹⁵ mod 29
                B = 26
        4. Exchange public keys
            P1 → 19 → P2
            P2 → 26 → P1
            - An attacker can see these values.
        5. Calculate the shared secret
            P1:
                Bᵃ mod p
                26¹³ mod 29 = 10
            P2:
                Aᵇ mod p
                19¹⁵ mod 29 = 10
        Therefore:
            P1 shared secret: 10
            P2 shared secret: 10
            They now have the same secret without sending 10 across the network.

**Cybersecurity Importance**
    An attacker may see:
    p = 29
    g = 3
    A = 19
    B = 26

    But the attacker does not know:
    a = 13
    b = 15

    With real-world parameters, discovering the private values from the public information is computationally infeasible.

    The resulting shared secret can then be used to establish symmetric encryption for the actual communication.

**Diffie-Hellman + RSA**
    - Diffie-Hellman and RSA can work together to secure communication. Diffie-Hellman is mainly used to create a shared secret key between two parties, while RSA can be used to verify identity through digital signatures and authentication. For example, RSA can help Alice confirm that she is really communicating with Bob instead of an attacker pretending to be Bob, helping prevent Man-in-the-Middle (MITM) attacks. Together, they provide stronger security by helping with key agreement, authentication, confidentiality, and integrity.