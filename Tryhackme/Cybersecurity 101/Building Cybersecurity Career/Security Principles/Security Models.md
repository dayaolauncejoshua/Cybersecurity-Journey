# Security Models

    Security models are frameworks that define rules for protecting information and systems. They help enforce security principles such as confidentiality and integrity.

    The three foundational models are:
    1. Bell-LaPadula
    2. Biba
    3. Clark-Wilson

### 1.Bell-LaPadula Model - Confidentiality

    Prevent unauthorized disclosure of sensitive information.

    This model uses security levels, such as Confidential, Secret, and Top Secret

    A. Main Rules

    1. Simple Security Property - No Read Up

    A subject cannot read information at a higher security level than their own.

    Example: An employee with Secret clearance cannot read a Top Secret document.

    
    2. Star (*) Security Property - No Write Down

    A subject cannot write information to a lower security level.

    Example: A user handling Top Secret information cannot copy that information into a Confidential document, preventing sensitive information from leaking to a lower level.


    3. Discretionary-Security Property

    Access is also controlled through permissions, which determine whether a subject may read or write a particular object.

    Example: Even if a user has an appropriate security clearance, an access-control rule may still deny access to a specific file.

### Note

    Bell-LaPadula is commonly summarized as:

    No read up
    No write down
    Often remembered as write up, read down for the allowed direction of information flow.

    Its primary focus is confidentiality, not preventing unauthorized data modification.

### 2.Biba Model - Integrity

    Protect data from unauthorized or improper modification and preserve its trustworthiness. Instead of security classifications for confidentiality, think of different levels of data integrity.

    A. Main Rules

    1. Simple Integrity Property — No Read Down

    A subject at a higher integrity level should not read data from a lower integrity level.
    Example: A highly trusted financial application should not rely directly on unverified data from a low-integrity source.


    2. Star (*) Integrity Property — No Write Up

    A subject at a lower integrity level cannot write to an object at a higher integrity level.
    Example: An ordinary, untrusted process must not be allowed to modify a highly trusted system file.

    Note:
    Summarized as No read down, no write up, and often remembered as read up, write down for the allowed direction of information flow.

    Biba focuses on integrity, whereas Bell-LaPadula focuses on confidentiality. Biba's basic rules alone do not address every possible insider threat or security problem.


### 3.Clark-Wilson Model - Integrity Through Controlled Transactions

    Maintain data integrity by ensuring that data is modified only through approved, controlled procedures.

    Clark-Wilson is particularly relevant to business systems, banking, and financial transactions.

    A. Main Concepts

    1. Constrained Data Item (CDI) - Data whose integrity must be protected.
    
    Example: A customer's official bank balance.


    2. Unconstrained Data Item (UDI) - Input that has not yet been validated or brought under the model's integrity controls.

    Example: A value entered into a transfer form by a user.


    3. Transformation Procedure (TP) - An approved operation that modifies or processes protected data according to defined rules.

    Example: A banking transaction procedure that transfers money between accounts while checking that the transaction is valid.

    
    4. Integrity Verification Procedure (IVP) - A procedure that checks whether protected data satisfies its integrity requirements.

    Example: A check that verifies account balances and transaction records are consistent.

### Example: Bank Transfer

    A customer requests a transfer of P1,000

      1. The transfer amount is submitted as input (UDI)
      2. The system validates the requres and authorization.
      3. An approved transformation procedure performs the transfer
      4. Integrity checks help confirm that the transaction was recorded correctly

    The process helps prevent unauthorized or invalid changes to protected financial data.

### Other Security Models

    Additional models include:

    Brewer-Nash (Chinese Wall): Helps prevent conflicts of interest when accessing sensitive information.

    Goguen-Meseguer: Focuses on security policies and information flow between system components.

    Sutherland: Focuses on preventing improper information flow.

    Graham-Denning: Defines rules for securely creating and managing subjects, objects, and access rights.

    Harrison-Ruzzo-Ullman (HRU): Examines how access rights can change and whether unauthorized rights can arise.

### Key takes

    Bell-LaPadula = Confidentiality: Stop sensitive information from flowing to lower security levels.

    Biba = Integrity: Prevent lower-integrity data or subjects from improperly influencing higher-integrity information.

    Clark-Wilson = Integrity: Protect data through approved transactions, separation of duties, and verification procedures.

    Bell-LaPadula protects secrets; Biba protects trustworthiness; Clark-Wilson protects integrity through controlled processes.






