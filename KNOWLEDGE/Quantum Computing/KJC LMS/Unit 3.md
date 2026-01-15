

## Overview of Classical Cryptography and Its Limitations in Quantum Computing

### **Overview of Classical Cryptography and Its Limitations in Quantum Computing**

#### **1. Classical Cryptography**

Classical cryptography consists of cryptographic techniques that rely on mathematical hardness assumptions for security. It is broadly categorized into:

- **Symmetric-Key Cryptography**
    
    - Uses the same key for encryption and decryption.
    - Examples: Advanced Encryption Standard (AES), Data Encryption Standard (DES), Triple DES.
    - Security depends on key length and computational infeasibility of brute-force attacks.
- **Asymmetric-Key Cryptography (Public-Key Cryptography)**
    
    - Uses a public key for encryption and a private key for decryption.
    - Examples: RSA (Rivest-Shamir-Adleman), Diffie-Hellman Key Exchange, Elliptic Curve Cryptography (ECC).
    - Security relies on the hardness of problems like integer factorization and discrete logarithms.
- **Hash Functions**
    
    - Used for integrity verification and digital signatures.
    - Examples: SHA-256, MD5 (now broken).
    - Security depends on resistance to collisions and preimage attacks.

#### **2. Limitations of Classical Cryptography in Quantum Computing**

Quantum computing poses a significant threat to classical cryptographic systems due to its ability to solve certain problems exponentially faster than classical computers. The primary concerns include:

- **Shor’s Algorithm (1994) – Breaking Asymmetric Cryptography**
    
    - Can efficiently factorize large numbers and compute discrete logarithms.
    - This threatens RSA, ECC, and Diffie-Hellman, rendering them insecure against quantum attacks.
    - Example: RSA-2048, which is currently secure against classical attacks, would be breakable in polynomial time by a sufficiently powerful quantum computer.
- **Grover’s Algorithm – Weakening Symmetric Cryptography**
    
    - Provides a quadratic speedup for brute-force searching.
    - Reduces the effective security of symmetric ciphers (e.g., AES-256 would be weakened to the security level of AES-128).
    - To counteract this, key sizes need to be doubled to maintain security.
- **Threat to Hash Functions**
    
    - Grover’s algorithm also weakens cryptographic hash functions by speeding up collision and preimage attacks.
    - Hash functions like SHA-256 would require increased output sizes to maintain security in a quantum context.

#### **3. Transition to Post-Quantum Cryptography**

To address these vulnerabilities, researchers are developing **post-quantum cryptographic algorithms**, designed to be secure even against quantum attacks. Examples include:

- **Lattice-Based Cryptography** (e.g., NTRU, Kyber)
- **Code-Based Cryptography** (e.g., McEliece)
- **Multivariate Polynomial Cryptography**
- **Hash-Based Cryptography** (e.g., SPHINCS+)

Quantum cryptography, particularly **Quantum Key Distribution (QKD)**, also offers a promising alternative by using quantum mechanics to achieve theoretically unbreakable encryption.





## Quantum Key Distribution (QKD) Protocols: BB84

### **Quantum Key Distribution (QKD) Protocols: BB84** 

Quantum Key Distribution (QKD) is a cryptographic method that allows two parties to generate a shared secret key using the principles of quantum mechanics. Unlike classical cryptography, which relies on computational hardness assumptions, QKD provides **provable security** based on the **laws of quantum physics**, particularly **Heisenberg’s Uncertainty Principle** and **Quantum No-Cloning Theorem**.

The two most well-known QKD protocols are:

---

## **1. BB84 Protocol (Bennett-Brassard 1984)**

**Inventors**: Charles Bennett and Gilles Brassard (1984)  
**Key Principle**: Uses quantum states of photons to securely distribute a cryptographic key.

### **Steps of the BB84 Protocol**

1. **Quantum State Transmission**
    
    - Alice (sender) sends a sequence of **randomly polarized photons** to Bob (receiver).
    - Each photon is encoded in **one of two possible bases**:
        - **Rectilinear basis** (+): Horizontal (0°) or Vertical (90°)
        - **Diagonal basis** (×): 45° or 135°
2. **Measurement by Bob**
    
    - Bob randomly chooses one of the two bases to measure each received photon.
    - If he chooses the correct basis, he gets the correct bit. If he chooses the wrong basis, he gets a random bit.
3. **Basis Reconciliation**
    
    - Bob and Alice communicate **publicly** (without revealing bit values) to compare which bases they used.
    - They discard bits measured with mismatched bases and keep only the correctly measured bits.
4. **Error Checking**
    
    - To detect eavesdropping, they randomly compare a subset of their bits.
    - If the error rate is too high, they suspect an **Eve (eavesdropper)** and discard the key.
5. **Key Distillation**
    
    - If the error rate is low, Alice and Bob apply **error correction** and **privacy amplification** to create a final secure key.

### **Security of BB84**

- If an eavesdropper (Eve) tries to measure photons, she **disturbs their quantum state**, introducing detectable errors.
- The **No-Cloning Theorem** prevents Eve from making perfect copies of quantum states.
- Any **interception attempt** can be detected, ensuring security.

**Application**: Widely implemented in real-world QKD systems and commercial quantum networks.




## E91 Protocol (Ekert 1991)

## **E91 Protocol (Ekert 1991)**

