## 4. Breaking RSA: Classical Weaknesses vs Quantum Breaks

### Classical Weaknesses (Already Exploited)

Even today, RSA fails in real-world deployments due to:

- insufficient key sizes
- weak entropy during key generation
- incorrect padding or protocol misuse

These attacks do **not** break RSA mathematically.  
They break how it is implemented and deployed.

This is why RSA is still considered secure  
*when used correctly*.

---

### Quantum Break (Fundamental)

Shor’s algorithm demonstrates that:

- factoring large integers can be done efficiently on a quantum computer

If large-scale quantum computers become practical:

- RSA becomes cryptographically obsolete
- increasing key size will not help

This is a **fundamental break**, not an implementation issue.
