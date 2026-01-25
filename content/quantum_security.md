## 2. What Quantum Computers Do in Terms of Security

From a security perspective, quantum computers are **not universally dangerous**.

They do **not**:

- instantly break all encryption
- replace brute-force attacks everywhere

They **do**:

- fundamentally weaken cryptographic systems based on certain mathematical problems

### Cryptographic Assumptions at Risk

Modern public-key cryptography relies on problems that are:

- easy to compute in one direction
- extremely hard to reverse

Examples:

- factoring large integers (RSA)
- discrete logarithms (Diffie–Hellman, ECC)

Quantum algorithms change the cost of reversing these problems.

This is a **threat model change**, not a bug.