**Inventor**: Artur Ekert (1991)  
**Key Principle**: Uses **quantum entanglement** for secure key distribution.

### **Steps of the E91 Protocol**

1. **Generation of Entangled Pairs**
    
    - A third party (or Alice and Bob themselves) generates pairs of **entangled photons** in the Bell state.
    - One photon from each pair is sent to Alice, and the other is sent to Bob.
2. **Random Basis Measurement**
    
    - Alice and Bob randomly choose measurement bases:
        - Basis 1: Horizontal/Vertical (0°/90°)
        - Basis 2: Diagonal (45°/135°)
    - Due to **quantum entanglement**, their measurement results are strongly correlated.
3. **Public Basis Announcement**
    
    - Alice and Bob publicly share which bases they used, without revealing measurement outcomes.
4. **Correlation Verification (Bell’s Inequality Test)**
    
    - They check if their results violate **Bell’s inequality**, proving **quantum entanglement** and ruling out classical eavesdropping.
    - If Bell’s inequality holds, an eavesdropper is suspected, and the protocol is aborted.
5. **Key Extraction**
    
    - Alice and Bob keep only the correlated measurement results from matching bases to form a secure key.

### **Security of E91**

- **Quantum entanglement** ensures that only Alice and Bob share the correlations.
- **No-cloning and Bell’s Theorem** prevent any third party from gaining information without disturbing the system.
- More resistant to **man-in-the-middle attacks** compared to BB84.

**Application**:

- Used in **entanglement-based QKD** experiments.
- Foundations for **device-independent QKD (DIQKD)**, where security does not rely on trusting the devices.




## Comparison: BB84 vs. E91

|Feature|BB84|E91|
|---|---|---|
|**Year**|1984|1991|
|**Mechanism**|Photon polarization|Quantum entanglement|
|**Security Basis**|No-Cloning Theorem, Heisenberg’s Uncertainty Principle|Bell’s Inequality, Entanglement Correlations|
|**Eavesdropping Detection**|Disturbance in photon states|Violation of Bell’s Inequality|
|**Implementation**|Easier, widely deployed|Harder, requires entanglement|
|**Resistance to Attacks**|Good, but vulnerable to device imperfections|Stronger, can enable device-independent security|





## Quantum Secure Communication

## **Quantum Secure Communication** 

Quantum secure communication ensures **unbreakable encryption** by leveraging the principles of quantum mechanics, primarily **quantum entanglement**, **the No-Cloning Theorem**, and **Heisenberg’s Uncertainty Principle**. It provides security against **both classical and quantum adversaries**, making it resistant to attacks from quantum computers.

### **1. Quantum Secure Communication**

Quantum secure communication ensures that information exchanged between parties remains confidential and cannot be intercepted without detection. The two primary approaches are:

#### **(a) Quantum Key Distribution (QKD)**

- QKD enables two parties (Alice and Bob) to securely generate a **shared cryptographic key** using quantum mechanics.
- If an eavesdropper (Eve) tries to intercept the quantum states, she disturbs them, introducing detectable errors.
- Once a secure key is established, Alice and Bob can encrypt their messages using classical symmetric encryption (e.g., **AES**).

✅ **Protocols:**

- **BB84** (Bennett-Brassard 1984) – Based on single-photon polarization.
- **E91** (Ekert 1991) – Uses quantum entanglement.
- **Decoy State QKD** – Protects against photon number splitting (PNS) attacks.

#### **(b) Quantum Direct Communication (QDC)**

- Unlike QKD, where only the key is exchanged, **QDC allows direct transmission of messages** using quantum states.
- If an eavesdropper tries to measure the quantum states, they collapse, alerting the sender and receiver.
- Still in research phases, but promising for **high-security applications**.

✅ **Protocols:**

- **Quantum Secure Direct Communication (QSDC)** – Allows secure message transmission without a separate key exchange.
- **DSQC (Deterministic Secure Quantum Communication)** – Variation of QSDC ensuring reliability.






## Quantum Key Exchange

### **Quantum Key Exchange**

Quantum key exchange refers to the process of **establishing a shared secret key** between two parties using quantum principles.

#### **(a) QKD-Based Key Exchange**

- Uses QKD (BB84, E91, etc.) to establish a symmetric encryption key.
- Once the quantum key is exchanged, **AES or One-Time Pad (OTP)** can be used for message encryption.

#### **(b) Post-Quantum Cryptography (PQC)**

- Since **QKD requires specialized quantum hardware**, researchers are developing **classical cryptographic methods** resistant to quantum attacks.
- **Lattice-based, code-based, and multivariate polynomial cryptosystems** provide alternatives to QKD for quantum-safe key exchange.

✅ **Quantum-Secure Key Exchange Algorithms:**

- **Kyber** (Lattice-based) – Standardized for post-quantum key exchange.
- **McEliece** (Code-based) – Secure but requires large key sizes.

### **3. Applications of [Quantum Secure Communication](https://www.kristujayantiexamlms.com/mod/lesson/view.php?id=226504 "Quantum Secure Communication")**

🔹 **Military and Government Communications** – Protects classified information from cyber espionage.  
🔹 **Financial Transactions** – Secures banking and payment systems against quantum threats.  
🔹 **Secure Satellite Communications** – China’s **Micius satellite** demonstrated quantum-secure key exchange globally.  
🔹 **Quantum Internet** – Future networks based on entanglement for ultra-secure communication.




